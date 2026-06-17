**tag_generator.py**

```
import os
from openai import OpenAI

client = OpenAI(
    api_key=os.environ.get("OPENAI_API_KEY"),
    base_url=os.environ.get("OPENAI_API_BASE")
)

def generate_seo(description: str, tone: str) -> str:
    prompt = f"""
Generate SEO content for the product below.

Description: {description}
Tone: {tone}

Requirements:
- Generate a short attention-grabbing product title (4-8 words) in the specified tone.
- Generate exactly 10 low-competition SEO keywords.
- Output exactly two lines and nothing else.
- Line 1: title only.
- Line 2: exactly 10 comma-separated keywords with no spaces around commas.
"""

    response = client.chat.completions.create(
        model="openai/gpt-4.1-mini",
        messages=[
            {"role": "user", "content": prompt}
        ],
        max_tokens=60,
        temperature=0.7,
    )

    return response.choices[0].message.content.strip()


if __name__ == "__main__":
    result = generate_seo(
        "A waterproof, lightweight backpack designed for multi-day hikes in difficult terrain.",
        "Rugged and Adventurous",
    )
    print(result)
```


<img width="1029" height="844" alt="image" src="https://github.com/user-attachments/assets/4a2cd1d2-bdc5-4f35-a8ed-614a2e3183f3" />
