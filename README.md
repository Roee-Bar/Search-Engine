# Vercel Search Engine with Web Crawler

A comprehensive search engine and analytics platform for analyzing content from the Vercel website. The system features a web crawler that collects and analyzes text from Vercel.com, providing insights into term frequency, content patterns, and offering a powerful search functionality.

## Project Overview

This search engine project implements a complete full-stack solution:
- Backend web crawler that analyzes Vercel.com content
- Firebase database for data storage
- Frontend interface with search capabilities and analytics
- Admin functionality for data management
- AI chatbot integration (using Google's Gemini model)

## Key Features

- **Web Crawler**: Intelligent web crawler that analyzes text content from Vercel.com
- **Search Functionality**: Powerful search capability with result ranking based on relevance score
- **Data Visualization**: Statistical insights with interactive graphs
- **User Authentication**: Different permission levels for regular users and administrators
- **Admin Controls**: Management interface for modifying and deleting data
- **AI Assistant Integration**: Chatbot integration using Google's Gemini model
- **Microservices Architecture**: Backend implemented as separate, modular services

## Technology Stack

### Backend
- Python
- BeautifulSoup for web scraping
- NLTK for natural language processing
- Firebase for database storage
- Microservices architecture

### Frontend
- HTML/CSS
- JavaScript
- Matplotlib and Seaborn for data visualization
- Google Generative AI for chatbot functionality

## System Architecture

The system is built around a microservices architecture with the following components:

### Microservices
1. **Upload Object Service**: Manages the storage and uploading of processed data to Firebase
2. **Dictionary Creation Service**: Creates dictionaries of words and their relevance scores
3. **Pre-process Service**: Cleans and processes raw text from web pages
4. **Post-process Service**: Adds metadata and statistics to processed data

For a visual representation of the system architecture, see the diagram in `HW4_Tiger.docx`.

## Implementation Details

### Backend

The backend consists of a web crawler and several microservices that work together to collect, process, and store data:

#### Web Crawler
The crawler starts from Vercel's homepage and navigates through links, respecting `robots.txt` rules. It processes each page's text content and builds a database of terms with their frequency, location, and relevance.

#### Text Processing Algorithm
The system uses a sophisticated ranking algorithm for terms:
```python
# Position-based scoring
position_score = 1 - (index / total_words)
```

This algorithm weights terms appearing earlier in a document higher than those appearing later, while also considering frequency of appearance.

#### Data Storage
Processed data is stored in Firebase with the following structure:
- Terms as primary keys
- Each term contains links, count, and score information
- Metadata for statistics and analytics

### Frontend

The frontend provides several interfaces:

1. **Login Page**: Authentication for different user roles
2. **Dashboard**: Central navigation hub
3. **Search Page**: Search functionality and AI chatbot
4. **Statistics Page**: Visual analytics of term frequency and distribution

For screenshots and detailed UI descriptions, refer to the `User_book.docx` file.

## KPI Performance

The system meets three key performance indicators:
1. **User Experience**: Minimalist, organized, and easy-to-use interface
2. **Performance**: Data retrieval occurs in 700-900ms
3. **Security**: Access control with protected admin functionality

## Setup and Installation

The project can be run either locally or through Google Colab:

### Google Colab
1. Access the project via this link:
   https://colab.research.google.com/drive/1FIctTIYxFi1hUt1UKq2afl7wPgEtWITm

2. Run all cells in the notebook

### Local Installation

1. Clone the repository:
   ```
   git clone https://github.com/goodpvp90/CloudComputing
   ```

2. Install required dependencies:
   ```
   pip install requests beautifulsoup4 nltk firebase-admin matplotlib seaborn pandas google-generativeai
   ```

3. Run the `TigerVercel_Final_Project.ipynb` notebook

## Usage

### Authentication
- **Admin Access**: 
  - Username: `admin`
  - Password: `admin`
- **User Access**: 
  - Username: `user`
  - Password: `user`

### Search Functionality
1. Log in with credentials
2. Navigate to the search page
3. Enter search terms
4. View ranked results
5. Admin users can modify or delete entries

### Analytics
1. Access the Statistics page from the dashboard
2. View visualizations of:
   - Top 10 most frequent terms
   - Action vs. Restriction term distribution
   - Average term appearance frequency

### AI Chatbot
1. Navigate to the search page
2. Enter questions in the AI input field
3. Receive responses generated by Google's Gemini model

## Future Improvements

Based on user feedback and development plans:
- Improved UI consistency and button styling
- Extended microservices for frontend components
- Enhanced search algorithm for multi-term queries
- Expanded visualization capabilities

## Project Documentation

For more detailed information, please refer to:
- `HW4_Tiger.docx` - Overview and project requirements
- `Programmer_book.docx` - Technical documentation for developers
- `User_book.docx` - User manual with screenshots and usage instructions

## Team

This project was developed by Team Tiger for the Cloud Computing course.