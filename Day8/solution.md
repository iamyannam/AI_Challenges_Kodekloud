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

def generate_haiku(topic: str) -> str:
    parameterized_prompt = f"""
Generate a three-line-haikus about the specified topic, strictly following the 5-7-5 syllable structure.
{topic}
"""

    response = client.chat.completions.create(
        model="openai/gpt-4.1-mini",
        messages=[
            {"role": "user", "content": parameterized_prompt}
        ],
        max_tokens=60,
        temperature=0.0
    )

    return response.choices[0].message.content.strip()


topic = "sky"

response = generate_haiku(topic)

print(response)

```
3.  run the pyhton file - ```python3 openaiproject/resume_extractor.py```

<img width="1849" height="920" alt="image" src="https://github.com/user-attachments/assets/4148d143-88d2-4a13-925d-2ffb388268be" />


