The devops AI Development Team is building intelligent developer-assistance tools that enhance productivity and communication across engineering workflows. Continuing this mission, you are tasked to develop a Python-based AI Commit Generator that analyzes code change descriptions and produces clean, Conventional Commit–style messages — ensuring consistency and clarity in version control histories.

Your task is to build a function that takes a summary of code changes and generates a formal Git commit message adhering to the Conventional Commit standard (<type>: <subject>). The file /root/openaiproject/commit_generator.py is ready.

1.  Initialize the OpenAI client using api_key & base_url credentials provided under root/.bash_profile.

2.  Define a function named generate_commit(changes: str) -> str.

3.  Construct a detailed prompt asking the AI to:

+  Analyze the input changes.
+  Choose the appropriate commit type from: feat, fix, or docs.
+  Generate a concise subject (under 50 characters).
+  The output must be only the commit message in the exact format: <type>: <subject>.

4.  Send this prompt to the API using the following parameters:
+  model: openai/gpt-4.1-mini
+  messages: [{\"role\": \"user\", \"content\": prompt}]
+  max_tokens: 30
+  temperature: 0.0 (for strict formatting)

5.  In the main execution, call the function with the changes summary:
    _ Summary: 'Added a new user registration endpoint and fixed a typo in the README file._

6.  Print only the generated commit message to the console.


Notes:
1.  The final output must be a single line of text.
2.  The output must contain a colon (:) exactly once, separating the type and subject.
3.  Ensure the commit type correctly matches the primary nature of the change (e.g., feat for new functionality, fix for a bug correction, docs for documentation updates).
4.  Use hardcoded values for api_key and base_url when initializing the OpenAI client or read them from environment variables via os.environ.get('OPENAI_API_KEY') and os.environ.get('OPENAI_BASE_URL').
5.  Before running commit_generator.py, create and activate a virtual environment, then install OpenAI using:
```
python3 -m venv venv && source venv/bin/activate && pip install openai
```
6.  The script should strictly output only the formatted commit message, with no additional commentary or lines.
7.  You are allowed a maximum of 10 requests. After this, you may encounter a rate limiter error. Therefore, use your requests judiciously.
