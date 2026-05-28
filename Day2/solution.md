chatbot.py
```

import os
from openai import OpenAI

# Initialize OpenAI client using environment variables
client = OpenAI(
 api_key=os.environ.get("OPENAI_API_KEY"),
 base_url=os.environ.get("OPENAI_API_BASE")
)

prompt = "You are a friendly travel guide. Greet the user and ask where they want to go."

nameresponse = client.chat.completions.create(
    model="openai/gpt-4.1-mini",
    messages=[
        {"role": "user", "content": prompt}
    ],
    temperature=0.7,
    max_tokens=100
)

print(nameresponse.choices[0].message.content)
```

.bash_profile
```
export ALLOWED_MODELS=openai/gpt-5-nano,google/gemini-2.5-flash-image-preview,openai/gpt-5-mini,deepseek/deepseek-chat,x-ai/grok-4.3,alibaba/qwen3-coder-plus,x-ai/grok-code-fast-1,openai/gpt-4.1-nano,openai/gpt-4.1-mini,deepseek/deepseek-reasoner,moonshotai/kimi-k2-0905,moonshot/kimi-k2-0711-preview,google/gemini-2.5-flash
export OPENAI_API_BASE=https://kodekey.ai.kodekloud.com/v1
export OPENAI_API_KEY=Sk-kkAI-8025f07cfbc0027618c27dba21e3c43f44edacdd2d854c198046405464c3de46kk_nubny5o4mixgllfc-kk323c7335

```
