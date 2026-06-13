**commit_generator.py**
```
from openai import OpenAI
import os


def generate_commit(changes: str) -> str:
    prompt = f"""
Analyze the following code changes summary.

Requirements:
- Choose the most appropriate commit type from: feat, fix, or docs.
- Generate a concise subject under 50 characters.
- Output only the commit message in the exact format:
<type>: <subject>

Changes:
{changes}
"""

    client = OpenAI(
        api_key=os.environ.get("OPENAI_API_KEY"),
        base_url=os.environ.get("OPENAI_BASE_URL"),
    )

    response = client.chat.completions.create(
        model="openai/gpt-4.1-mini",
        messages=[{"role": "user", "content": prompt}],
        max_tokens=30,
        temperature=0.0,
    )

    return response.choices[0].message.content.strip()


if __name__ == "__main__":
    changes = (
        "Added a new user registration endpoint and fixed a typo "
        "in the README file."
    )
    print(generate_commit(changes))
```


<img width="1004" height="729" alt="image" src="https://github.com/user-attachments/assets/f4eea734-d8e6-4724-961d-30c85abd1d1b" />
