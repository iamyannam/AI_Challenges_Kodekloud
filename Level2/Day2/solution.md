**log_analyser.py**
```
from openai import OpenAI
import os


client = OpenAI(
    api_key=os.environ.get("OPENAI_API_KEY"),
    base_url=os.environ.get("OPENAI_API_BASE"),
)


def analyze_log_anomaly(log_file_path: str) -> str:
    with open(log_file_path, "r") as f:
        log_content = f.read()

    prompt = f"""
You are an auditor.

Focus ONLY on the [CRITICAL] log entry in the log content below.

Provide a concise two-part summary:
1. Error Type
2. Immediate Impact

Log Content:
{log_content}
"""

    response = client.chat.completions.create(
        model="openai/gpt-4.1-mini",
        messages=[
            {
                "role": "system",
                "content": (
                    "Act as an auditor. Focus ONLY on the [CRITICAL] line. "
                    "Provide a two-part summary: 1) The error type, "
                    "2) Immediate Impact."
                ),
            },
            {
                "role": "user",
                "content": prompt,
            },
        ],
        max_tokens=80,
        temperature=0.1,
    )

    return response.choices[0].message.content.strip()


if __name__ == "__main__":
    print(analyze_log_anomaly("/root/openaiproject/app.log"))

```

run -- 
```
python3 -m venv venv && source venv/bin/activate && pip install openai

python3 openaiporject/log_analyser.py
```
<img width="1786" height="968" alt="image" src="https://github.com/user-attachments/assets/401f7515-2430-43f2-9714-e9d5f3c4d974" />
