# RAG_Chatbots_LLM 


### [1.A book assistant chatbot using Python,embedding-based retrieval strategies, and GPT-2](https://github.com/kavyapan/RAG_Chatbot_LLM/tree/main/RAG_BookRecommendation_Chatbot_GPT2) 
This project is a simple book recommendation chatbot designed to provide users with personalized book recommendations based on their queries. The chatbot leverages a combination of Sentence Transformers for generating embeddings of book descriptions and GPT-2 for generating human-like conversational responses. Additionally, it uses FAISS (Facebook AI Similarity Search) for efficient similarity search and retrieval of book embeddings.

#### Explanation  
**1. Loading Book Data**: The book data is loaded from a JSON file (book.json), containing details such as the book's ID, title, author, publication date, genres, and description. For ease of use, the [book_summaries.txt](https://github.com/kavyapan/RAG_Chatbot_LLM/blob/main/RAG_BookRecommendation_Chatbot_GPT2/book_summaries.txt) data downloaded from the [CMU Book Summary Corpus](https://www.kaggle.com/datasets/ymaricar/cmu-book-summary-dataset) is processed and saved into [book.json](https://github.com/kavyapan/RAG_Chatbot_LLM/blob/main/RAG_BookRecommendation_Chatbot_GPT2/book.json)  
**2. Generating Embeddings**: The descriptions of the books are encoded into embeddings using the Sentence Transformers model(all-MiniLM-L6-v2)  
**3. Storing Embeddings in FAISS**: Embeddings are stored in a FAISS index for efficient similarity search.  
**4. Retrieving Books**: Books are retrieved based on the cosine similarity between the user's query embedding and the stored book embeddings.  
**5. Generating Responses**: GPT-2 is used to generate conversational responses based on the user query and context. It helps to generate natural language responses, enhancing user interaction.  
**6. Interactive Chatbot**: Offers an interactive interface for users to input their preferences and receive book recommendations.  
 

### [2.Chat with multiple PDFs using LangChain,FAISS vector emebeddings, and Google Gemini](https://github.com/kavyapan/RAG_Chatbot_LLM/tree/main/RAG_PDF_Chatbot_Gemini)
In this Project the Streamlit app allows users to ask questions based on the content of uploaded PDF files and receive relevant answers. The app utilizes Gemini- Google's Generative AI model for text embeddings and conversational response generation. It also uses FAISS (Facebook AI Similarity Search) for efficient similarity search and retrieval of book embeddings.  

#### Explanation  
**1.Reading PDF Data**: The model reads the content from the uploaded PDF files.  
**2.Chunk Generation**:In natural language processing (NLP) tasks, it's often beneficial to break down large texts into smaller, more manageable chunks for processing. The create_chunks function in the provided code accomplishes this task. Here's how it works:  
*Text Splitting*: The function utilizes a RecursiveCharacterTextSplitter from the langchain.text_splitter module. This splitter divides the text into chunks based on a specified chunk size and overlap.  
*Chunk Size and Overlap*: The chunk_size parameter determines the maximum length of each chunk, ensuring that they are of manageable size for processing. The chunk_overlap parameter controls how much overlap there is between adjacent chunks, which can help ensure coherence when processing the text.  
*Iterative Splitting*: If the text is too long to fit into a single chunk, the splitter recursively splits it into smaller chunks until each chunk meets the specified size criteria.  
**3.Vector Store**:Once the text is divided into chunks, the next step is to generate embeddings for each chunk and store them efficiently for later retrieval. This is where the concept of a vector store comes into play. In the provided code, the create_vector_store function handles this task. Here's what it does:  
*Embedding Generation*: The function uses Google's Generative AI to generate embeddings for each text chunk. Embeddings are dense, numerical representations of text that capture its semantic meaning.  
*FAISS Integration*: The embeddings are then stored in a vector store using the FAISS library. FAISS (Facebook AI Similarity Search) is a library for efficient similarity search and clustering of dense vectors.  
*Efficient Retrieval*: Storing the embeddings in a vector store allows for fast and efficient retrieval based on similarity. This is crucial for quickly finding the most relevant chunks when answering user questions.  
**4.Gemini**: Gemini is a conversational AI model developed by Google that is specifically designed for natural language understanding and generation tasks. In the provided code, Gemini is used for generating responses to user questions based on the context provided by the text chunks. Here's how it fits into the workflow:  
*Conversational Chain*: The conversational_chain function sets up a conversational chain using the Gemini model. This chain takes as input the context (i.e., the text chunks) and the user's question and generates an appropriate response.  
*Prompt Template*: The function defines a template for prompting Gemini to generate a response. The template includes placeholders for the context and the user's question, which are filled in dynamically when generating responses.  
*Model Configuration*: Gemini is configured with specific parameters such as temperature, which controls the randomness of the generated responses. This parameter affects the diversity and creativity of the responses.  

#### How to Use  
**1.Upload PDF Files** : Click on the "Upload PDF Files" button in the sidebar and select one or multiple PDF files containing the content you want to query.  
**2.Ask Questions**: Once the PDF files are uploaded, type your question in the text input field labeled "Ask any Question from uploaded PDF Files".  
**3.Submit**: Click on the "Submit" button to process the question and retrieve the answer.  
![Chatbot Response](https://github.com/kavyapan/RAG_Chatbot_LLM/blob/main/RAG_PDF_Chatbot_Gemini/Chatbot_reponse1.JPG)
![Chatbot Response](https://github.com/kavyapan/RAG_Chatbot_LLM/blob/main/RAG_PDF_Chatbot_Gemini/Chatbot_reponse2.JPG)


#### Requirements
Before running the app, ensure you have the necessary modules and dependencies installed. You can install them using the following command:  
'pip install -r requirements.txt'  
Also in the .env file paste your Google API Key.


