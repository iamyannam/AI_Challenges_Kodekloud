The xfusion AI Innovation Team is building a smart Resume Analyzer that automatically extracts the most relevant job keywords from candidate profiles.

You are required to build a Python-based AI module that extracts exactly five comma-separated job-relevant keywords from a resume paragraph.

Inside /root/openaiproject/resume_extractor.py, create an OpenAI client using the provided API key and base URL. Then define a function:

extract_keywords(text: str) -> str

This function must construct a parameterized prompt that asks the AI to extract exactly 5 comma-separated keywords from the provided resume text.

Next, send the prompt to the OpenAI chat model using:

+  model: openai/gpt-4.1-mini
+  messages: user → prompt
+  max_tokens: 40
+  temperature: 0
+  Finally, print the extracted keywords.


Notes:
1.  Function must be named extract_keywords.
2.  Use the OpenAI API key and base_url from /root/.bash_profile.
3.  The prompt MUST demand exactly five comma-separated keywords.
4.  Use hardcoded values for api_key and base_url when initializing the OpenAI client or read them from environment variables via os.environ.get('OPENAI_API_KEY') and os.environ.get('OPENAI_BASE_URL')
5.  Before running the script, create & activate a virtual environment and install OpenAI.
```
python3 -m venv venv&&source venv/bin/activate &&pip install openai
```
6.  You will use the following resume text:
```
Experienced DevOps engineer skilled in Python, Kubernetes, Docker, CI/CD pipelines, and cloud automation.
```
7.  You are allowed a maximum of 10 requests. After this, you may encounter a rate limiter error, so use your calls wisely.
