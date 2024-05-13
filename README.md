Databrick's DBRX for real-time, without fine-tuning

Databricks DBRXWhat is DBRX?
DBRX is one of the State-of-the-art Language Model from Databricks. A language Model is a computer program that has been fed enough examples to be able to recognize and interpret human language or other types of complex data. Many LLMs are trained on data that has been gathered from the Internet - thousands or millions of gigabytes' worth of text
DBRX, an open, general-purpose LLM created by Databricks. Across a range of standard benchmarks, DBRX sets a new state-of-the-art for established open LLMs. 
DBRX advances the state-of-the-art in efficiency among open models, thanks to its fine-grained mixture-of-experts (MoE) architecture. Inference is up to 2x faster than LLaMA2–70B, and DBRX is about 40% of the size of Grok-1 in terms of both total and active parameter counts
DBRX is a large language model (LLM) that uses a fine-grained mixture-of-experts (MoE) architecture with 132 billion total parameters, of which 36 billion are active on any input. It's decoder-only and trained using next-token prediction on a massive dataset containing 12 trillion tokens of text and code data. Unlike similar models such as Mixtral and Grok-1, DBRX employs a fine-grained approach, utilizing 16 experts and selecting 4 of them, whereas the others have 8 experts and choose 2.
Traditional language models are limited in their ability to predict recent events or information outside their training data, making them less effective for queries about current topics. This limitation gave rise to the need for Retrieval-Augmented Generation (RAG) to supplement the generative capabilities of language models. By incorporating external sources, RAG enhances the accuracy and timeliness of responses, particularly for inquiries about recent events or topics beyond the model's training data.
Why DBRX?
Outperformance of Open Source Models: Databricks' DBRX model demonstrates superior performance compared to leading open source models like LLaMA2–70B, Mixtral, and Grok-1 across multiple domains such as language understanding, programming, math, and logic. This indicates Databricks' commitment to contributing to the improvement of open source model quality, a trend they are proud to support

Benchmark ComparisionAdvantage over Proprietary Models: DBRX surpasses GPT-3.5 on various benchmarks, aligning with a noticeable shift among Databricks' extensive customer base towards favoring open-source models over proprietary ones for enhanced efficiency and control. Databricks highlights the ability of customers to achieve better quality and speed by customizing open-source models to fit their specific needs, potentially accelerating the adoption of open-source models in enterprises and organizations.

DBRX outperforms GPT3.5 across language understanding (MMLU), Programming (HumanEval), and Math (GSM8K)Efficiency and Scalability with MoE Architecture: DBRX's Mixture-of-Experts (MoE) model architecture, developed on the MegaBlocks research and open-source project, ensures high speed in terms of tokens processed per second. Databricks believes this innovation will pave the way for future open-source models to adopt MoE structures, enabling the training of larger models while maintaining fast throughput. This scalability, with DBRX utilizing only 36 billion parameters at any given time out of its total 132 billion parameters, presents a balance between speed and performance, offering users an efficient solution.

Mixture of ExpertsKnowledge Window for Language Model!!!
The Knowledge Window for LLMs makes language models smarter by adding real-time information from outside sources. This helps them give more accurate and meaningful responses across different topics. RAG, or Retrieval-Augmented Generation, is a key part of this, helping them find and use the right information to improve their answers.

What is RAG (Retrieval-Augmented Generation)?
Traditional language models are limited in their ability to predict recent events or information outside their training data, making them less effective for queries about current topics. This limitation gave rise to the need for Retrieval-Augmented Generation
RAG, or retrieval-augmented generation, is a new way to understand and create language. It combines two kinds of models. First, retrieve relevant information. Second, generate text from that information. By using both together, RAG does an amazing job. Each model's strengths make up for the other's weaknesses. So, RAG stands out as a groundbreaking method in natural language processing.
RAG ArchitectureWhat is Vector Store?
Vector Store and Vector Search are essential components of modern information Retrieval systems.
Vector Store: It's like a database that stores data in a way that represents each piece of information as a vector - a mathematical representation in multi-dimensional space. This allows for efficient storage and retrieval of data based on similarity metrics rather than traditional indexing methods.
Vector Search: It's the process of finding relevant information by comparing similarities between vectors. Instead of keyword matching or other conventional search techniques, Vector Search identifies similar vectors in the Vector Store, returning results that are semantically related, even if they don't contain the exact query terms.
Hands-on RAG Demo:
I chose Databricks as my platform because it offers DBRX, a foundational model, along with tools and libraries tailored for end-to-end machine learning and deep learning workflows.
Code overview:
Importing the Chat model (DBRX) & embedding model from Databricks Foundational Models 

2. Importing GPT Tokenizer from Hugging Face
3. Creating a Class for Chat Assistant which take Tokenizer, Embedding, Docs & LLM as input to instantiate the class object:
get_pdf_text(): To extract the text from the Document Provided
Chunk_return(): takes in the text as input tokenizes & splits the huge text into chunks

get_vector_text(): To embed the chunks & index the embedded content using the FAISS index which returns the Vector Library 

get_conve_chain(): is the method to return the Conversation Q&A Chain along with Prompt Template & Language Model (DBRX)
query() : Method is used to call the LLM chain & Vector Library to feed it to the Language Model(DBRX)

Examples:
Querying the DBRX about RAG.

Querying the DBRX along with Knowledge Window

Conclusion:
DBRX, a top-notch language model by Databricks, is excellent at understanding language & Code. But when it comes to recent stuff, it struggles a bit. So, we use a technique called Retrieval-Augmented Generation (RAG) to help it out. This combine finding information with making new text, making DBRX even smarter. Implemented on Databricks, RAG with DBRX makes machine learning easier and more effective.
