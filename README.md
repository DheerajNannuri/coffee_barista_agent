# ☕ Coffee Barista Agent

An AI-powered coffee shop assistant that helps customers discover drinks and pastries based on their preferences.

The application uses **Google ADK**, **Gemini**, **Google Cloud Firestore Vector Search**, and **Streamlit** to provide menu-aware recommendations through a conversational interface.

## 🚀 Features

- 🤖 AI-powered coffee barista assistant
- ☕ Personalized drink and pastry recommendations
- 🔎 Semantic menu search using vector embeddings
- 🧠 Google Gemini-powered reasoning
- 🗄️ Google Cloud Firestore for menu storage and vector search
- 💬 Interactive Streamlit chat interface
- 🥛 Allergy-aware recommendations
- 🌱 Supports preferences such as dairy-free and vegan
- ❓ Asks clarifying questions when customer preferences are unclear
- 📋 Displays menu items, prices, tags, and allergens in the sidebar

## 🏗️ Architecture

```text
                    ┌─────────────────────┐
                    │      Customer       │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │   Streamlit UI     │
                    │      app.py         │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │   Google ADK Agent  │
                    │     agent.py        │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │   get_menu(query)   │
                    └──────────┬──────────┘
                               │
                    Generate Query Embedding
                               │
                               ▼
                    ┌─────────────────────┐
                    │  Gemini Embeddings  │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │ Google Cloud        │
                    │ Firestore           │
                    │ Vector Search       │
                    └──────────┬──────────┘
                               │
                         Top Menu Matches
                               │
                               ▼
                    ┌─────────────────────┐
                    │  Gemini Barista     │
                    │  Recommendation     │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │     Customer        │
                    │     Response        │
                    └─────────────────────┘
