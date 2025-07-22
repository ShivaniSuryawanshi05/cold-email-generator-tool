📧 Cold Email Generator Tool
This tool generates highly personalized cold outreach emails based on job descriptions scraped from company career pages. It uses Llama 3 via Groq Cloud, LangChain, and ChromaDB to match job descriptions with your company’s portfolio and craft targeted, compelling cold emails.

🔍 Overview
Extracts job postings from a company’s career page using LLMs (Llama 3).

Structures extracted data into a clean JSON format.

Matches relevant portfolio items from your internal project database.

Generates customized cold emails tailored to the role and required skills.

Built with Streamlit for an easy-to-use UI.

🔄 How It Works

1️⃣ Extract Careers Page Content

LangChain orchestrates Llama 3 via Groq Cloud to extract structured job descriptions from text.

2️⃣ Store in Vector Database (ChromaDB)

Structured job data stored in ChromaDB for fast, similarity-based retrieval.

3️⃣ Portfolio Matching

Internal projects (my_portfolio.csv) matched against the client's job descriptions.

4️⃣ LLM-Driven Email Generation

Matched context and prompts sent to Llama 3 via Groq Cloud for generating personalized cold emails.


🧱 System Design

Components
✅ chains.py – Core Email Generation Engine
extract_jobs(cleaned_text):
Uses LangChain + Llama 3 to extract job postings and return them as structured JSON with role, experience, skills, and description.

write_mail(job, links):
Generates a cold email personalized for a given job description and list of portfolio links.

✅ portfolio.py – Portfolio Matching
load_portfolio():
Loads company projects/solutions from a CSV file (my_portfolio.csv).

query_links(skills, top_k=3):
Matches job-required skills with relevant portfolio links using basic keyword matching.

✅ utils.py – Text Cleaning
clean_text(text):
Cleans scraped job page content by removing HTML, URLs, special characters, and excess whitespace.

✅ main.py – Streamlit App
Web UI for inputting a job posting URL.

Loads job content → cleans it → extracts jobs → matches projects → generates email.

Displays cold emails as markdown in the browser.

🧰 Tech Stack

Tool/Library	          Purpose

LangChain	              Framework to build LLM chains

Llama 3 via Groq	      LLM model for text generation

ChromaDB	              Vector storage (planned integration)

Streamlit             	Web UI

Python 3.11	            Core language


🧪 Setup Instructions

1. Clone the repository
2. Install dependencies
3. Create .env file with API key
GROQ_API_KEY=your_groq_api_key

🚀 How to Run
🔹 Streamlit App (Recommended)
cd app
streamlit run main.py

📂 File Structure
bash
Copy
Edit
cold-email-generator-tool/
├── app/
│   ├── main.py             # Streamlit UI
│   ├── chains.py           # LLM-based job extraction and email generation
│   ├── portfolio.py        # Loads and queries portfolio data
│   ├── utils.py            # Cleans scraped text
│   └── resource/
│       └── my_portfolio.csv  # Your company project links
├── vectorstore/            # (Optional) Vector DB for semantic search
├── .env                    # Environment variables
├── requirements.txt

📌 Example Output
Input: Job description scraped from Nike careers page.
Output:
Subject: Helping Nike Scale Engineering Teams Efficiently

Hi [CTO's Name],

As a Business Development Executive at XYZ, I wanted to share how we've helped companies solve challenges similar to what you're hiring for...




📈 Future Enhancements

CRM Integrations (HubSpot, Salesforce)

Tone customization (Formal / Casual / Neutral)

Multi-language support

