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

def summarize(text: str) -> str:
    prompt = f"""
Summerize the given paragraph into single-line summary in easy-to-understand manner.
{text}
"""

    response = client.chat.completions.create(
        model="openai/gpt-4.1-mini",
        messages=[
            {"role": "user", "content": prompt}
        ],
        max_tokens=60,
        temperature=0.5
    )

    return response.choices[0].message.content.strip()


text = "Artificial Intelligence enables machines to mimic human intelligence, performing tasks such as learning, problem-solving, and decision-making with increasing accuracy."

response = summarize(text)

print(response)

```
3.  run the pyhton file - ```python3 openaiproject/summarize.py```

<img width="1001" height="809" alt="image" src="https://github.com/user-attachments/assets/ae5ed53f-7a88-4f2e-9e1b-907cabeb2f54" />


