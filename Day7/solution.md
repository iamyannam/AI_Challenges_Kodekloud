1.  Create Virtual environment and activate and install AI
```
python3 -m venv venv && source venv/bin/activate && pip install openai
```
2. Update the email_assistant.py as per the instructions is task.md file
```
import os
from openai import OpenAI

client = OpenAI(
    api_key=os.getenv("OPENAI_API_KEY"),
    base_url=os.getenv("OPENAI_API_BASE")
)

def extract_keywords(text: str) -> str:
    prompt = f"""
Extract information to exactly 5 comma-seperated keywords from the provided resume text.
{text}
"""

    response = client.chat.completions.create(
        model="openai/gpt-4.1-mini",
        messages=[
            {"role": "user", "content": prompt}
        ],
        max_tokens=40,
        temperature=0
    )

    return response.choices[0].message.content.strip()


text = "Experienced DevOps engineer skilled in Python, Kubernetes, Docker, CI/CD pipelines, and cloud automation."

response = extract_keywords(text)

print(response)
```
3.  run the pyhton file - ```python3 openaiproject/resume_extractor.py```

<img width="1880" height="957" alt="image" src="https://github.com/user-attachments/assets/53cfa33e-8be1-4bd1-a1b8-5379ca6be42e" />

