1.  Create virtual environment and install open ai using pip
  ```
  cd /root/openaiproject

  python3 -m venv bugai
  source bugai/bin/activate

  pip install openai  
  ```
2.  Create bug_clarifier.py with the following content:
   ```
  import os
from openai import OpenAI

# Initialize OpenAI client using environment variables
client = OpenAI(
    api_key=os.environ.get("OPENAI_API_KEY"),
    base_url=os.environ.get("OPENAI_API_BASE")
)

def clarify_bug(description: str) -> str:
    prompt = f"""
Rewrite the following informal bug report into a clear, structured, and professional bug summary.

Bug Report:
{description}
"""

    completion = client.chat.completions.create(
        model="openai/gpt-4.1-mini",
        messages=[
            {
                "role": "user",
                "content": prompt
            }
        ],
        max_tokens=100,
        temperature=0.0
    )

    return completion.choices[0].message.content.strip()

# Input bug report
bug_description = "App keeps crashing when I click save."

# Store AI response
response = clarify_bug(bug_description)

# Print clarified bug summary
print(response)
   ```

3. Run the bug_clarifier.py file using ```python3 bug_clarifier.py```

<img width="1776" height="886" alt="image" src="https://github.com/user-attachments/assets/23a7d9df-cab7-4ce8-84ca-99f8de7b5df3" />
