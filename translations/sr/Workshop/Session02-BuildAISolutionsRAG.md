<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "72de9f8878960ee83159ae9e8f592ea0",
  "translation_date": "2025-10-28T23:21:22+00:00",
  "source_file": "Workshop/Session02-BuildAISolutionsRAG.md",
  "language_code": "sr"
}
-->
# Сесија 2: Изградња AI решења са Azure AI Foundry

## Апстракт

Истражите како да изградите применљиве GenAI радне токове користећи Foundry Local и Azure AI Foundry. Научите напредно креирање упутстава, интегришите структуриране податке и оркестрирајте задатке са репродуктивним цевоводима. Иако је фокус на Retrieval-Augmented Generation (RAG) за Q&A са документима и подацима, обрасци се могу применити на шири дизајн GenAI решења.

## Циљеви учења

На крају ове сесије, моћи ћете:

- **Овладати креирањем упутстава**: Дизајнирајте ефикасна системска упутства и стратегије за утемељење
- **Применити RAG обрасце**: Изградите Q&A системе засноване на документима уз помоћ векторске претраге
- **Интегрисати структуриране податке**: Радите са CSV, JSON и табеларним подацима у AI радним токовима
- **Изградити продукцијски RAG**: Креирајте скалабилне RAG апликације уз Chainlit
- **Повезати локално са облаком**: Разумети путеве миграције од Foundry Local до Azure AI Foundry

## Предуслови

- Завршена Сесија 1 (постављање Foundry Local)
- Основно разумевање векторских база података и уградњи
- Искусто у програмирању на Python-у
- Познавање концепата обраде докумената

### Брзи почетак у окружењу за више платформи (Windows & macOS)

Windows PowerShell:
```powershell
py -m venv .venv
 .\.venv\Scripts\Activate.ps1
pip install --upgrade pip
pip install foundry-local-sdk openai sentence-transformers ragas datasets scikit-learn
```

macOS / Linux:
```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install --upgrade pip
pip install foundry-local-sdk openai sentence-transformers ragas datasets scikit-learn
```

Ако Foundry Local macOS бинарни фајлови још увек нису доступни у вашем окружењу, покрените сервис на Windows VM-у или контејнеру и поставите:
```bash
export FOUNDRY_LOCAL_ENDPOINT=http://<windows-host>:5273/v1
```


## Валидација: Провера локалног окружења Foundry

Пре него што започнете демонстрације, проверите своје локално окружење:

```powershell
foundry --version              # Ensure CLI is installed
foundry status                 # Service status
foundry model run phi-4-mini   # Start baseline SLM
curl http://localhost:5273/v1/models  # Validate API (should list running model)
```

Ако последња команда не успе, покрените (или поново покрените) сервис: `foundry service start`.

## Ток демонстрације (30 минута)

### 1. Системска упутства и стратегије утемељења (10 минута)

#### Корак 1.1: Напредно креирање упутстава

Креирајте `samples/02-rag-solutions/prompt_engineering.py`:

```python
#!/usr/bin/env python3
"""
Advanced Prompt Engineering with Foundry Local
Demo: System prompts, grounding, and context management
Reference: https://learn.microsoft.com/en-us/azure/ai-foundry/foundry-local/reference/reference-sdk?pivots=programming-language-python
"""

import os
from openai import OpenAI
from typing import List, Dict, Any

class PromptEngineer:
    """Advanced prompt engineering utilities for Foundry Local"""
    
    def __init__(self, base_url: str = "http://localhost:5273/v1"):
        self.client = OpenAI(
            base_url=base_url,
            api_key="not-needed"
        )
    
    def create_grounded_prompt(self, 
                             context: str, 
                             question: str, 
                             domain: str = "general") -> List[Dict[str, str]]:
        """Create a grounded prompt with context and domain expertise"""
        
        system_prompts = {
            "general": "You are a helpful AI assistant. Use the provided context to answer questions accurately and concisely.",
            "medical": "You are a medical AI assistant. Provide evidence-based responses using the medical literature context. Always include disclaimers about consulting healthcare professionals.",
            "legal": "You are a legal research assistant. Analyze the provided legal documents and statutes. Note that this is for informational purposes only.",
            "technical": "You are a technical documentation assistant. Provide detailed, accurate responses based on the technical documentation provided.",
            "financial": "You are a financial analysis assistant. Use the provided financial data to give insights while noting this is not financial advice."
        }
        
        return [
            {
                "role": "system", 
                "content": system_prompts.get(domain, system_prompts["general"])
            },
            {
                "role": "user", 
                "content": f"""
                Context Information:
                {context}
                
                Question: {question}
                
                Please provide a comprehensive answer based on the context above. If the context doesn't contain enough information to fully answer the question, please state that clearly.
                """.strip()
            }
        ]
    
    def chat_with_grounding(self, 
                          context: str, 
                          question: str, 
                          model: str = "phi-4-mini",
                          domain: str = "general") -> Dict[str, Any]:
        """Execute grounded chat completion"""
        
        messages = self.create_grounded_prompt(context, question, domain)
        
        try:
            response = self.client.chat.completions.create(
                model=model,
                messages=messages,
                max_tokens=1000,
                temperature=0.3,  # Lower temperature for more consistent responses
                top_p=0.9
            )
            
            return {
                "answer": response.choices[0].message.content,
                "model": response.model,
                "tokens": response.usage.total_tokens if response.usage else None,
                "context_length": len(context),
                "domain": domain
            }
            
        except Exception as e:
            return {"error": str(e)}

def demo_grounding_strategies():
    """Demonstrate different grounding strategies"""
    
    engineer = PromptEngineer()
    
    # Sample contexts for different domains
    contexts = {
        "technical": """
        Microsoft Foundry Local is a development platform that enables running AI models locally on Windows devices. 
        It supports various model formats including ONNX and provides hardware acceleration through DirectML.
        The platform includes a CLI for model management and an OpenAI-compatible API for integration.
        Models can be cached locally and run without internet connectivity.
        """,
        
        "financial": """
        Q3 2024 Results: Revenue $45.2M (up 23% YoY), Operating Margin 18.5%, 
        Cash Flow $12.3M, R&D Investment $8.7M (19% of revenue).
        Key metrics: Customer Acquisition Cost $1,200, Lifetime Value $15,600, Monthly Churn 2.1%.
        Geographic breakdown: North America 65%, Europe 25%, APAC 10%.
        """
    }
    
    questions = {
        "technical": "How does Foundry Local handle model caching and what are the benefits?",
        "financial": "What is the current financial health and what are the key performance indicators?"
    }
    
    for domain in ["technical", "financial"]:
        print(f"\n{'='*50}")
        print(f"Domain: {domain.upper()}")
        print(f"{'='*50}")
        
        result = engineer.chat_with_grounding(
            context=contexts[domain],
            question=questions[domain],
            domain=domain
        )
        
        if "error" in result:
            print(f"Error: {result['error']}")
        else:
            print(f"Answer: {result['answer']}")
            print(f"Tokens used: {result['tokens']}")
            print(f"Context length: {result['context_length']} characters")

if __name__ == "__main__":
    demo_grounding_strategies()
```

#### Корак 1.2: Тестирајте стратегије утемељења

```powershell
# Ensure phi-4-mini is running
foundry model run phi-4-mini

# Run the prompt engineering demo
python samples/02-rag-solutions/prompt_engineering.py
```


### 2. Интеграција табеларних података са упутствима (CSV Q&A) (10 минута)

#### Корак 2.1: Интеграција CSV података

Креирајте `samples/02-rag-solutions/csv_qa_system.py`:

```python
#!/usr/bin/env python3
"""
CSV Q&A System with Foundry Local
Demo: Structured data integration and tabular reasoning
Reference: https://learn.microsoft.com/en-us/azure/ai-foundry/foundry-local/reference/reference-sdk?pivots=programming-language-python
"""

import pandas as pd
import json
from openai import OpenAI
from typing import Dict, Any, List
import io

class CSVQASystem:
    """CSV Question-Answering system using Foundry Local"""
    
    def __init__(self, base_url: str = "http://localhost:5273/v1"):
        self.client = OpenAI(
            base_url=base_url,
            api_key="not-needed"
        )
        self.data = None
        self.summary_stats = None
    
    def load_csv_data(self, csv_path: str) -> bool:
        """Load and analyze CSV data"""
        try:
            self.data = pd.read_csv(csv_path)
            self.summary_stats = self._generate_summary_stats()
            return True
        except Exception as e:
            print(f"Error loading CSV: {e}")
            return False
    
    def _generate_summary_stats(self) -> Dict[str, Any]:
        """Generate comprehensive summary statistics"""
        stats = {
            "shape": self.data.shape,
            "columns": list(self.data.columns),
            "dtypes": self.data.dtypes.to_dict(),
            "null_counts": self.data.isnull().sum().to_dict(),
            "sample_rows": self.data.head(3).to_dict('records')
        }
        
        # Add numerical statistics for numeric columns
        numeric_cols = self.data.select_dtypes(include=['number']).columns
        if len(numeric_cols) > 0:
            stats["numeric_summary"] = self.data[numeric_cols].describe().to_dict()
        
        # Add categorical summaries
        categorical_cols = self.data.select_dtypes(include=['object']).columns
        if len(categorical_cols) > 0:
            stats["categorical_summary"] = {}
            for col in categorical_cols:
                stats["categorical_summary"][col] = {
                    "unique_count": self.data[col].nunique(),
                    "top_values": self.data[col].value_counts().head(5).to_dict()
                }
        
        return stats
    
    def create_data_context(self, question: str) -> str:
        """Create relevant data context for the question"""
        context_parts = [
            f"Dataset Overview:",
            f"- Shape: {self.summary_stats['shape'][0]} rows, {self.summary_stats['shape'][1]} columns",
            f"- Columns: {', '.join(self.summary_stats['columns'])}"
        ]
        
        # Add sample data
        context_parts.append("\nSample Data:")
        for i, row in enumerate(self.summary_stats['sample_rows'][:3]):
            context_parts.append(f"Row {i+1}: {json.dumps(row, default=str)}")
        
        # Add relevant statistics based on question content
        question_lower = question.lower()
        
        if any(word in question_lower for word in ['average', 'mean', 'sum', 'count', 'max', 'min', 'statistics']):
            if 'numeric_summary' in self.summary_stats:
                context_parts.append("\nNumerical Statistics:")
                for col, stats in self.summary_stats['numeric_summary'].items():
                    context_parts.append(f"{col}: mean={stats['mean']:.2f}, std={stats['std']:.2f}, min={stats['min']}, max={stats['max']}")
        
        if any(word in question_lower for word in ['category', 'group', 'type', 'unique']):
            if 'categorical_summary' in self.summary_stats:
                context_parts.append("\nCategorical Data Summary:")
                for col, info in self.summary_stats['categorical_summary'].items():
                    context_parts.append(f"{col}: {info['unique_count']} unique values, top: {list(info['top_values'].keys())[:3]}")
        
        return "\n".join(context_parts)
    
    def answer_question(self, question: str, model: str = "phi-4-mini") -> Dict[str, Any]:
        """Answer questions about the CSV data"""
        
        if self.data is None:
            return {"error": "No data loaded. Please load CSV data first."}
        
        context = self.create_data_context(question)
        
        messages = [
            {
                "role": "system",
                "content": """
                You are a data analysis assistant. You have access to a CSV dataset and its summary statistics.
                Answer questions about the data accurately based on the provided context.
                If calculations are needed, explain your reasoning.
                If the data doesn't contain enough information to answer the question, state that clearly.
                """.strip()
            },
            {
                "role": "user",
                "content": f"""
                Data Context:
                {context}
                
                Question: {question}
                
                Please analyze the data and provide a comprehensive answer.
                """.strip()
            }
        ]
        
        try:
            response = self.client.chat.completions.create(
                model=model,
                messages=messages,
                max_tokens=800,
                temperature=0.2  # Low temperature for factual data analysis
            )
            
            return {
                "answer": response.choices[0].message.content,
                "model": response.model,
                "tokens": response.usage.total_tokens if response.usage else None,
                "dataset_shape": self.data.shape
            }
            
        except Exception as e:
            return {"error": str(e)}

def create_sample_dataset():
    """Create a sample dataset for demonstration"""
    
    # Create sample sales data
    sales_data = {
        'Date': ['2024-01-01', '2024-01-02', '2024-01-03', '2024-01-04', '2024-01-05',
                 '2024-01-06', '2024-01-07', '2024-01-08', '2024-01-09', '2024-01-10'],
        'Product': ['Laptop', 'Phone', 'Tablet', 'Laptop', 'Phone', 
                   'Accessories', 'Laptop', 'Tablet', 'Phone', 'Accessories'],
        'Sales_Amount': [1200, 800, 600, 1100, 850, 150, 1300, 580, 780, 200],
        'Quantity': [1, 1, 1, 1, 1, 3, 1, 1, 1, 4],
        'Region': ['North', 'South', 'East', 'West', 'North', 
                  'South', 'East', 'West', 'North', 'South'],
        'Sales_Rep': ['Alice', 'Bob', 'Charlie', 'Diana', 'Alice',
                     'Bob', 'Charlie', 'Diana', 'Alice', 'Bob']
    }
    
    df = pd.DataFrame(sales_data)
    csv_path = "samples/02-rag-solutions/sample_sales_data.csv"
    
    # Ensure directory exists
    os.makedirs(os.path.dirname(csv_path), exist_ok=True)
    
    df.to_csv(csv_path, index=False)
    return csv_path

def demo_csv_qa():
    """Demonstrate CSV Q&A capabilities"""
    
    # Create sample dataset
    csv_path = create_sample_dataset()
    print(f"Created sample dataset: {csv_path}")
    
    # Initialize Q&A system
    qa_system = CSVQASystem()
    
    # Load data
    if not qa_system.load_csv_data(csv_path):
        print("Failed to load CSV data")
        return
    
    print(f"\nLoaded dataset with shape: {qa_system.data.shape}")
    
    # Example questions
    questions = [
        "What is the total sales amount?",
        "Which product has the highest average sales amount?",
        "How many sales were made in the North region?",
        "Who is the top performing sales representative?",
        "What is the average quantity sold per transaction?"
    ]
    
    for i, question in enumerate(questions, 1):
        print(f"\n{'='*60}")
        print(f"Question {i}: {question}")
        print(f"{'='*60}")
        
        result = qa_system.answer_question(question)
        
        if "error" in result:
            print(f"Error: {result['error']}")
        else:
            print(f"Answer: {result['answer']}")
            print(f"Tokens used: {result['tokens']}")

if __name__ == "__main__":
    demo_csv_qa()
```

#### Корак 2.2: Тестирајте CSV Q&A систем

```powershell
# Run the CSV Q&A demo
python samples/02-rag-solutions/csv_qa_system.py
```


### 3. Почетни пројекат: Адаптација 02-grounding-data (5 минута)

#### Корак 3.1: Унапређени документ RAG систем

Креирајте `samples/02-rag-solutions/document_rag.py`:

```python
#!/usr/bin/env python3
"""
Document RAG System with Foundry Local
Demo: Document processing, vector search, and retrieval-augmented generation
Reference: https://learn.microsoft.com/en-us/azure/ai-foundry/foundry-local/reference/reference-sdk?pivots=programming-language-python
"""

import os
from openai import OpenAI
import requests
from typing import List, Dict, Any
import numpy as np
from sklearn.metrics.pairwise import cosine_similarity
from sklearn.feature_extraction.text import TfidfVectorizer
import json

class SimpleRAGSystem:
    """Simple RAG system using TF-IDF for demonstration"""
    
    def __init__(self, base_url: str = "http://localhost:5273/v1"):
        self.client = OpenAI(
            base_url=base_url,
            api_key="not-needed"
        )
        self.documents = []
        self.vectorizer = None
        self.doc_vectors = None
    
    def add_documents(self, documents: List[str]):
        """Add documents to the knowledge base"""
        self.documents.extend(documents)
        self._create_vectors()
    
    def _create_vectors(self):
        """Create TF-IDF vectors for documents"""
        if not self.documents:
            return
        
        self.vectorizer = TfidfVectorizer(
            max_features=1000,
            stop_words='english',
            ngram_range=(1, 2)
        )
        
        self.doc_vectors = self.vectorizer.fit_transform(self.documents)
    
    def retrieve_relevant_docs(self, query: str, top_k: int = 3) -> List[Dict[str, Any]]:
        """Retrieve most relevant documents for a query"""
        if not self.documents or self.vectorizer is None:
            return []
        
        # Vectorize query
        query_vector = self.vectorizer.transform([query])
        
        # Calculate similarities
        similarities = cosine_similarity(query_vector, self.doc_vectors).flatten()
        
        # Get top-k documents
        top_indices = np.argsort(similarities)[::-1][:top_k]
        
        results = []
        for idx in top_indices:
            if similarities[idx] > 0.1:  # Minimum similarity threshold
                results.append({
                    "content": self.documents[idx],
                    "similarity": float(similarities[idx]),
                    "index": int(idx)
                })
        
        return results
    
    def generate_answer(self, 
                       question: str, 
                       model: str = "phi-4-mini",
                       max_context_docs: int = 3) -> Dict[str, Any]:
        """Generate answer using retrieved documents"""
        
        # Retrieve relevant documents
        relevant_docs = self.retrieve_relevant_docs(question, max_context_docs)
        
        if not relevant_docs:
            context = "No relevant documents found in the knowledge base."
        else:
            context_parts = []
            for i, doc in enumerate(relevant_docs, 1):
                context_parts.append(f"Document {i} (relevance: {doc['similarity']:.3f}):\n{doc['content']}")
            context = "\n\n".join(context_parts)
        
        messages = [
            {
                "role": "system",
                "content": """
                You are a helpful AI assistant that answers questions based on provided documents.
                Use the context documents to provide accurate, detailed answers.
                If the documents don't contain sufficient information, say so clearly.
                Always cite which documents you're referencing in your answer.
                """.strip()
            },
            {
                "role": "user",
                "content": f"""
                Context Documents:
                {context}
                
                Question: {question}
                
                Please provide a comprehensive answer based on the context documents above.
                """.strip()
            }
        ]
        
        try:
            response = self.client.chat.completions.create(
                model=model,
                messages=messages,
                max_tokens=1000,
                temperature=0.3
            )
            
            return {
                "answer": response.choices[0].message.content,
                "model": response.model,
                "tokens": response.usage.total_tokens if response.usage else None,
                "retrieved_docs": len(relevant_docs),
                "context_length": len(context)
            }
            
        except Exception as e:
            return {"error": str(e)}

def create_sample_knowledge_base() -> List[str]:
    """Create a sample knowledge base about AI and technology"""
    
    documents = [
        """
        Microsoft Foundry Local is a comprehensive development platform that enables developers to run AI models locally on Windows devices.
        It provides hardware acceleration through DirectML and supports various model formats including ONNX.
        The platform includes a command-line interface for model management and an OpenAI-compatible API for seamless integration.
        """,
        
        """
        Edge AI refers to the deployment of artificial intelligence algorithms directly on edge devices, such as smartphones, IoT devices, and local computers.
        This approach reduces latency, improves privacy, and enables offline functionality.
        Edge AI is particularly important for real-time applications and scenarios where data privacy is critical.
        """,
        
        """
        Small Language Models (SLMs) are compressed versions of large language models that maintain much of their capabilities while requiring significantly fewer computational resources.
        Examples include Microsoft's Phi models, which can run efficiently on consumer hardware.
        SLMs are ideal for edge deployment and privacy-sensitive applications.
        """,
        
        """
        Vector databases store and retrieve data based on vector representations, enabling semantic search and similarity matching.
        They are essential components in RAG (Retrieval-Augmented Generation) systems, where relevant context is retrieved to enhance AI responses.
        Popular vector databases include Chroma, Pinecone, and Weaviate.
        """,
        
        """
        Prompt engineering is the practice of crafting effective prompts to guide AI model behavior and improve response quality.
        Techniques include few-shot learning, chain-of-thought prompting, and system message optimization.
        Well-designed prompts can significantly improve model performance on specific tasks.
        """,
        
        """
        Azure AI Foundry provides cloud-based AI development capabilities, including model training, deployment, and monitoring.
        It offers integration with Azure services and supports both custom and pre-trained models.
        The platform enables seamless scaling from local development to enterprise deployment.
        """
    ]
    
    return [doc.strip() for doc in documents]

def demo_document_rag():
    """Demonstrate document RAG capabilities"""
    
    # Create RAG system
    rag_system = SimpleRAGSystem()
    
    # Add sample knowledge base
    documents = create_sample_knowledge_base()
    rag_system.add_documents(documents)
    
    print(f"Loaded {len(documents)} documents into knowledge base")
    
    # Example questions
    questions = [
        "What is Microsoft Foundry Local and what are its key features?",
        "How do Small Language Models differ from regular language models?",
        "What is the role of vector databases in RAG systems?",
        "What are the benefits of Edge AI?",
        "How can I improve my prompt engineering skills?"
    ]
    
    for i, question in enumerate(questions, 1):
        print(f"\n{'='*70}")
        print(f"Question {i}: {question}")
        print(f"{'='*70}")
        
        result = rag_system.generate_answer(question)
        
        if "error" in result:
            print(f"Error: {result['error']}")
        else:
            print(f"Answer: {result['answer']}")
            print(f"Retrieved {result['retrieved_docs']} documents")
            print(f"Tokens used: {result['tokens']}")

if __name__ == "__main__":
    demo_document_rag()
```


### 4. Приказ пута миграције од CLI до Azure (5 минута)

#### Корак 4.1: Преглед стратегије миграције

Креирајте `samples/02-rag-solutions/migration_guide.py`:

```python
#!/usr/bin/env python3
"""
Foundry Local to Azure AI Foundry Migration Guide
Demo: Code patterns and migration strategies
Reference: https://learn.microsoft.com/en-us/azure/ai-foundry/foundry-local/reference/reference-sdk?pivots=programming-language-python
"""

import os
from openai import OpenAI
from typing import Dict, Any, Optional

class UnifiedAIClient:
    """Unified client that works with both Foundry Local and Azure AI Foundry"""
    
    def __init__(self, 
                 environment: str = "local",
                 azure_endpoint: Optional[str] = None,
                 azure_api_key: Optional[str] = None,
                 azure_api_version: str = "2024-08-01-preview"):
        
        self.environment = environment
        
        if environment == "local":
            # Foundry Local configuration
            self.client = OpenAI(
                base_url="http://localhost:5273/v1",
                api_key="not-needed"
            )
            self.default_model = "phi-4-mini"
            
        elif environment == "azure":
            # Azure AI Foundry configuration
            if not azure_endpoint or not azure_api_key:
                raise ValueError("Azure endpoint and API key required for Azure environment")
            
            self.client = OpenAI(
                base_url=f"{azure_endpoint}/openai/deployments",
                api_key=azure_api_key,
                default_headers={"api-version": azure_api_version}
            )
            self.default_model = "gpt-4"  # Or your Azure deployment name
            
        else:
            raise ValueError("Environment must be 'local' or 'azure'")
    
    def chat_completion(self, 
                       messages: list,
                       model: Optional[str] = None,
                       **kwargs) -> Dict[str, Any]:
        """Unified chat completion that works in both environments"""
        
        model = model or self.default_model
        
        try:
            response = self.client.chat.completions.create(
                model=model,
                messages=messages,
                **kwargs
            )
            
            return {
                "success": True,
                "response": response.choices[0].message.content,
                "model": response.model,
                "tokens": response.usage.total_tokens if response.usage else None,
                "environment": self.environment
            }
            
        except Exception as e:
            return {
                "success": False,
                "error": str(e),
                "environment": self.environment
            }
    
    def get_available_models(self) -> Dict[str, Any]:
        """Get available models in current environment"""
        
        try:
            if self.environment == "local":
                # For Foundry Local, we'd typically use the CLI
                # This is a simplified example
                return {
                    "success": True,
                    "models": ["phi-4-mini", "qwen2.5-0.5b", "deepseek-coder-1.3b"],
                    "environment": "local"
                }
            else:
                # For Azure, you might query the deployments endpoint
                models_response = self.client.models.list()
                return {
                    "success": True,
                    "models": [model.id for model in models_response.data],
                    "environment": "azure"
                }
                
        except Exception as e:
            return {
                "success": False,
                "error": str(e),
                "environment": self.environment
            }

def demo_migration_patterns():
    """Demonstrate migration patterns between local and cloud"""
    
    print("Foundry Local to Azure AI Foundry Migration Demo")
    print("=" * 60)
    
    # Test message
    test_messages = [
        {
            "role": "system",
            "content": "You are a helpful AI assistant. Provide concise, accurate responses."
        },
        {
            "role": "user",
            "content": "Explain the benefits of edge AI in 2-3 sentences."
        }
    ]
    
    # Test with Foundry Local
    print("\n1. Testing with Foundry Local:")
    print("-" * 40)
    
    try:
        local_client = UnifiedAIClient(environment="local")
        local_result = local_client.chat_completion(
            messages=test_messages,
            max_tokens=200,
            temperature=0.7
        )
        
        if local_result["success"]:
            print(f"✓ Local Response: {local_result['response']}")
            print(f"  Model: {local_result['model']}")
            print(f"  Tokens: {local_result['tokens']}")
        else:
            print(f"✗ Local Error: {local_result['error']}")
            
    except Exception as e:
        print(f"✗ Local Setup Error: {e}")
    
    # Show Azure configuration (commented out as it requires credentials)
    print("\n2. Azure AI Foundry Configuration:")
    print("-" * 40)
    print("""
    # To migrate to Azure AI Foundry, configure as follows:
    
    azure_client = UnifiedAIClient(
        environment="azure",
        azure_endpoint="https://your-resource.openai.azure.com",
        azure_api_key="your-api-key",
        azure_api_version="2024-08-01-preview"
    )
    
    # Same API calls work in both environments!
    azure_result = azure_client.chat_completion(
        messages=test_messages,
        max_tokens=200,
        temperature=0.7
    )
    """)
    
    # Migration strategy
    print("\n3. Migration Strategy:")
    print("-" * 40)
    print("""
    Step 1: Develop and test locally with Foundry Local
    Step 2: Use environment variables for configuration
    Step 3: Test with Azure AI Foundry in staging
    Step 4: Deploy to production with Azure AI Foundry
    
    Benefits of this approach:
    ✓ Faster development cycle (no network latency)
    ✓ Lower development costs (no API charges)
    ✓ Privacy during development (local processing)
    ✓ Easy scaling to production (same API)
    """)
    
    # Configuration examples
    print("\n4. Environment-based Configuration:")
    print("-" * 40)
    print("""
    # .env file for development
    AI_ENVIRONMENT=local
    FOUNDRY_LOCAL_URL=http://localhost:5273/v1
    DEFAULT_MODEL=phi-4-mini
    
    # .env file for production
    AI_ENVIRONMENT=azure
    AZURE_OPENAI_ENDPOINT=https://your-resource.openai.azure.com
    AZURE_OPENAI_API_KEY=your-api-key
    AZURE_OPENAI_API_VERSION=2024-08-01-preview
    DEFAULT_MODEL=gpt-4
    """)

if __name__ == "__main__":
    demo_migration_patterns()
```

#### Корак 4.2: Тестирајте обрасце миграције

```powershell
# Run the migration demo
python samples/02-rag-solutions/migration_guide.py
```


## Кључни концепти

### 1. Напредно креирање упутстава

- **Системска упутства**: Персоне експерата специфичне за домен
- **Стратегије утемељења**: Технике интеграције контекста
- **Контрола температуре**: Балансирање креативности и конзистентности
- **Управљање токенима**: Ефикасно коришћење контекста

### 2. Интеграција структурираних података

- **Обрада CSV-а**: Интеграција Pandas-а са AI моделима
- **Статистичка анализа**: Аутоматизовано сумирање података
- **Креирање контекста**: Динамичко генерисање контекста на основу упита
- **Подршка за више формата**: JSON, CSV и табеларни подаци

### 3. RAG обрасци имплементације

- **Векторска претрага**: TF-IDF и косинусна сличност
- **Проналажење докумената**: Оцењивање релевантности и рангирање
- **Комбинација контекста**: Синтеза више докумената
- **Генерисање одговора**: Креирање одговора заснованих на контексту

### 4. Стратегије миграције у облак

- **Уједињени API-ји**: Једна кодна база за локално и облак
- **Апстракција окружења**: Конфигурацијом вођено распоређивање
- **Развојни ток**: Локално → Тестирање → Продукција
- **Оптимизација трошкова**: Локални развој, продукција у облаку

## Разматрања за продукцију

### 1. Оптимизација перформанси

```python
# Optimize for production RAG
rag_config = {
    "max_context_docs": 5,
    "similarity_threshold": 0.15,
    "max_tokens": 1000,
    "temperature": 0.2,
    "chunk_size": 500,
    "chunk_overlap": 50
}
```

### 2. Руковање грешкама

```python
# Robust error handling
try:
    result = rag_system.generate_answer(question)
    if "error" in result:
        # Fallback to general knowledge
        fallback_result = client.chat.completions.create(
            model="phi-4-mini",
            messages=[{"role": "user", "content": question}]
        )
except Exception as e:
    # Log error and provide graceful degradation
    logger.error(f"RAG system error: {e}")
```

### 3. Надзор и посматрање

```python
# Track RAG performance
metrics = {
    "retrieval_time": time.time() - start_time,
    "context_relevance": avg_similarity_score,
    "token_usage": response.usage.total_tokens,
    "user_satisfaction": feedback_score
}
```


## Следећи кораци

Након завршетка ове сесије:

1. **Истражите Сесију 3**: Модели отвореног кода у Foundry Local
2. **Изградите продукцијски RAG**: Имплементирајте са Chainlit (Пример 04)
3. **Напредна векторска претрага**: Интегришите са Chroma или Pinecone
4. **Миграција у облак**: Распоредите на Azure AI Foundry
5. **Процените квалитет RAG-а**: Покрените `cd Workkshop/samples;python -m session02.rag_eval_ragas` за мерење релевантности одговора, веродостојности и прецизности контекста користећи ragas

### Опциона побољшања

| Категорија | Побољшање | Разлог | Упутство |
|------------|-----------|--------|----------|
| Проналажење | Замените TF-IDF са векторском базом (FAISS / Chroma) | Боља семантичка прецизност и скалабилност | Поделите документе (500–800 карактера), уградите, сачувајте индекс |
| Хибридни индекс | Двоструко семантичко + филтрирање кључних речи | Побољшава прецизност за нумеричке / кодне упите | Филтрирајте по кључној речи, затим рангирајте по косинусној сличности |
| Уградње | Процените више модела уградње | Оптимизујте релевантност у односу на брзину | A/B: MiniLM vs E5-small vs локално хостовани енкодер |
| Кеширање | Кеширајте уградње и резултате претраге | Смањите кашњење поновљених упита | Једноставно на диску pickle / sqlite са хеш кључем |
| Евалуација | Проширите ragas скуп података | Статистички значајан квалитет | Креирајте 50–100 Q/A + контексте; стратификујте по теми |
| Метрике | Пратите време претраге и генерисања | Профилисање перформанси | Снимите `retrieval_ms`, `gen_ms`, `tokens` по позиву |
| Заштитне мере | Додајте резервну опцију за халуцинације | Безбеднији одговори | Ако је веродостојност < праг → одговор: "Недовољан контекст." |
| Резервна опција | Каскадно локално → Azure модел | Побољшање хибридног квалитета | На ниској сигурности преусмерите на облак преко истог OpenAI API-ја |
| Детерминизам | Стабилна поређења | Поновљиви скупови евалуације | Фиксирајте seed, `temperature=0`, онемогућите случајност узорка |
| Надзор | Сачувајте историју евалуације | Детекција регресије | Додајте JSON линије са временском ознаком + променама метрика |

#### Пример: Додавање времена претраге

```python
import time
start_ret = time.time()
idxs = retrieve(query)
retrieval_ms = (time.time() - start_ret) * 1000
start_gen = time.time()
text, usage = chat_once(alias, messages=messages, max_tokens=250, temperature=0.2)
gen_ms = (time.time() - start_gen) * 1000
record = {"retrieval_ms": retrieval_ms, "gen_ms": gen_ms, "tokens": getattr(usage,'total_tokens',None)}
```


#### Скалирање евалуације са ragas

1. Саставите JSONL са пољима: `question`, `answer`, `contexts`, `ground_truths` (листа)
2. Конвертујте у `Dataset.from_list(list_of_dicts)`
3. Покрените `evaluate(dataset, metrics=[...])`
4. Сачувајте метрике (CSV/JSON) за анализу трендова.

#### Брзи почетак за векторску базу (FAISS)

```python
import faiss, numpy as np
index = faiss.IndexFlatIP(embeddings.shape[1])
index.add(embeddings)  # embeddings = np.array([...]) normalized
D, I = index.search(query_vec, k)
```

За перзистенцију на диску користите `faiss.write_index(index, "kb.index")`.

## Додатни ресурси

### Документација
- [Foundry Local Python SDK](https://learn.microsoft.com/en-us/azure/ai-foundry/foundry-local/reference/reference-sdk?pivots=programming-language-python)
- [Azure AI Foundry RAG Patterns](https://learn.microsoft.com/en-us/azure/ai-foundry/concepts/retrieval-augmented-generation)
- [Водич за креирање упутстава](https://learn.microsoft.com/en-us/azure/ai-services/openai/concepts/advanced-prompt-engineering)
- [Ragas документација за евалуацију](https://docs.ragas.io)

### Пример кода
- [Модул08 Пример 04](./samples/04/README.md) - Chainlit RAG апликација
- [Напредни систем са више агената](./samples/09/README.md) - Обрасци координације агената

---

**Трајање сесије**: 30 минута практично + 15 минута Q&A  
**Ниво тежине**: Средњи  
**Предуслови**: Завршена Сесија 1, Основно знање Python-а  

## Пример сценарија и мапирање радионице

| Скрипта радионице / Бележница | Сценарио | Циљ | Основни скуп података / Извор | Пример питања |
|------------------------------|----------|-----|-------------------------------|---------------|
| `samples/session02/rag_pipeline.py` / `notebooks/session02_rag_pipeline.ipynb` | Интерна база знања за подршку која одговара на питања о приватности + перформансама | Минимални RAG у меморији са уградњама | `DOCS` листа у скрипти (5 кратких пасуса) | Зашто користити RAG са локалним инференцијама? |
| `samples/session02/rag_eval_ragas.py` / `notebooks/session02_rag_eval_ragas.ipynb` | Аналитичар квалитета који успоставља основне метрике веродостојности претраге | Израчунати ragas метрике на малом синтетичком скупу података | `DOCS`, `QUESTIONS`, `GROUND_TRUTH` низови | Која је предност локалне инференције? |
| `prompt_engineering.py` (напредно) | SME за домен који креира утемељена упутства за више вертикала | Поређење системских упутстава за домен и утицај токена | Уграђени `contexts` речник | Како Foundry Local управља кеширањем модела? |
| `csv_qa_system.py` | Операције продаје које истражују интерактивну аналитику преко извоза | Сажети и упитати мали део продаје | Генерисани `sample_sales_data.csv` (10 редова) | Који производ има највећи просечан износ продаје? |
| `document_rag.py` | Тим за производе који истражује RAG за интерну вики | Проналажење + цитирање релевантних докумената | `create_sample_knowledge_base()` листа | Које су предности Edge AI? |
| `migration_guide.py` | Архитекта који припрема план миграције у облак | Демонстрирати паритет локалног→Azure API-ја | Статички тест упутства | Објасните предности Edge AI у 2–3 реченице. |

### Снипети скупа података
Листа докумената за RAG цевовод:
```python
DOCS = [
    "Foundry Local provides an OpenAI-compatible local inference endpoint.",
    "Retrieval Augmented Generation (RAG) improves answer grounding by injecting relevant context passages.",
    "Edge AI reduces latency and preserves privacy by executing models locally.",
    "Small Language Models can achieve competitive quality with reduced resource usage.",
    "Vector similarity search retrieves semantically relevant documents for a query.",
]
```

Истините вредности за евалуацију ragas:
```python
QUESTIONS = ["What advantage does local inference offer?", "How does RAG improve answer grounding?"]
GROUND_TRUTH = [
    "Local inference reduces latency and preserves privacy.",
    "RAG adds retrieved context snippets to improve factual grounding."
]
```


### Наратив сценарија
Група за подршку инжењеринга жели брзи прототип за одговарање на интерна питања без излагања података о клијентима екстерно. Артефакти из Сесије 2 напредују од минималног еферемалног RAG-а (без перзистенције) → структурирани CSV Q&A → проналажење докумената са цитирањем → објективна евалуација квалитета (ragas) → стратегија миграције спремна за Azure тестирање.

### Путеви проширења
Користите табелу Опционих побољшања за развој: замените TF‑IDF са FAISS/Chroma, проширите корпус за евалуацију (50–100 Q/A), додајте резервну ескалацију на већи модел када је веродостојност < праг.

---

**Одрицање од одговорности**:  
Овај документ је преведен помоћу услуге за превођење уз помоћ вештачке интелигенције [Co-op Translator](https://github.com/Azure/co-op-translator). Иако настојимо да обезбедимо тачност, молимо вас да имате у виду да аутоматски преводи могу садржати грешке или нетачности. Оригинални документ на његовом изворном језику треба сматрати ауторитативним извором. За критичне информације препоручује се професионални превод од стране људи. Не преузимамо одговорност за било каква погрешна тумачења или неспоразуме који могу настати услед коришћења овог превода.