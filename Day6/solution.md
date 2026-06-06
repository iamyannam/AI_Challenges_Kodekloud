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

def rewrite_email(text: str) -> str:
    prompt = f"""
Rewrite the given email text prompt into polite and proffessional email text to send to client or stakeholders or also internal team members.
{text}
"""

    response = client.chat.completions.create(
        model="openai/gpt-4.1-mini",
        messages=[
            {"role": "user", "content": prompt}
        ],
        max_tokens=60,
        temperature=0.1
    )

    return response.choices[0].message.content.strip()


text = "hey send me that report asap"

response = rewrite_email(text)


print(response)

```
3.  run the pyhton file - ```python3 openaiproject/convertor.py```

<img width="1039" height="848" alt="image" src="https://github.com/user-attachments/assets/9b1fbb2e-e18d-4204-a51c-fce70b3ded04" />

