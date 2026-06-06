The nautilus AI Development Team is now working on automating written communication tasks. As part of this initiative, you are required to build a Python-based AI Email Assistant that rewrites messages into polite and professional emails.

Inside email_assistant.py, create an OpenAI client using the provided API key and base URL under /root/.bash_profile. Then, define a function named rewrite_email(text: str) -> str that constructs a parameterized prompt asking the AI to rewrite the given email text politely and professionally.

After defining rewrite_email, send the constructed prompt to the OpenAI chat model with these parameters:

+  model: openai/gpt-4.1-mini
+  messages: user → prompt
+  max_tokens: 60
+  temperature: 0.1
  
 Store the output in a variable named response and print the polite rewritten email to the console.

Use the following email text for rewriting:

**hey send me that report asap**


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
