The datacenter AI Development Team is experimenting with how artificial intelligence can create expressive short poetry through automation. In this task, you are required to build a Python-based AI module that generates three-line haikus (5-7-5 syllable pattern) based on a given topic.

Inside /root/openaiproject/haiku_generator.py, create an OpenAI client using the api_key and base_url provided for this session. Additionally, define a function named generate_haiku(topic: str) -> str. This function should construct a parameterized prompt that instructs the AI to generate a haiku about the specified topic, strictly following the 5-7-5 syllable structure.

Then, send the parameterized prompt to the OpenAI chat model using:

+  model: openai/gpt-4.1-mini
+  prompt: parameterized_prompt
+  max_tokens: 60
+  temperature: 0.0

Store the output in a variable named response and print the generated haiku (three distinct lines). Use the topic:

**Topic: 'sky'**

Notes:
1.  Function should accept one parameter: topic.
2.  Use the provided OpenAI  api_key and base_url under /root/.bash_profile.
3.  The prompt must be parameterized with the topic.
4.  Ensure you are working inside /root/openaiproject.
5.  Use hardcoded values for api_key and base_url when initializing the OpenAI client or read them from environment variables via os.environ.get('OPENAI_API_KEY') and os.environ.get('OPENAI_BASE_URL').
6.  Before running, create and activate a virtual environment and install OpenAI:
```
python3 -m venv venv && source venv/bin/activate && pip install openai
```
7.  Final output should display three distinct lines (the haiku).
8.  You are allowed a maximum of 10 requests before hitting rate limits.
