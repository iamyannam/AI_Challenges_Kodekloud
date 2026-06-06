The devops AI Development Team is now exploring how artificial intelligence can assist in improving productivity and communication by transforming lengthy text into clear, concise bullet points for faster understanding.

You are tasked to build a Python-based AI module that converts a given paragraph into concise, easy-to-read bullet points.

Inside /root/openaiproject/converter.py, create an OpenAI client using the api_key and base_url provided for this session. Then, define a function named convert_to_bullets(text: str) -> str that constructs a parameterized prompt asking the AI to convert the given paragraph into short, meaningful bullet points.

After creating the function, send the constructed prompt to the OpenAI chat model with the following parameters:

+  model: openai/gpt-4.1
+  messages: user → prompt
+  max_tokens: 150
+  temperature: 0.1
+  Store the result in a variable named response and print the bullet points to the console.

Use this paragraph for conversion:
**Artificial Intelligence is transforming industries by automating tasks, improving decision-making, and enabling new innovations across healthcare, finance, and education.**


Notes:
1.  Function must accept one parameter: text.
2.  Use the provided OpenAI api_key and base_url from /root/.bash_profile.
3.  The prompt must be parameterized with the paragraph.
4.  Use hardcoded values for api_key&base_url when initializing the OpenAI client, or read them from environment variables via os.environ.get('OPENAI_API_KEY') and os.environ.get('OPENAI_BASE_URL').
5.  Before running converter.py, create and activate a virtual environment:

```
python3 -m venv venv && source venv/bin/activate && pip install openai
```

6.  You are allowed a maximum of 10 API requests due to rate limits.

<img width="1828" height="587" alt="image" src="https://github.com/user-attachments/assets/ab191220-0d70-45c9-951b-3ccd3e60055f" />
