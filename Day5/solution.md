1.  Create Virtual environment and activate and install AI
```
python3 -m venv venv && source venv/bin/activate && pip install openai
```
2. Update the converter.py as per the instructions is task.md file
```
import os
from openai import OpenAI

client = OpenAI(
    api_key=os.getenv("OPENAI_API_KEY"),
    base_url=os.getenv("OPENAI_API_BASE")
)

def convert_to_bullets(text: str) -> str:
    prompt = f"""
Converts a given paragraph into concise, easy-to-read bullet points.
{text}
"""

    response = client.chat.completions.create(
        model="openai/gpt-4.1-mini",
        messages=[
            {"role": "user", "content": prompt}
        ],
        max_tokens=150,
        temperature=0.1
    )

    return response.choices[0].message.content.strip()


text = "Artificial Intelligence is transforming industries by automating tasks, improving decision-making, and enabling new innovations across healthcare, finance, and education."

response = convert_to_bullets(text)


print(response)

```
3.  run the pyhton file - ```python3 openaiproject/convertor.py```

<img width="1912" height="974" alt="image" src="https://github.com/user-attachments/assets/49947c93-8241-4a5e-a909-fa2194628eca" />
