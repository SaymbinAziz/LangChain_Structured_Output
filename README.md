# LangChain_Structured_Output

This project is part of my learning journey in Generative AI, where I explored how to get **structured outputs from LLMs** instead of plain text.

Usually, LLMs return free-form text, but in real applications we often need clean, structured data (like JSON) that can be directly used in code. This project helped me understand how to achieve that using different approaches in LangChain.

---

## 📌 What is Structured Output?

Structured output means getting responses from an LLM in a **predefined format** (like a dictionary or JSON) instead of unstructured paragraphs.

For example, instead of:

> “This phone has a great camera and battery…”

We get:

```json
{
  "summary": "...",
  "sentiment": "positive",
  "pros": [...],
  "cons": [...]
}
```

👉 This makes it much easier to use LLM outputs in real applications.

---

## 🧠 What I Explored

I experimented with three different ways to define structure:

### 1. TypedDict (Simple & Lightweight)

* Uses Python’s built-in typing
* Easy to define structure
* Less strict validation

### 2. Pydantic (Strict & Powerful)

* Strong validation (email, ranges, etc.)
* Supports defaults and descriptions
* Best for production-level use

### 3. JSON Schema (Flexible & Universal)

* Fully manual schema definition
* Works across different systems
* More control, but slightly verbose

---

## 📂 Project Structure

### 🔹 Concept Demo Files (Basics)

These files are just to understand the concepts:

* `typedict_demo.py` → Basic TypedDict example (Person schema)
* `pydantic_demo.py` → Pydantic model with validation (Student schema)
* `json_schema.json` → Simple JSON schema reference

👉 These helped me understand structure before applying it to LLMs.

---

### 🔹 Structured Output with LLMs

These files apply structured output on a real example (Samsung Galaxy S24 Ultra review):

* `with_structure_out_typedict.py`
  → Uses TypedDict with MistralAI

* `with_structure_out_pydantic.py`
  → Uses Pydantic BaseModel with validation

* `with_structure_out_json.py`
  → Uses raw JSON schema

* `with_structure_out_llama.py`
  → Uses HuggingFace (TinyLlama) instead of Mistral

👉 All of them extract:

* Summary
* Sentiment
* Pros & Cons
* Key themes
* Reviewer name (Ahmed Reza)

---

## ⚙️ Setup

1. Clone the repository

2. Install dependencies:

```bash id="g8k2an"
pip install -r requirements.txt
```

3. Create a `.env` file:

```env id="u7gk3p"
MISTRAL_API_KEY=your_api_key_here
HUGGINGFACEHUB_API_TOKEN=your_token_here
```

---

## ▶️ How to Run

Run any file individually:

```bash id="z9l2bc"
python typedict_demo.py
python pydantic_demo.py
python with_structure_out_typedict.py
python with_structure_out_pydantic.py
python with_structure_out_json.py
python with_structure_out_llama.py
```

---

## 📊 Expected Output

* **Demo files** → Simple structured Python objects
* **LLM files** → Clean structured data extracted from text

  * Summary
  * Sentiment (positive/negative)
  * Pros & Cons
  * Reviewer name

---

## 🤖 Models Used

* Mistral AI (API-based)
* HuggingFace (TinyLlama – local/open-source)

👉 This helped me understand that structured output works across different LLM providers.

---

## 💡 What I Learned

* How to convert unstructured text into structured data
* Difference between TypedDict, Pydantic, and JSON schema
* How validation improves reliability
* How structured outputs make LLMs usable in real applications
* How to switch between different LLM providers

This project gave me a clear understanding of how to make LLM outputs more practical and usable.

---

⭐ This is part of my journey in learning Generative AI and building real-world AI applications.
