**quiz_generator.py**
```
from openai import OpenAI
import os

client = OpenAI(
    api_key=os.environ.get("OPENAI_API_KEY"),
    base_url=os.environ.get("OPENAI_API_BASE")
)


def generate_quiz(topic: str) -> str:
    system_message = """
You generate quizzes.

Return ONLY a valid JSON array containing exactly ONE object.

Schema:
[
  {
    "question": "Question text",
    "options": ["Option A", "Option B", "Option C", "Option D"],
    "answer": "Correct option text"
  }
]

Rules:
- Exactly one question.
- Exactly four options.
- The answer must exactly match one of the options.
- No markdown.
- Question must not be repeated when execute next time
- No explanations.
- Output only JSON.
"""

    user_message = f"""
Generate exactly one multiple-choice question about: {topic}.

The topic is related to the Linux operating system.

Return only the JSON array.
"""

    response = client.chat.completions.create(
        model="openai/gpt-4.1-mini",
        messages=[
            {"role": "system", "content": system_message},
            {"role": "user", "content": user_message}
        ],
        max_tokens=150,
        temperature=0.3,
    )

    return response.choices[0].message.content


if __name__ == "__main__":
    result = generate_quiz("Basic Linux Commands")
    print(result)

```
