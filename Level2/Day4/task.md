The devops AI Learning team is developing intelligent training tools that automatically generate learning content for developers and students. You are tasked to build a Python-based Structured Quiz Generator that creates a single, well-formatted multiple-choice question (MCQ) in JSON format to support automated learning modules.

Build a function that generates a quiz on a given topic, ensuring the output is a strict JSON array containing a single question object. The file quiz_generator.py has been created.

1.  Initialize the OpenAI clientusing api_key andbase_urlunder /root/.bash_profile

2.  Define a function generate_quiz(topic: str) -> str.

3.  Implement the API call using a detailed prompt and system message to instruct the AI to generate exactly one multiple-choice question (MCQ) on the topic: 'Basic Linux Commands'.

4.  The final output must be a JSON array containing a single object with the keys: question, options (an array of 4 strings), and answer (the correct option text).

5.  Use the following parameters, and print the raw JSON output to the console:

+  model: openai/gpt-4.1-mini
+  max_tokens: 150
+  temperature: 0.3
You must output your response ONLY as a JSON array that strictly follows this schema:
 >  [
 >  {"question": "The question text.", "options": ["Option A", "Option B", "Option C", "Option D"], "answer": "The correct answer text."}
 >  ]


Notes:
1.  Ensure you are working in the /root/openaiproject folder.
2.  Use the system message to strictly enforce the JSON format and the constraint of one question.
3.  Use hardcoded values for api_key and base_url when initializing the OpenAI client or read them from environment variables via os.environ.get('OPENAI_API_KEY') and os.environ.get('OPENAI_BASE_URL').
4.  Before running quiz_generator.py, create and activate a virtual environment, then install OpenAI using:
```
python3 -m venv venv && source venv/bin/activate && pip install openai
```
5.  Question should be related to topic Linux operating system.
6.  You are allowed a maximum of 10 requests. After this, you may encounter a rate limiter error. Therefore, use your requests judiciously.
