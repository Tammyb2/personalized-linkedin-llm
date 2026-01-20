LinkedIn Post Generator 🚀
An AI-powered tool that generates LinkedIn posts in your personal writing style using Few-Shot Learning. By analyzing your past successful posts, the system mimics your tone, length preference, and language (English or Hinglish).

✨ Features
Style Mimicry: Uses Few-Shot prompting to ensure the AI writes like you.

Topic Filtering: Automatically categorizes your past posts by tags (e.g., Job Search, Motivation).

Multi-lingual Support: Supports both English and "Hinglish" (Hindi + English mix).

Metadata Extraction: Automatically counts lines and identifies languages from raw text using Llama 3.

🛠️ Tech Stack
LLM: Groq (Llama 3.3 70B)

Framework: LangChain

Frontend: Streamlit

Data Handling: Pandas

Environment & Dependency Management: uv

🚀 Getting Started
1. Prerequisites
Ensure you have uv installed. If not, install it via:

Bash

curl -LsSf https://astral.sh/uv/install.sh | sh
2. Set Up Environment Variables
Create a .env file in the root directory and add your Groq API Key:

Code snippet

GROQ_API_KEY=your_api_key_here
3. Install Dependencies
Bash

uv sync
4. Run the Application
Bash

uv run streamlit run main.py
🏗️ Project Structure
preprocess.py: Cleans raw JSON data, extracts metadata (tags/language), and unifies topics.

few_shots.py: Manages the collection of past posts and filters them based on user selection.

post_generator.py: Constructs the final prompt by injecting the retrieved "few-shot" examples into the LLM instructions.

llm_helper.py: Configures the connection to the Groq Cloud API.

📊 Data Pipeline
Raw Posts: Input your past posts in data/raw_posts.json.

Enrichment: Run preprocess.py to generate processed_posts.json which includes line counts and unified tags.

Selection: Choose your topic and length in the Streamlit UI.

Generation: The system finds 2-3 similar posts from your history and sends them to Llama 3 as examples to generate the new post.
