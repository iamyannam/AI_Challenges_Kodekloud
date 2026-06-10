The xfusion AI Engineering Team is building an intelligent Summarization Assistant designed to transform lengthy or unclear developer-reported issues into concise, easy-to-understand one-line summaries. This helps improve clarity, reduce ambiguity, and make bug reports easier to analyze and reproduce.

Inside /root/openaiproject/summarizer.py, create an OpenAI client using the api_key and base_url provided for this session. Additionally, create a function named summarize(text: str) -> str. This function should build a parameterized prompt that asks the AI to summarize the given paragraph into a single-line summary.

Use the following paragraph for summarization:

Artificial Intelligence enables machines to mimic human intelligence, performing tasks such as learning, problem-solving, and decision-making with increasing accuracy.

Then send the previously defined prompt to the OpenAI chat model, save the result in a variable named response, and print the one-line summary to the console.

Model requirements:

+  model: openai/gpt-4.1-mini
+  messages: role=user, content=prompt
+  max_tokens: 60
+  temperature: 0.5

Notes:
1.  Your work directory must be /root/openaiproject.
2.  OpenAI api_key and base_url are stored in /root/.bash_profile.
3.  Prompt must be parameterized with the input paragraph.
4.  Use hardcoded values for api_key and base_url when initializing the OpenAI client or read them from environment variables via os.environ.get('OPENAI_API_KEY') and os.environ.get('OPENAI_BASE_URL').
5.  Before running, create and activate a virtual environment:
```
python3 -m venv venv && source venv/bin/activate && pip install openai
```
6.  You are allowed a maximum of 10 requests. After this, you may encounter a rate limiter error, so use your calls wisely.
