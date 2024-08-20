# Chatbot-using-gemini

import google.generativeai as genai

genai.configure(api_key="your api key")   #key

# Create the model
generation_config = {
  "temperature": 0.9,
  "top_p": 1,
  "top_k": 1,
  "max_output_tokens": 2048,
}

model = genai.GenerativeModel(
  model_name="gemini-1.0-pro",
  generation_config=generation_config,
)

convo= model.start_chat(history=[])

a=input("Enter the question :")

convo.send_message(a)

print(convo.last.text)
