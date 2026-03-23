## Context & Objective

* **Context:** This project was a key component of the "Digital Humanities Interdisciplinary Talent and Smart Leadership Program."

* **Problem:** Campus regulations are fundamental to protecting the rights of students and staff. However, traditional translations often suffer from inconsistent quality or slow updates, which can lead to international members being harmed by misunderstandings or conflicts.

* **Objective:** To create a system that combines advanced AI technologies with human-expert calibration to ensure the accuracy, professionalism, and timeliness of regulation translations, thereby improving convenience and protecting fundamental rights.

## System Architecture & Flow

The core highlight of this system is the combination of two advanced AI techniques, RAG and Auto-CoT, supplemented by a human review loop to ensure the rigorousness required for legal/regulatory texts.

<img width="14364" height="3024" alt="翻譯系統" src="https://github.com/user-attachments/assets/f70ecf61-2503-4238-9680-b7c85873f7f7" />

**System Workflow Explained:**

* **Input (Regulation Documents):** A user (e.g., a campus administrator) inputs or uploads the latest Chinese regulation documents.

* **RAG (Retrieval-Augmented Generation):**
    * The system first performs a vector search on the input document.
    * It retrieves the most relevant existing "Chinese regulation" and "English regulation" pairs from a "Bilingual Regulation Knowledge Base."
    * The purpose of this step is to provide the AI with crucial context and domain-specific terminology, mitigating the "hallucination" risk when translating proper nouns or legal terms.

* **Auto-CoT (Automatic Chain-of-Thoughts):**
    * The "Chinese-English samples" retrieved by RAG are fed into a separate Large Language Model (LLM).
    * This LLM's task is not to translate, but to "derive rules." It analyzes the samples to automatically deduce the "linguistic structure," "legal terminology style," and "syntactic norms" of the regulation documents.
    * This "chain-of-thought" process is like having the AI first learn to be a "legal translation expert."

* **Prompt Engineering:** The system dynamically combines the "original Chinese text," the "RAG-retrieved references," and the "Auto-CoT-derived structural rules" into a single, high-quality, information-rich prompt.

* **LLM (Translation):**
    * This high-quality prompt is sent to a second LLM, which performs the final translation.
    * With sufficient context and clear stylistic guidance, this model can generate a highly accurate and stylistically consistent English translation.

* **Human in the Loop (HITL) Feedback:**
    * The initial draft is submitted to human reviewers (e.g., humanities students, translation center experts).
    * These experts review and correct the text, with their "finalized results" fed back into the system.
    * This valuable feedback is used to optimize (fine-tune) the RAG knowledge base and the Auto-CoT model's rule derivation, allowing the system to get "smarter" over time.

* **Output (Final Translation):** The system outputs a verified, high-quality English regulation.

## My Role

As the primary developer on this project, I was responsible for the end-to-end technical implementation of this prototype. My key contributions include:

* **Prototype Development:** Built the functional proof-of-concept (PoC) from the ground up, translating the conceptual architecture into working code.

* **System Implementation:** Wrote the Python scripts for the complete data processing pipeline, managing document input, text processing, and API integrations.

* **AI Workflow Engineering:** Implemented the core AI logic, orchestrating the multi-step process for both the RAG (Retrieval-Augmented Generation) and Auto-CoT (Automatic Chain-of-Thoughts) components.

* **Testing & Validation:** Conducted tests on the system's output, making sure the system process and output correctly worked.

## Key Highlights

* **Humanity AI Driven:** The core goal is "protecting fundamental rights" and "promoting social equity," not just technology for its own sake.

* **Dual RAG + Auto-CoT Architecture:**
    * RAG solves the "knowledge" problem ("I know how to translate this specific term").
    * Auto-CoT solves the "style" problem ("I know how to write this sentence like a legal document").
    * This combination is specifically designed for high-stakes scenarios like legal/regulatory translation, which demand both accuracy and professionalism.

* **Expert Feedback Loop (HITL):** The system is designed with a clear optimization path, allowing it to continuously iterate and improve based on expert knowledge, ensuring long-term reliability.

## Technology Stack

* **Core Models:** LLMs (Ollama, GPT, Gemini)

* **Core Techniques:** RAG, Auto-CoT, Prompt Engineering

* **Database (Inferred):** Vector Database

## A Note on This Repository

Please note that this project was developed as part of a formal, collaborative academic program. Due to the nature of this partnership, the full source code is not publicly available. This repository serves as a professional portfolio piece to document and showcase the project's conceptual architecture, the AI workflow, and my role in its design.
