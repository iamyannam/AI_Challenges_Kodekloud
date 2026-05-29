compare.py file ---
```

import os
from openai import OpenAI

client = OpenAI(
    api_key=os.getenv("OPENAI_API_KEY"),
    base_url=os.getenv("OPENAI_API_BASE")
)

def compare(item1: str, item2: str) -> str:
    prompt = f"""
Compare the iPhone models "{item1}" and "{item2}" only in terms of the chip used.
Include details for "{item1}" in one line only.
"""

    response = client.chat.completions.create(
        model="openai/gpt-4.1-mini",
        messages=[
            {"role": "user", "content": prompt}
        ],
        max_tokens=100,
        temperature=0.5
    )

    return response.choices[0].message.content.strip()


item1 = "iphone 13"
item2 = "iphone 17"

response = compare(item1, item2)


print(response)
```
run the following commands
```python3 -m venv venv && source venv/bin/activate && pip install openai```

```python compare.py```

output file -

<img width="1768" height="814" alt="image" src="https://github.com/user-attachments/assets/9f30a519-5280-4cfa-807e-1937a7288c90" />

