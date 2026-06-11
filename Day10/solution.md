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

def translate_to_language(text: str, language: str) -> str:
    prompt = f"""
Translate the following English text into {language}.

Text:
{text}

Return only the translated text.
""".strip()

    response = client.chat.completions.create(
        model="openai/gpt-4.1-mini",
        messages=[
            {"role": "user", "content": prompt}
        ],
        max_tokens=100,
        temperature=0.7
    )

    return response.choices[0].message.content.strip()


text = "Good morning, how are you?"

spanish_translation = translate_to_language(text, "Spanish")
french_translation = translate_to_language(text, "French")
telugu_translation = translate_to_language(text, "Telugu")
hindi_translation = translate_to_language(text, "Hindi")
tamil_translation = translate_to_language(text, "Tamil")
malayalam_translation = translate_to_language(text, "Malayalam")
kannada_translation = translate_to_language(text, "Kannada")
urdu_translation = translate_to_language(text, "Urdu")

print("Spanish:", spanish_translation)
print("French:", french_translation)
print("Telugu:", telugu_translation)
print("Hindi:", hindi_translation)
print("Tamil:", tamil_translation)
print("Malayalam:", malayalam_translation)
print("Kannada:", kannada_translation)
print("Urdu:", urdu_translation)


```
3.  run the pyhton file - ```python3 openaiproject/summarize.py```

<img width="1035" height="824" alt="image" src="https://github.com/user-attachments/assets/b6ccc069-70d6-4c0d-804c-12d18e838ff6" />




