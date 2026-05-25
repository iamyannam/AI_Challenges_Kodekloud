The nautilus AI Engineering team is developing tools to improve the clarity of developer-reported bugs. Developers often report issues informally, which makes them difficult to understand or reproduce.

You are tasked to build a Python-based AI Bug Description Clarifier that transforms such informal bug reports into clear, structured, and professional issue summaries.

Inside /root/openaiproject/bug_clarifier.py:
1.  Initialize the OpenAI client using environment values (api_key and base_url).
2.  Define a function clarify_bug(description: str) -> str that builds a parameterized prompt to rewrite the raw bug description.
3.  Send this prompt to the OpenAI Chat Completion API.
4.  Use the following configuration for the API call:
    +  model: openai/gpt-4.1-mini
    +  messages: user → the constructed prompt
    +  max_tokens: 100
    +  temperature: 0.0
5.  Use the input bug report:
    ```App keeps crashing when I click save.```
6.  Store the AI response in a variable named response and print the clarified bug summary to the console.

Notes:

-  Function must use the developer's input description dynamically in the prompt.

-  Ensure you are working inside /root/openaiproject.

-  OpenAI credentials are available in /root/.bash_profile.

-  Use hardcoded values for api_key and base_url when initializing the OpenAI client or read them from environment variables via os.environ.get('API_KEY') and os.environ.get('BASE_URL').

-  Before running bug_clarifier.py, set up a virtual environment:
```
python3 -m venv venv && source venv/bin/activate && pip install openai
```
-  Maximum of 10 API requests allowed before rate limiting.

<img width="1000" height="394" alt="image" src="https://github.com/user-attachments/assets/5d4b5307-50bc-4de5-babb-65649a1d4768" />

.bash_profile
```
export ALLOWED_MODELS=openai/gpt-5-mini,moonshot/kimi-k2-0711-preview,deepseek/deepseek-chat,moonshotai/kimi-k2-0905,google/gemini-2.5-flash-image-preview,alibaba/qwen3-coder-plus,openai/gpt-4.1-mini,deepseek/deepseek-reasoner,google/gemini-2.5-flash,x-ai/grok-code-fast-1,openai/gpt-5-nano,openai/gpt-4.1-nano
export OPENAI_API_BASE=https://kodekey.ai.kodekloud.com/v1
export OPENAI_API_KEY=Sk-kkAI-e02857141837690af01b0a82f67cc9b0041b5ead1b4b6bb5460a43503a651f7fkk_w5bco54qzq5j34ay-kkd40f212a
```

