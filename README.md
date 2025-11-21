# ⚡ Prompt Optimizer: Rule-Based Prompt Engineering Web App

A powerful **Django web application** that transforms raw, simple prompts into **well-structured, high-quality prompts** using advanced **rule-based prompt engineering techniques**. No external API calls are required—everything runs **locally**!

![image alt](https://github.com/DATTA1804/Make-ai-agents/blob/fd73b52edc25b3fff5583a0b1881c33bb35791f0/Screenshot%202025-11-14%20152625.png)
---

## 🎯 Features

* **🎨 Beautiful Dark UI:** Modern **Tailwind CSS dark theme** with a responsive design.
* **⚡ Rule-Based Optimization:** Transform prompts using an intelligent, local `PromptOptimizer` class with predefined engineering rules.
* **🔧 Customizable Options:** Fine-tune optimization with selectable options:
    * **Tone:** Formal, Friendly, Technical, Neutral
    * **Output Format:** Paragraph, List, Steps, Summary, Detailed
    * **Detail Levels:** Low, Medium, High
    * **Target Audience:** General, Technical, Business, Creative, Educational
    * **Few-shot Examples:** Support for including few-shot learning examples.
* **💾 History Tracking:** An **SQLite database** stores all optimization history for easy review.
* **📋 One-Click Copy:** Copy optimized prompts to the clipboard instantly.
* **🔍 Admin Interface:** Django admin panel for managing and reviewing prompt history.

---

## 🚀 Quick Start

### Prerequisites

* Python 3.8 or higher
* `pip` (Python package manager)

### Installation

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/yourusername/prompt-optimizer.git](https://github.com/yourusername/prompt-optimizer.git)
    cd prompt-optimizer
    ```

2.  **Create virtual environment:**
    ```bash
    python -m venv venv
    # On Windows
    venv\Scripts\activate
    # On macOS/Linux
    source venv/bin/activate
    ```

3.  **Install dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

4.  **Run migrations:**
    ```bash
    python manage.py makemigrations
    python manage.py migrate
    ```

5.  **Create superuser (optional):**
    ```bash
    python manage.py createsuperuser
    ```

6.  **Start the development server:**
    ```bash
    python manage.py runserver
    ```

7.  **Open your browser:**
    ```
    [http://127.0.0.1:8000/](http://127.0.0.1:8000/)
    ```

---

## 📁 Project Structure
