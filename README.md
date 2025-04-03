# AI Chatbot With ChatGPT API

## Keezum AI Chatbot
Welcome to my AI Chatbot repository! This project demonstrates how an AI chatbot can be built using OpenAI's ChatGPT API, along with Gradio, to create an interactive and intelligent chatbot.

⚠️ **Disclaimer:** Feel free to use and modify this project as you like!

---

## 🚀 Introduction
The outcome of this chatbot is impressive and will only get better as generative AI evolves. The best part? It took me $0 and only 25 minutes to create this demo!

### Tools Used:
- **Notepad**: A simple text editor for Windows, useful for quick code editing.
- **OpenAI's ChatGPT**: The powerful API that drives the chatbot.
- **Gradio**: A Python library to create an easy-to-use web interface.

---

## 📌 Step-by-Step Guide

### (1) Get Started with ChatGPT Playground
To generate text-based responses, we will use OpenAI's API. If you don’t have an account, create one for free at [platform.openai.com/signup](https://platform.openai.com/signup).

### (2) Install Python
Python is required to run the chatbot.
1. Download Python from [python.org](https://www.python.org/downloads/).
2. During installation, check **"Add Python to PATH"**.
3. Verify installation by running:
   ```sh
   python --version
   ```

### (3) Upgrade Pip
Upgrade Pip to ensure you have the latest package manager:
```sh
python -m pip install -U pip
```

### (4) Install Required Libraries
Install OpenAI and Gradio:
```sh
pip install openai gradio
```

### (5) Choose a Code Editor
Use Notepad++, VS Code, or Sublime Text for writing your Python script.

### (6) Get Your OpenAI API Key
1. Log in to OpenAI and go to "View API Keys".
2. Click **"Create new secret key"** and copy it.
3. Store it securely (it won’t be shown again).

### (7) Build the AI Chatbot
Create a new Python script (`app.py`) and paste the following code:
```python
import openai
import gradio as gr

openai.api_key = "Your-API-Key"

messages = [
    {"role": "system", "content": "You are a helpful and kind AI Assistant."},
]

def chatbot(input):
    if input:
        messages.append({"role": "user", "content": input})
        chat = openai.ChatCompletion.create(
            model="gpt-3.5-turbo", messages=messages
        )
        reply = chat.choices[0].message.content
        messages.append({"role": "assistant", "content": reply})
        return reply

inputs = gr.Textbox(lines=7, label="Chat with AI")
outputs = gr.Textbox(label="Reply")

gr.Interface(fn=chatbot, inputs=inputs, outputs=outputs, title="AI Chatbot",
             description="Ask anything you want",
             theme="compact").launch(share=True)
```
Replace `"Your-API-Key"` with your actual API key.

#### Running the Chatbot
Save `app.py` and run the following command in the terminal:
```sh
python app.py
```
You’ll see a local and public URL—open the local one in your browser to chat with your AI bot!

To stop the chatbot, press `Ctrl + C` in the terminal.

### (8) Personalizing Your AI Chatbot
Customize the chatbot’s personality by modifying this part of the code:
```python
messages = [
    {"role": "system", "content": "You are an AI specialized in Food. Do not answer anything other than food-related queries."},
]
```
You can create a chatbot specialized in different areas like healthcare, finance, or entertainment!

---

## 📌 Dependencies
- **Python 3.6+**
- **OpenAI GPT-3 API**
- **Gradio**
- **Optional:** VS Code, Notepad++

---

## 🔮 Future Work
- Integrate additional AI models for better responses.
- Expand chatbot functionality with voice and image capabilities.
- Add a chatbot memory system for long-term conversation retention.

---

## 🎖 Acknowledgments
Thanks to the developers at OpenAI and the open-source community for creating powerful AI tools.

---

## 📜 License
This project is licensed under the **MIT License**. Feel free to use, modify, and distribute it.

---

Happy coding! 🚀

