# Learning Path Generator with Model Context Protocol (MCP)

This project is a Streamlit-based web application that generates personalized learning paths using the Model Context Protocol (MCP). It integrates with various services including YouTube, Google Drive, and Notion to create comprehensive learning experiences.

## Features

- 🎯 Generate personalized learning paths based on your goals
- 🎥 Integration with YouTube for video content
- 📁 Google Drive integration for document storage
- 📝 Notion integration for note-taking and organization
- 🚀 Real-time progress tracking
- 🎨 User-friendly Streamlit interface

## Prerequisites

- Python 3.10+
- Google ai Studio API Key
- Pipedream URLs for integrations (YouTube and either Drive or Notion)

## Installation

1. Clone the repository:

2. Create and activate a virtual environment:

3. Install the required packages:
```bash
pip install -r requirements.txt
```

## Configuration

Before running the application, you'll need to set up:

1. Google API Key
2. Pipedream URLs for:
   - YouTube (required)
   - Google Drive or Notion (based on your preference)

## Running the Application

To start the application, run:
```bash
streamlit run app.py
```

The application will be available at `http://localhost:8501` by default.

## Usage

1. Enter your Google ai studio API key and Pipedream URLs in the sidebar
2. Select your preferred secondary tool (Drive or Notion)
3. Enter your learning goal (e.g., "I want to learn python basics in 3 days")
4. Click "Generate Learning Path" to create your personalized learning plan

## Project Structure

- `app.py` - Main Streamlit application
- `utils.py` - Utility functions and helper methods
- `prompt.py` - Prompt template
- `requirements.txt` - Project dependencies


Here’s a comprehensive breakdown of your project, how to explain it in an interview, and how to discuss the models and technologies used:

---

## 1. **Project Overview**

**Name:**  
Model Context Protocol (MCP) - Learning Path Generator

**Purpose:**  
This is a Streamlit-based web application that generates a personalized learning path for users based on their learning goals. It leverages YouTube content and integrates with either Google Drive or Notion to organize the learning materials.

---

## 2. **How the Project Works**

### **User Flow:**
1. **Configuration:**  
   - User enters their Google API key.
   - User provides a Pipedream YouTube URL (required).
   - User selects a secondary tool (Google Drive or Notion) and provides the corresponding Pipedream URL.

2. **Goal Input:**  
   - User enters a learning goal (e.g., "Learn Python basics in 3 days").

3. **Generation:**  
   - User clicks "Generate Learning Path".
   - The app uses the provided APIs and URLs to fetch relevant YouTube content and organizes it into a structured learning path.
   - The learning path is then optionally integrated into Google Drive or Notion, based on the user's choice.

4. **Progress Tracking:**  
   - The app visually tracks the progress of the learning path generation process.

5. **Result Display:**  
   - The generated learning path is displayed to the user.

---

## 3. **Key Technologies and Models Used**

### **Frontend:**
- **Streamlit:**  
  For building the interactive web UI.

### **Backend/Logic:**
- **Python:**  
  Main programming language.
- **Custom Utility (`run_agent_sync`):**  
  Handles the core logic of fetching YouTube content, generating the learning path, and integrating with Drive/Notion.
- **Pipedream:**  
  Used as a middleware to connect with YouTube, Google Drive, and Notion APIs.

### **APIs:**
- **Google API:**  
  For authentication and possibly for Drive integration.
- **YouTube API (via Pipedream):**  
  To fetch relevant video content.
- **Google Drive API (via Pipedream):**  
  To store or organize the learning path.
- **Notion API (via Pipedream):**  
  To store or organize the learning path in Notion.

### **AI/ML Models:**
- **LLM (Large Language Model):**  
  The actual model used for generating the learning path is likely an LLM (such as OpenAI’s GPT or similar), though the specific model is abstracted behind the `run_agent_sync` function.  
  - **How to explain:**  
    "We use a large language model to analyze the user’s learning goal and generate a structured, step-by-step learning path using curated YouTube content. The model understands the goal, breaks it down into topics, and sequences the content for optimal learning."

---

## 4. **How to Answer Interview Questions**

### **a. What does this project do?**
> "This project generates a personalized learning path for any topic the user wants to learn, using YouTube videos as the primary resource. It also integrates with Google Drive or Notion to organize the learning materials, making it easy for users to follow and track their progress."

### **b. What technologies did you use?**
> "The frontend is built with Streamlit for rapid prototyping and interactive UI. The backend logic is in Python, and we use Pipedream to connect with YouTube, Google Drive, and Notion APIs. The core of the learning path generation uses a large language model to understand the user’s goal and curate content accordingly."

### **c. How does the AI/ML part work?**
> "When a user enters a learning goal, the app sends this to a large language model, which breaks down the goal into subtopics and finds relevant YouTube videos for each. The model sequences these into a logical learning path, which is then presented to the user and optionally saved to Drive or Notion."

### **d. How do you handle API integrations?**
> "We use Pipedream as a middleware to simplify API integrations with YouTube, Google Drive, and Notion. This allows us to securely and efficiently fetch and store data without handling all the authentication and API logic directly in our app."

### **e. How would you improve this project?**
> - Add user authentication for saving progress.
> - Support more content sources (e.g., blogs, MOOCs).
> - Add quizzes or interactive checkpoints.
> - Use more advanced AI models for better content curation.

---

## 5. **How to Show the Models Used in the Interview**

- **Show the Code:**  
  Open `app.py` and `utils.py` to show how the `run_agent_sync` function is called and how it interacts with the LLM and APIs.
- **Explain the Flow:**  
  Use the UI to demonstrate entering a goal, configuring APIs, and generating a path.
- **Highlight the LLM Usage:**  
  Point out where the user’s input is sent to the language model and how the results are processed and displayed.
- **Show API Integration:**  
  Demonstrate how Pipedream URLs are used to connect to YouTube, Drive, and Notion.

---


## 6. **Summary Statement**

> "In summary, this project is a smart learning path generator that leverages AI and cloud integrations to help users learn any topic efficiently using curated YouTube content, with seamless organization in Google Drive or Notion. It demonstrates skills in Python, Streamlit, API integration, and practical use of large language models."

