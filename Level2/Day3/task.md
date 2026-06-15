The devops AI Engineering team is developing tools to interpret the tone of developer communications. You are tasked to build a Python-based AI Sentiment Analyzer that identifies whether a given message or feedback is Positive, Negative, or Neutral, helping teams gauge emotional context quickly.

Create a Python program named under /root/openaiproject/sentiment_analyzer.py that analyzes the sentiment (Positive, Negative, or Neutral) of a given text using the OpenAI API.

1.  Initialize the OpenAI client with the provided api_key and base_url.
2.  Define a function named ```analyze_sentiment(text: str) -> str``` that:
+  Constructs a parameterized prompt asking the AI to analyze the sentiment of the given text and respond with Sentiment and Reason.
+  Sends this prompt to the API using the following parameters:
+  model: openai/gpt-4.1-mini
+  messages:{"role": "user", "content": constructed prompt}
+  max_tokens: 60
+  temperature: 0.0
+  Extracts and returns both the Sentiment label (Positive, Negative, or Neutral) and a short Reason explaining the classification.

3.  In the main execution block, analyze the following text:```I am really happy with the new update!```
>  Print the output strictly in the following format:
>  Sentiment:<Positive/Negative/Neutral>
>  Reason:<short explanation>


Notes:
1.  Ensure you are working in the /root/openaiproject directory.
2.  Your API credentials will be provided under /root/.bash_profile.
3.  Use hardcoded values for api_key and base_url when initializing the OpenAI client or read them from environment variables via os.environ.get('OPENAI_API_KEY') and os.environ.get('OPENAI_BASE_URL').
4.  Before running sentiment_analyzer.py, create and activate a virtual environment, then install OpenAI using:
```
python3 -m venv venv && source venv/bin/activate && pip install openai
```
5.  The output should be a single, case-sensitive word & short reason extracted from the AI's response.
6.  You are allowed a maximum of 10 requests. After this, you may encounter a rate limiter error. Therefore, use your requests judiciously.
