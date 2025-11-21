# ⚡ Prompt Optimizer: Rule-Based Prompt Engineering Web App

A powerful **Django web application** that transforms raw, simple prompts into **well-structured, high-quality prompts** using advanced **rule-based prompt engineering techniques**. No external API calls are required—everything runs **locally**!


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

## 📁 Project Structure


prompt_optimizer/ ├── manage.py # Django management script ├── requirements.txt # Python dependencies ├── README.md # Project documentation ├── db.sqlite3 # SQLite database (generated) ├── prompt_optimizer/ # Main project directory │ ├── init.py │ ├── settings.py # Django settings │ ├── urls.py # URL routing │ ├── wsgi.py # WSGI configuration │ └── asgi.py # ASGI configuration └── optimizer/ # Main application ├── init.py ├── apps.py # App configuration ├── admin.py # Admin interface ├── models.py # Database models ├── views.py # View logic ├── urls.py # App URLs ├── prompt_engineering/ # Core optimization logic │ ├── init.py │ └── rules.py # PromptOptimizer class definition └── templates/ └── optimizer/ └── index.html # Main UI template


---

## 💡 How It Works

The Prompt Optimizer uses a **rule-based approach** implemented in the `PromptOptimizer` class found in `optimizer/prompt_engineering/rules.py`.

### Core Methods

The `optimize()` method orchestrates the following systematic transformation steps:

* `clean_text()`: Normalizes and removes extra whitespace.
* `add_role()`: Adds **role-based instructions** based on the target audience.
* `add_tone_instruction()`: Applies the selected **tone guidelines**.
* `structure_prompt()`: Clarifies and structures the main task instruction.
* `add_constraints()`: Adds output format and detail requirements.
* `add_output_requirements()`: Tailors content for specific audiences (e.g., "Make sure to tailor the content for a technical audience.").
* `add_examples()`: Incorporates **few-shot learning examples** if provided.

### Optimization Flow

1.  **Input:** User enters raw prompt and selects options in the UI.
2.  **Processing:** `PromptOptimizer` applies systematic, rule-based transformations.
3.  **Output:** A clean, structured, and professional optimized prompt is displayed.
4.  **Storage:** The input, options, and output are saved to the SQLite database.

---

## 🎮 Usage Example

| Category | Input | Selected Options |
| :--- | :--- | :--- |
| **Raw Prompt** | `explain machine learning` | |
| **Tone** | | Formal |
| **Format** | | List |
| **Detail** | | High |
| **Audience** | | Technical |

**Output (Optimized Prompt):**
---

## 🛠️ Configuration

### Django Settings

Key settings in `prompt_optimizer/settings.py`:

* `DEBUG`: **Set to `False` in production.**
* `SECRET_KEY`: **Change for production deployment.**
* `ALLOWED_HOSTS`: Add your domain names.

### Database

The default database is **SQLite** (`db.sqlite3`).

For production environments, consider using **PostgreSQL** or **MySQL**:

```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'prompt_optimizer_db',
        'USER': 'your_user',
        'PASSWORD': 'your_password',
        'HOST': 'localhost',
        'PORT': '5432',
    }
}

