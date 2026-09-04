# 🎙️ Podly — AI Podcast Generator

> **Turn any idea into a podcast with AI.**

**Podly** is an AI-powered podcast generation platform that transforms a simple topic into a complete podcast using **Google Gemini, Murf AI, and n8n automation**.

Users simply enter a topic, and Podly handles the rest — generating an engaging podcast script with Gemini, converting it into natural-sounding speech using Murf AI, and delivering the final podcast through an automated workflow.

🌐 **Live Demo:** https://podly-podcasts.lovable.app/

---

## ✨ What is Podly?

Creating a podcast traditionally requires research, scriptwriting, recording, editing, and audio processing.

**Podly automates the entire pipeline.**

```text
        💡 YOUR IDEA
             │
             ▼
     ┌─────────────────┐
     │   Podly Web UI  │
     │  Enter a Topic  │
     └────────┬────────┘
              │
              ▼
     ┌─────────────────┐
     │       n8n       │
     │ Automation Layer│
     └────────┬────────┘
              │
              ▼
     ┌─────────────────┐
     │  Google Gemini  │
     │  Script Creation│
     └────────┬────────┘
              │
              ▼
     ┌─────────────────┐
     │    Murf AI      │
     │ Text → Speech   │
     └────────┬────────┘
              │
              ▼
     ┌─────────────────┐
     │ 🎧 Final Podcast│
     │      Audio      │
     └─────────────────┘
```

---

## 🚀 Features

### 🎯 Simple Topic Input

Users only need to provide a topic.

Example:

```text
The Future of Artificial Intelligence
```

No complicated configuration is required.

### 🤖 AI-Powered Script Generation

Google Gemini generates a structured and engaging podcast script based on the user's topic.

The script can contain:

* Introduction
* Topic overview
* Key concepts
* Examples
* Interesting insights
* Conclusion

### 🎙️ Natural AI Voice

The generated script is sent to **Murf AI** using API integration and converted into realistic speech.

### ⚡ Automated Workflow

**n8n** connects the different services and handles the complete backend automation.

```text
User Input
    ↓
Webhook / Trigger
    ↓
Gemini
    ↓
Podcast Script
    ↓
Murf AI API
    ↓
Generated Audio
    ↓
Web Application
```

### 🌐 Web-Based Interface

Podly provides a clean and minimal interface where users can enter a topic and generate their podcast directly from the browser.

### 🎧 Podcast Output

The generated podcast is returned to the application and presented to the user for listening/download.

---

## 🧠 Architecture

Podly follows a simple AI automation architecture:

```text
┌───────────────────────────────────────────┐
│                  FRONTEND                 │
│                                           │
│              🌐 Podly Web App             │
│                                           │
│        Topic Input → Generate Podcast     │
└─────────────────────┬─────────────────────┘
                      │
                      │ API / Webhook
                      ▼
┌───────────────────────────────────────────┐
│             AUTOMATION LAYER              │
│                                           │
│                    n8n                    │
│                                           │
│        Workflow Orchestration             │
└─────────────────────┬─────────────────────┘
                      │
                      ▼
┌───────────────────────────────────────────┐
│                 AI LAYER                  │
│                                           │
│              Google Gemini                │
│                                           │
│          Topic → Podcast Script           │
└─────────────────────┬─────────────────────┘
                      │
                      ▼
┌───────────────────────────────────────────┐
│               VOICE LAYER                 │
│                                           │
│                  Murf AI                  │
│                                           │
│           Script → Natural Voice          │
└─────────────────────┬─────────────────────┘
                      │
                      ▼
              🎧 Podcast Audio
```

---

## 🛠️ Tech Stack

| Technology         | Role                      |
| ------------------ | ------------------------- |
| 🌐 Web Application | User interface            |
| ⚡ n8n              | Workflow automation       |
| 🤖 Google Gemini   | Podcast script generation |
| 🎙️ Murf AI        | AI voice generation       |
| 🔗 REST APIs       | Service communication     |
| 📦 JSON            | Data exchange             |

---

## 🔄 End-to-End Workflow

### Step 1 — Enter a Topic

The user enters a topic into the Podly interface.

```text
What's on your mind?

"The Future of Robotics"
```

### Step 2 — Trigger Automation

The frontend sends the topic to the backend automation workflow.

### Step 3 — Generate Script

n8n passes the topic to Google Gemini.

Gemini generates a podcast-ready script designed to sound conversational rather than like a traditional article.

### Step 4 — Generate Voice

The generated script is sent to Murf AI through an API request.

Murf converts the text into natural-sounding speech.

### Step 5 — Return Podcast

The generated audio is returned to the application and presented as the final podcast.

---

## 📸 Application

### Podly Interface

The application provides a minimal interface focused on one primary action:

> **Type a topic → Generate Podcast**

![Podly](screenshots/podly-home.png)

### n8n Automation Workflow

![n8n Workflow](screenshots/n8n-workflow.png)

### Generated Podcast

![Podcast Output](screenshots/podcast-output.png)

> Replace the screenshot paths above with your actual screenshots.

---

## 💡 Example

### Input

```text
The Impact of Artificial Intelligence on Education
```

### AI-Generated Script

```text
Welcome to Podly!

Today we're exploring how artificial intelligence
is transforming education...

[AI-generated podcast conversation/script]

From personalized learning to intelligent tutoring
systems, AI is changing the way students learn...
```

### Output

```text
🎙️ AI-generated podcast
        ↓
🔊 Natural voice
        ↓
🎧 Ready to listen
```

---

## 🎯 Use Cases

Podly can be used to create podcasts for:

* 🎓 Education
* 💻 Technology
* 🤖 Artificial Intelligence
* 📈 Business
* 📰 News & current topics
* 📚 Learning & revision
* 🚀 Startups
* 🧠 Knowledge sharing
* 🎧 Personal content creation

---

## 🔐 API & Security

Podly integrates external AI services through APIs.

Required services include:

* Google Gemini API
* Murf AI API
* n8n workflow

**Never expose API keys in the frontend or commit them to GitHub.**

Use environment variables or n8n's credential management system.

Example:

```env
GEMINI_API_KEY=your_api_key
MURF_API_KEY=your_api_key
```

> Add your actual credentials only through secure configuration. Do not commit `.env` files.

---

## ⚙️ Local Setup

### 1. Clone the Repository

```bash
git clone https://github.com/YOUR-USERNAME/podly.git

cd podly
```

### 2. Install Dependencies

```bash
npm install
```

### 3. Configure Environment Variables

Create a `.env` file:

```env
GEMINI_API_KEY=your_gemini_key
MURF_API_KEY=your_murf_key
N8N_WEBHOOK_URL=your_n8n_webhook
```

### 4. Start the Application

```bash
npm run dev
```

Open the local development URL provided by your framework.

---

## 🔗 Live Demo

Try Podly here:

**https://podly-podcasts.lovable.app/**

---

## 🔮 Future Enhancements

Podly can be extended into a much more powerful AI podcast platform.

### 🎭 Multiple Speakers

Generate conversations between multiple AI hosts.

```text
Host 1 🎙️
     ↕
Host 2 🎙️
     ↕
Guest 🤖
```

### 🎵 Background Music

Automatically add intro, outro, and background music.

### 🌍 Multi-Language Podcasts

Allow users to generate podcasts in different languages.

### 🎨 AI Podcast Covers

Generate a unique cover image for every episode.

### 📝 Episode Metadata

Automatically generate:

* Podcast title
* Description
* Show notes
* Chapters
* Keywords
* Social media captions

### 📺 Video Podcasts

Convert generated podcasts into AI-powered videos with subtitles and visual content.

### ☁️ Podcast Library

Allow users to save, manage, and revisit previously generated episodes.

### 📡 Publishing Automation

Automatically publish generated episodes to podcast platforms.

---

## 📊 Project Highlights

This project demonstrates practical implementation of:

```text
Generative AI
     +
AI Voice Generation
     +
API Integration
     +
Workflow Automation
     +
Web Development
     +
End-to-End AI Systems
```

Instead of using AI as a standalone chatbot, **Podly connects multiple AI services into a complete automated product.**

---

## 🏆 Why Podly?

Traditional podcast creation:

```text
Research
   ↓
Write
   ↓
Record
   ↓
Edit
   ↓
Export
```

Podly:

```text
Enter Topic
     ↓
     🤖
     ↓
Podcast 🎧
```

**One idea. One click. One AI-generated podcast.**

---

## 👨‍💻 Author

**Your Name**

Built with ❤️ using AI, automation, and modern web technologies.

---

## 📄 License

This project is licensed under the **MIT License**.

---

⭐ **If you found Podly interesting, consider starring the repository!**
