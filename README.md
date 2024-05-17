# Book Recommendation Chatbot_RAG_LLM 


### [1.A book assistant chatbot using Python,embedding-based retrieval strategies, and GPT-2](https://github.com/kavyapan/RAG_Chatbot_LLM/blob/main/RAG_Chatbot_BookRecommendation.ipynb) 
This project is a simple book recommendation chatbot designed to provide users with personalized book recommendations based on their queries. The chatbot leverages a combination of Sentence Transformers for generating embeddings of book descriptions and GPT-2 for generating human-like conversational responses. Additionally, it uses FAISS (Facebook AI Similarity Search) for efficient similarity search and retrieval of book embeddings.

#### Explanation  
**1. Loading Book Data**: The book data is loaded from a JSON file (book.json), containing details such as the book's ID, title, author, publication date, genres, and description. For ease of use, the [book_summaries.txt](https://github.com/kavyapan/RAG_Chatbot_LLM/blob/main/book_summaries.txt) data downloaded from the [CMU Book Summary Corpus](https://www.kaggle.com/datasets/ymaricar/cmu-book-summary-dataset) is processed and saved into [book.json](https://github.com/kavyapan/RAG_Chatbot_LLM/blob/main/book.json)  
**2. Generating Embeddings**: The descriptions of the books are encoded into embeddings using the Sentence Transformers model(all-MiniLM-L6-v2)  
**3. Storing Embeddings in FAISS**: Embeddings are stored in a FAISS index for efficient similarity search.  
**4. Retrieving Books**: Books are retrieved based on the cosine similarity between the user's query embedding and the stored book embeddings.  
**5. Generating Responses**: GPT-2 is used to generate conversational responses based on the user query and context. It helps to generate natural language responses, enhancing user interaction.  
**6. Interactive Chatbot**: Offers an interactive interface for users to input their preferences and receive book recommendations.  
 

### 2. A book recommendation chatbot using Python, LangChain, embedding-based retrieval strategies, and GPT3.5
(WIP)

### 3. 

