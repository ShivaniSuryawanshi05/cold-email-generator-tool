## 🧪 Setup Instructions

### 1. Clone the Repository

### 2. Install Dependencies

```bash
pip install 
```

### 3. Create a `.env` File

Create a `.env` file in the root directory and add your **Groq API key**:

```env
GROQ_API_KEY=your_groq_api_key
```

---

## 🚀 How to Run

### 🔹 Streamlit App (Recommended)

Launch the Streamlit UI from the `app/` directory:

```bash
cd app
streamlit run main.py
```

---

## 📂 File Structure

```
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
```

---

## 📌 Example Output

**Input:** Job description scraped from Nike careers page.  
**Output:**

```markdown
Subject: Helping Nike Scale Engineering Teams Efficiently

Hi [CTO's Name],

As a Business Development Executive at XYZ, I wanted to share how we've helped companies solve challenges similar to what you're hiring for...
```

---

## 📈 Future Enhancements

- 🔄 CRM Integrations (e.g., HubSpot, Salesforce)  
- 🗣️ Tone customization (Formal / Casual / Neutral)  
- 🌐 Multi-language support  
- 💬 Email preview and export options  


