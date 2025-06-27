## Technical Write-up

### Architecture and Tools Used

For this assignment, I developed a lightweight AI agent to assist with marketing research tasks, implemented as a FastAPI backend and prototyped in a Google Colab environment. The main features currently supported are:

- **Ad Performance Analysis:** The agent accepts CSV uploads of Meta/Google ad performance data and generates insights or suggestions for creative improvement.
- **Ad Text Rewriting:** It can rewrite user-uploaded ad text in a specified tone (such as fun, professional, etc.), leveraging the Gemini API for high-quality language generation.
- **Output Evaluation:** There is a simple evaluation endpoint that scores the generated output based on keyword matching against user-provided expectations.

**Key technologies and libraries used:**
- **FastAPI:** Provides the web backend and API endpoints.
- **Pandas:** Handles CSV parsing and data processing for ad analysis.
- **Google Generative AI (Gemini API):** Powers all text generation and analysis features.
- **Uvicorn & nest_asyncio:** Enable running the FastAPI server within the Colab notebook.
- **pyngrok:** Used to expose the local server to the internet for testing.

### Challenges Faced and Solutions

The main challenge was to keep the prototype simple and focused, while ensuring it demonstrates the core agentic capabilities required by the assignment. I initially considered integrating a knowledge graph for richer domain reasoning, but decided to keep the implementation lean for this first version. This allowed me to focus on reliable CSV handling, robust API integration with Gemini, and a user-friendly API interface.

Another challenge was evaluating the quality of generated outputs. For this, I implemented a basic keyword matching strategy, which, while limited, provides a quick way to assess whether the agent’s output aligns with user expectations.

### Potential Improvements and Next Steps

This is a foundational implementation, intended as a starting point for more advanced agentic workflows. To make the agent more impactful and intelligent, I plan to:

- **Integrate frameworks like LangChain or Agno:** These would allow for multi-step reasoning, memory, tool use, and more flexible agent behaviors.
- **Add Retrieval-Augmented Generation (RAG):** By connecting to a vector database (such as Chroma or Pinecone), the agent could search marketing blogs or documents and ground its responses in external knowledge, improving accuracy and relevance.
- **Enhance Evaluation:** I’d like to implement more sophisticated evaluation metrics, such as relevance scoring, hallucination detection, F1 score, and ROUGE, and support both automated and manual review.
- **Pattern Recognition and Feedback Loops:** In future iterations, I plan to add mechanisms for the agent to learn from user feedback, refine its prompts, and adapt over time using memory modules or feedback-based prompt engineering.

### Notes on Knowledge Graph and RAG

Currently, the agent does **not** use a knowledge graph or RAG workflow. However, the architecture is designed to be extensible: frameworks like LangChain or Agno could be incorporated in future versions to support these advanced features, enabling the agent to represent structured marketing knowledge and perform more complex, multi-step reasoning.

**In summary:**  
This prototype demonstrates the core requirements—a FastAPI backend with endpoints for ad analysis, rewriting, and evaluation—while providing a clear path for future expansion into more advanced agentic and retrieval-augmented workflows.

