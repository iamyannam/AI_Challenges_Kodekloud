The xfusion AI team is focusing on improving their translation capabilities by using OpenAI's API. Begin by creating a new Python file named translator.py inside the /root/openaiproject directory. Import the OpenAI class in this file to enable interaction with OpenAI models.

Inside translator.py, create an OpenAI client using the API key and base URL provided for this session. Additionally, create a function named translate_to_language(text: str, language: str) -> str. This function should build a parameterized prompt that asks the AI to translate the English text into Spanish and French.

Use the following text for translation: ```Good morning, how are you?```

Finally, update the file to send the prompt to the OpenAI model using:

+  model: openai/gpt-4.1-mini
+  messages: user → prompt
+  max_tokens: 100
+  temperature: 0.7

Then print the translated Spanish & French output to the console.


Notes:
1.  Ensure you are working in the /root/openaiproject directory.
2.  Create and use the OpenAI client with API key + base_url from /root/.bash_profile.
3.  Function must accept parameters text and language.
4.  Prompt must be parameterized.
5.  Use hardcoded values for api_key and base_url when initializing the OpenAI client or read them from environment variables via os.environ.get('OPENAI_API_KEY') and os.environ.get('OPENAI_BASE_URL').
6.  Before running, create a virtual environment and install OpenAI:
```
python3 -m venv venv && source venv/bin/activate && pip install openai
```
7.  You are allowed a maximum of 10 requests. After this, you may encounter a rate limiter error, so use your calls wisely
