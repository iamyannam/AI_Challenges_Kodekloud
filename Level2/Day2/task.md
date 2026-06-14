The nautilus AI Reliability team is designing intelligent tools to monitor application health and proactively detect production issues. You are tasked to build a Python-based Log Anomaly Detector and Summarizer that reads a log file, identifies the most critical failure, and generates a concise, human-readable summary — helping engineers quickly understand the nature and impact of system errors.

Your task is to build a Python script to detect and summarize critical errors from a log file. The file log_analyzer.py has been created under /root/openaiproject.

1.  Initialize the OpenAI client using the api_key and base_url provided in your environment.

2.  Define a function named analyze_log_anomaly(log_file_path: str) -> str.

3.  Inside the function:
+  Read the entire content of the provided log file (app.log under/root/openaiproject).
+  Construct the API call using both a system message and a user message.
+  The system instruction is critical: You must instruct the AI to act as an auditor, focus ONLY on the [CRITICAL] line, and provide a two-part summary: 1) The error type, 2) Immediate Impact.

4.  End this prompt (including the log content in the user message) to the API using the following parameters:
+  model: openai/gpt-4.1-mini
+  messages: [{"role": "user", "content": prompt}]
+  max_tokens: 80
+  temperature: 0.1 (for factual summarization)

5.  In the main execution, call the function with the path '/root/openaiproject/app.log' and print only the raw summary to the console.
   
Notes:
1.  Ensure you are working in the /root/openaiproject folder.
2.  You will be provided with an OpenAI api_key & base_urlfor this session under /root/.bash_profile
3.  The prompt must include the log file content.
4.  The final output printed should be only the concise summary text.
5.  Use hardcoded values for api_key and base_url when initializing the OpenAI client or read them from environment variables via os.environ.get('OPENAI_API_KEY') and os.environ.get('OPENAI_BASE_URL').
6.  Before running log_analyzer.py, create and activate a virtual environment, then install OpenAI using:
```
python3 -m venv venv && source venv/bin/activate && pip install openai
```
7.  You are allowed a maximum of 10 requests. After this, you may encounter a rate limiter error. Therefore, use your requests judiciously.
