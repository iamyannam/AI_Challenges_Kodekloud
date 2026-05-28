1. Create Virtual environment & Activate & Install OpenAI
   ```python3 -m venv venv && source venv/bin/activate && pip install openai```
2. Code the commenter.py as per the instructions.
   ```
    import os
    from openai import OpenAI
    
    client = OpenAI(
        api_key=os.getenv("OPENAI_API_KEY"),
        base_url=os.getenv("OPENAI_BASE_URL")
    )
    
    def generate_comment(code_snippet: str) -> str:
        prompt = f"""
    Generate a concise one-line comment or docstring explaining the following Python code:
    
    {code_snippet}
    """
    
        response = client.chat.completions.create(
            model="openai/gpt-4.1-mini",
            messages=[
                {"role": "user", "content": prompt}
            ],
            max_tokens=30,
            temperature=0.2
        )
    
        return response.choices[0].message.content
    
    test_code = """
    def calculate_area(length, width):
     return length * width
    """
    
    response = generate_comment(test_code)
    
    print(response)
   ```
3.  Run the python code ```python commenter.py```
    <img width="1011" height="744" alt="image" src="https://github.com/user-attachments/assets/136a7d65-4753-4ea4-a1d8-d437955ed557" />
