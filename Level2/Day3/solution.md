**sentiment_analyser.py**
```
from openai import OpenAI
import os
import re

# Initialize OpenAI client
client = OpenAI(
    api_key=os.environ.get("OPENAI_API_KEY"),
    base_url=os.environ.get("OPENAI_API_BASE"),
)

def analyze_sentiment(text: str) -> str:
    prompt = f"""
Analyze the sentiment of the following text.

Text: "{text}"

Respond in exactly this format:
Sentiment: <Positive/Negative/Neutral>
Reason: <short explanation>
"""

    response = client.chat.completions.create(
        model="openai/gpt-4.1-mini",
        messages=[
            {"role": "user", "content": prompt}
        ],
        max_tokens=60,
        temperature=0.0
    )

    content = response.choices[0].message.content.strip()

    sentiment_match = re.search(r"Sentiment:\s*(Positive|Negative|Neutral)", content, re.IGNORECASE)
    reason_match = re.search(r"Reason:\s*(.*)", content, re.IGNORECASE)

    sentiment = sentiment_match.group(1).capitalize() if sentiment_match else "Neutral"
    reason = reason_match.group(1).strip() if reason_match else ""

    return f"Sentiment:{sentiment}\nReason:{reason}"


if __name__ == "__main__":
    text = "I am really happy with the new update!"
    result = analyze_sentiment(text)
    print(result)

```

run -- 
```
python3 -m venv venv && source venv/bin/activate && pip install openai

python3 openaiporject/sentiment_analyser.py
```

<img width="1736" height="833" alt="image" src="https://github.com/user-attachments/assets/2d8822a5-943d-41e4-961a-2ec4d0979bdf" />

