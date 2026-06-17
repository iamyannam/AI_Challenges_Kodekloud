The xfusion AI Commerce team is developing tools to automatically enhance product visibility and branding through intelligent marketing assistance. You are tasked to build a Python-based Product Tag and Keyword Generator that creates creative titles and SEO-optimized keyword sets for product listings, helping businesses reach the right audience effectively.

Your task is to create a function that generates a marketing title and a fixed number of SEO keywords based on a product description and a target tone. The file tag_generator.py is ready for your code.

1.  Initialize the OpenAIclient using api_key and base_url provided under /root/.bash_profile
2.  Define a function named generate_seo(description: str, tone: str) -> str.
3.  Construct a parameterized prompt asking the AI to:
+  Generate a short, attention-grabbing product title (4-8 words) in the specified tone.
+  Generate exactly ten low-competition keywords, separated by commas, for SEO tagging.

4.  Send this prompt to the API, ensuring the output is strictly two lines:
+  Line 1: The generated title.
+  Line 2: The ten comma-separated keywords.
Use the following parameters:
+  model: openai/gpt-4.1-mini
+  messages: {"role": "user", "content": constructed prompt}
+  max_tokens: 60
+  temperature: 0.7 (for creative tone)

5.  In the main execution, call the function with:
+  Description: 'A waterproof, lightweight backpack designed for multi-day hikes in difficult terrain.'
+  Tone: 'Rugged and Adventurous'

6.  Print only the raw two-line output to the console.


Notes:
1.  Ensure you are working in the /root/openaiproject directory.
2.  Your API credentials will be provided under /root/.bash_profile.
3.  The entire output must consist of exactly two lines separated by a newline (\n), with no extra text.
4.  The keywords line must contain exactly 10 comma-separated values (no spaces around commas).
5.  Use hardcoded values for api_key and base_url when initializing the OpenAI client or read them from environment variables via os.environ.get('OPENAI_API_KEY') and os.environ.get('OPENAI_BASE_URL').
6.  Before running tag_generator.py, create and activate a virtual environment, then install OpenAI using:
```
python3 -m venv venv && source venv/bin/activate && pip install openai
```
7.  The output should be a single, case-sensitive word extracted from the AI's response.
8.  You are allowed a maximum of 10 requests. After this, you may encounter a rate limiter error. Therefore, use your requests judiciously.
