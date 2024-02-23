# simple_mistral_api_context_history_manager

https://colab.research.google.com/drive/1QOfDPk4BatHo2D37zWmsxCjs_PAb_7bU


# Simple Chat with Mistral API
This is a colab-notebook for chatting with a Mistral model. This colab can run on any online device that runs a web browser (phone, tablet, laptop, desktop, etc.).

### Note: Colabs are slower
Free colabs are amazing for easily sharing and running code in a portable way,
but they are slower. Code in production, or run locally, will be faster than a colab.

## mistral-small = Mixtral8x7
https://mistral.ai/news/mixtral-of-experts/

## Steps:
- Select Model: small-8x7 or tiny-7b (optional step)
- Select style-prompt to experiment with personality of answer (optional)
  - Modify the personality = "" text to describe the personality you want.
  - Specifying the language of reply can be done in the sytem-prompt
- Run all cells [Runtime tab -> run all]
- Type text when prompted at bottom of the colab.
- Download the saved conversation history if you want. (optional)
- Save or download your own copy of the colab under 'File' tab.

# For Roles and Conversation History


```
# Define the request body
request_body = {
  "model": "mistral-small",  # 'mistral-small' is 8x7, vs. 'mistral-tiny' for 7b
  "messages": [{"role": "user", "content": user_input}]
}

# Send the request
response = requests.post(endpoint_url, headers=headers, json=request_body)
```
or
```

conversation_history = [
{"role": "system", "content": user_input},
{"role": "user", "content": user_input},
{"role": "assistant", "content": user_input},
{"role": "user", "content": user_input},
{"role": "assistant", "content": user_input},
{"role": "user", "content": user_input},
]

# Define the request body
request_body = {
  "model": "mistral-small",  # 'mistral-small' is 8x7, vs. 'mistral-tiny' for 7b
  "messages": conversation_history
}

# Send the request
response = requests.post(endpoint_url, headers=headers, json=request_body)
```
