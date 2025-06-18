# Chat-bot
```python
import customtkinter as ctk
import tkinter as tk

responses = {
    "hi": "Hello! How can I help you?",
    "hello": "Hello! How can I help you?",
    "hey":"Hello! How are you?",
    "your name": "I'm ChatBot!",
    "name": "I'm ChatBot!",
    "how are you": "I'm doing great. Thanks for asking!",
    "bye": "Goodbye!",
    "what's the time": "I can't tell the time yet, but you can check your clock!",
    "what's the weather like": "I don't have weather data now, but it's always a good idea to carry an umbrella just in case!",
    "tell me a joke": "Why don't scientists trust atoms? Because they make up everything!",
    "what should I eat today": "How about something healthy and tasty — maybe a sandwich or some fruit?",
    "i'm bored": "Try listening to music, reading, or going for a walk!",
    "i'm sad": "I'm here for you. Sometimes talking to a friend can help.",
    "what is the meaning of life": "42! Just kidding. It depends on what you make of it.",
    "thank you": "You're welcome!",
    "good night": "Good night! Sleep well.",
    "good morning": "Good morning! Have a great day ahead!"
}

def send_message():
    chat_box.configure(state="normal")
    user_input = entry.get()
    chat_box.insert(ctk.END,f"'You: ' {user_input}\n")
    get_responses = display_responses(user_input)
    chat_box.insert(ctk.END,f"'Bot: ' {get_responses}\n")
    entry.delete(0,ctk.END)
    chat_box.configure(state="disabled")
def display_responses(x):
    y = x.lower()
    for key in responses:
        if key in y:
            return responses[key]
    return "Sorry, I don't understand that."
    
root = ctk.CTk()
root.geometry("450x750")
root.title("Chatbot")
root.configure(fg_color ="light sky blue")
label = ctk.CTkLabel(root,text="Simple Chatbot",font=("Arial", 18,))
label.pack()

chat_box =ctk.CTkTextbox(root,width = 400, height = 300,font=("Arial", 15),border_color="black")
chat_box.pack(padx=1,pady=10)

chat_box.insert("end", "Bot : Welcome! I'm your assistant. How can I help you?\n")
entry = ctk.CTkEntry(root, placeholder_text="Enter question here:",width=350,corner_radius=20, 
         border_width =2 ,bg_color = 'transparent' ,
         text_color = 'black',border_color = 'red')
entry.pack()

send_btn = ctk.CTkButton(root,text="send", corner_radius=20, 
         border_width =2 ,bg_color = 'transparent',
         text_color = 'black',border_color = 'red', width=20, height =30,command=send_message,fg_color="yellow", 
                            hover_color="pink")
send_btn.pack(pady=0)

entry.pack(padx=1,pady=30)
root.mainloop()
```
