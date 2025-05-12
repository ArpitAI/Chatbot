# Virtual Restaurant Assistant

## Overview

This project implements a virtual restaurant assistant capable of answering user queries based on information about a restaurant called "The Golden Spoon" located in Varanasi, Uttar Pradesh, India. It leverages the power of large language models (specifically Gemini) and a vector database (ChromaDB) to provide relevant and informative responses.

## Functionality

The assistant can understand and respond to various questions related to the restaurant, including:

* Basic information (address, contact details, website)
* Menu details and pricing for different cuisines (Indian, Chinese, Continental, South Indian, Italian)
* Availability of delivery services, associated charges, and delivery radius
* Reservation procedures and timings
* Information about food quality, service standards, and how to provide feedback
* Handling of dietary needs and allergies
* Details about ingredient sourcing and kitchen operations
* Efficiency measures and technology used in the restaurant
* Special offers, promotions, private events, and catering services
* Information about allergens, nutritional values (planned), and sustainability efforts
* Details about the restaurant staff and kitchen equipment

## Code Demonstration

The provided Python code demonstrates the core functionality of the virtual restaurant assistant:

1.  **Import Libraries:** Imports necessary libraries such as `pandas`, `numpy`, `sklearn` for potential future enhancements, `google-generativeai` for interacting with Gemini, and `chromadb` for the vector database.
2.  **Install Dependencies:** Uses `%pip install` to ensure the required libraries (`google-generativeai` and `chromadb`) are installed.
3.  **Configure Gemini API:** Authenticates and configures the Gemini API using a secret key obtained from Kaggle Secrets.
4.  **Load Restaurant Information:** Defines a list of strings (`documents`) where each string contains information about a specific aspect of "The Golden Spoon" restaurant.
5.  **Set up ChromaDB:**
    * Defines an embedding function (`GeminiEmbeddingFunction`) that uses the Gemini text embedding model to convert text into numerical vectors.
    * Initializes a ChromaDB client.
    * Creates or retrieves a ChromaDB collection named "googlerestaurentdb" using the defined embedding function.
    * Adds the restaurant information (`documents`) to the ChromaDB collection, assigning unique IDs to each document.
6.  **Query the Database:**
    * Sets the embedding function to query mode.
    * Defines a user query (e.g., "CAn you tell me menus").
    * Uses the ChromaDB `query` function to search the database for the most relevant information based on the query's vector representation.
    * Prints the most relevant passage retrieved from the database.

## Getting Started

To run this project, you will need:

1.  **Python 3.6 or higher** installed on your system.
2.  A **Google Cloud API key** with access to the Gemini API. You can obtain this from the Google Cloud Console.
3.  If running on Kaggle, you need to add your Google API key as a secret named "GOOGLE\_API\_KEY".
4.  Install the required Python libraries:
    ```bash
    pip install google-generativeai chromadb
    ```

## Usage

1.  Replace `"YOUR_GOOGLE_API_KEY"` in the code (if not using Kaggle Secrets) with your actual API key.
2.  Run the Python script.
3.  Modify the `query` variable to ask different questions about the restaurant.
4.  Observe the output, which will be the most relevant information retrieved from the ChromaDB based on your query.

## Potential Enhancements

* **More sophisticated natural language processing:** Integrate more advanced NLP techniques for better understanding of user queries.
* **Real-time data integration:** Connect to a live database for up-to-date menu information, availability, and promotions.
* **User interface:** Develop a web or mobile application for a more interactive user experience.
* **Multi-turn conversations:** Implement the ability to handle follow-up questions and maintain context.
* **Integration with other services:** Connect with online ordering platforms or reservation systems.
* **More comprehensive knowledge base:** Expand the information stored in the database to cover more aspects of the restaurant operations.
* **Sentiment analysis:** Analyze user feedback to identify areas for improvement.
