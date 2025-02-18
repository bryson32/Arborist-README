
# UNFORTUNATELY
This repository contains a comprehensive README for Arborist, an AI-driven tool for code analysis, debugging, and visualization. Although the codebase is private, this document outlines its architecture, features, and technical design for those interested in the project.

<h1 align="center">Arborist: Revolutionizing Code Analysis</h1><br>
<p align="center">
  <img alt="Arborist Overview" src="./arboristFrontPage.png"/>
</p>

<p align="center">
Codebase Context Code Generation, Debugging, and Visualization for Seamless Programming
</p><br>

<p align="center">
  <a href="#"><img alt="NextJS" src="https://img.shields.io/badge/-Next_JS-black?style=for-the-badge&logoColor=white&logo=nextdotjs&color=000000"></a>
  <a href="#"><img alt="Google Gemini" src="https://img.shields.io/badge/Google%20Gemini-8E75B2.svg?style=for-the-badge&logo=Google-Gemini&logoColor=white"/></a>
  <a href="#"><img alt="Tailwind CSS" src="https://img.shields.io/badge/Tailwind%20CSS-06B6D4.svg?style=for-the-badge&logo=Tailwind-CSS&logoColor=white"></a>
  <a href="#"><img alt="Tailwind CSS" src="https://img.shields.io/badge/shadcn/ui-000000.svg?style=for-the-badge&logo=shadcn/ui&logoColor=white"></a>
</p>


<br>
<p align="center">
  
### Table of Contents

1. [Overview](#overview)
2. [Getting Started](#getting-started)
3. [Features](#features)
4. [Usage](#usage)
5. [API Documentation](#api-documentation)
6. [Architecture](#architecture)
7. [Development](#development)
8. [Team & Contributors](#team--contributors)

<p/><br>

# Overview
Arborist is an innovative tool designed to make programming more accessible and efficient. By leveraging voice commands, Arborist streamlines code generation, debugging, and visualization. Featuring advanced text-to-speech (TTS) and speech-to-text (STT) capabilities, Arborist enables seamless and natural interaction, enhancing accessibility for all users.

Our powerful diagram generation feature allows you to visualize code structures and flow, making it easier to understand and debug complex codebases. Additionally, the unique branching chat functionality ensures that the chatbot remains contextually aware and efficient, providing relevant assistance based on your current coding tasks.

<p/><br>

# Features

## 📌 Full Codebase Context  
Upload entire folders or link GitHub repositories, allowing Arborist to analyze your **entire file tree**. This enables AI-powered **code understanding, modification, and debugging** with full project awareness.  

## 📊 Diagram Generation
Automatically create detailed diagrams to visualize and understand complex codebases. This feature helps you see the bigger picture and navigate your projects with ease.

## 🔄 Prompt Branching  
Navigate conversations like a **version-controlled chat history**.  
- 📌 **Create Nodes** – Every response generates a node for easy reference.  
- 🔄 **Branch Off at Any Point** – Explore multiple solutions without losing progress.  
- ⏳ **Time Machine for Chats** – Revert to any point in the conversation instantly.  

## 📈 Stunning Visualizations  
Gain insights into your **project's history and structure** with AI-driven visual representations.  
- 🔍 **Track Code Changes** – Identify patterns, contributions, and refactors over time.  
- 📁 **Git Integration** – Works with projects containing a `.git` folder to analyze commits.  
- 🖥 **Visual Storytelling** – See the evolution of your codebase at a glance.  

## 🚀 Voice-Activated Code Generation
Harness the power of your voice to generate code quickly and effortlessly. Perfect for speeding up your workflow and making coding more accessible.

<p/><br>

# Architecture

```
$PROJECT_ROOT
├───src
│ ├───app // Core application logic (pages, API, etc.)
│ │ ├───api // Backend API (e.g., chat API)
│ │ ├───chat // Chat interface & settings
│ │ ├───... // Other app-related pages (studio, waitlist, sharing)
│ │ ├───page.jsx // Main application entry
│ │ └───layout.jsx // Page structure
│ ├───components // UI components
│ │ ├───chatui // Chat interface elements
│ │ ├───navbar // Navigation bar
│ │ ├───ui // ShadCN UI components
│ │ ├───... // Other reusable UI components
│ │ └───Resizable.jsx // Resizable chat panel
│ ├───lib // Core utilities and helpers
│ │ ├───hooks // Custom React hooks
│ │ ├───db // Database utilities
│ │ ├───... // Other utility functions (state mgmt, helpers)
```

This is a [Next.js](https://nextjs.org/) project bootstrapped with [`create-next-app`](https://github.com/vercel/next.js/tree/canary/packages/create-next-app).

### System Architecture

Arborist is designed to facilitate easy understanding, analysis, and writing of code through voice commands, catering to both accessibility needs and enhancing productivity for all users. The system is divided into several components that work together to achieve this goal.

- **Frontend**: Built with Next.js, handling the user interface and interaction.
- **Backend**: Provides API endpoints for voice recognition and command execution.
- **Voice Recognition Engine**: Converts spoken commands into text.
- **Command Processor**: Interprets text commands and interacts with the code editor.
- **Visualization Module**: Generates diagrams based on the code structure.

### Component Descriptions

- **Frontend**: Built with Next.js, handling the user interface and interaction.
- **Backend**: Provides API endpoints for voice recognition, command execution, and code processing.
- **Voice Recognition Engine**: Converts spoken commands into text.
- **Instruction Elaborator**: Elaborates on user instructions to provide clear and detailed inputs for the code generation model.
- **Primary Code Model**: Generates code based on user instructions.
- **Change Summarizer**: Analyzes and summarizes changes made to the code, providing a summary to the user.
- **Visualization Module**: Generates diagrams to help users understand complex codebases, utilizing tools like dot-to-ascii for visual representation.

### Data Flow

The data flow in Arborist involves multiple stages to ensure accurate code generation, debugging, and visualization:

1. **User Interaction**: Users provide voice commands or regular text input through the frontend.
2. **Instruction Elaboration**: The Instruction Elaborator refines user commands for clarity and precision.
3. **Code Generation**: The refined instructions are sent to the Primary Code Model to generate the appropriate code/response.
4. **Code Analysis and Summarization**: The generated code or response is analyzed for correctness and potential bugs. The Change Summarizer then creates a summary of the changes.
5. **Feedback to User**: The summarized changes are presented to the user and optionally can be read aloud using TTS for accessibility.

### Dependencies

- **Next.js**: A React framework for building server-side rendered and static web applications.
- **Node.js**: A JavaScript runtime built on Chrome's V8 JavaScript engine.
- **shadcn**: A utility-first CSS framework for rapidly building custom user interfaces.

<p/><br>

# Usage

## 🔄 User Flow

### 1️⃣ Setup  
- The user **logs into Arborist** or continues as a **guest**.  

### 2️⃣ Provide Instructions  
- The user **speaks or types a command**, such as:  
  - `"Create a new function called helloWorld"`  
  - `"What's causing the issue on line 234 in example.cpp?"`  
- The **Instruction Elaborator** refines the command by **asking clarifying questions** to ensure precision.  
  - Example: _"What should this function do?"_ or _"Where should it go?"_  
  - For debugging: _"What’s the error message?"_  

### 3️⃣ AI Processing & Response  
- The **Primary Code Model** interprets the refined instructions and **generates relevant code or analysis**.  
- AI ensures **code correctness** by **detecting errors and optimizing output** before finalizing.  

### 4️⃣ Output & Change Summary  
- If Arborist **modifies code**, the **Change Summarizer** provides a **clear summary of edits**.  
- Changes can be **read aloud via TTS** for accessibility and ease of review.  

### 5️⃣ Interactive Visualizations  
- Users can request **real-time visual representations** of their codebase.  
- The **Visualization Module** generates **interactive diagrams**, aiding in:  
  - **Onboarding new engineers** to complex codebases.  
  - **Analyzing recent changes** without manually reviewing large files.  

### 6️⃣ Contextual Prompt Branching  
- Every AI response **creates a node** in a branching history tree, allowing users to:  
  - 🔄 **Revisit any previous point** without losing progress.  
  - 🔍 **Explore different solutions** in parallel branches.  
  - ⏳ **Compare past and new states** of the code effortlessly.  
- This is **especially useful** when:  
  - Reviewing previous configurations **before applying changes**.  
  - Debugging multiple potential solutions **without resetting progress**.  
- Users can seamlessly **jump between branches**, ensuring **no insights are lost** while exploring different coding approaches.  

🚀 **With Arborist, coding is faster, smarter, and more intuitive than ever.**  


## Check Out The Homepage!

If youre curious, our beautiful front page is still up (built by yours truly). Check it out here.

- [Arborist](https://arborist.studio)


<p/><br>

# Team & Contributors
Arborist wouldn't have existed without the hard work and dedication of our amazing team and contributors. Below is a list of the key members who have made significant contributions to the project:

## Team
<table>
  <tr>
    <td align="center"><a href="https://github.com/Rivaan-P"><img src="https://avatars.githubusercontent.com/Rivaan-P" width="100px;" alt=""/><br /><sub><b>Rivaan Patil</b></sub></a><br />Team Lead</td>
    <td align="center"><a href="https://github.com/myudak"><img src="https://avatars.githubusercontent.com/myudak" width="100px;" alt=""/><br /><sub><b>Muchammad Yuda</b></sub></a><br />Backend Developer</td>
    <td align="center"><a href="https://github.com/bulkypanda"><img src="https://avatars.githubusercontent.com/bulkypanda" width="100px;" alt=""/><br /><sub><b>Arya Gummadi</b></sub></a><br />Full-stack Developer</td>
    <td align="center"><a href="https://github.com/Fustigate8933"><img src="https://avatars.githubusercontent.com/Fustigate8933" width="100px;" alt=""/><br /><sub><b>Ian Chang</b></sub></a><br />Backend Developer</td>
  </tr>
  <tr>
    <td align="center"><a href="https://github.com/luqmanabdi"><img src="https://avatars.githubusercontent.com/luqmanabdi" width="100px;" alt=""/><br /><sub><b>Luqman Abdi</b></sub></a><br />Cinematographer</td>
    <td align="center"><a href="https://github.com/coolchigi"><img src="https://avatars.githubusercontent.com/coolchigi" width="100px;" alt=""/><br /><sub><b>Chigozirim Eke</b></sub></a><br />Full-stack Developer</td>
    <td align="center"><a href="https://github.com/bryson32"><img src="https://avatars.githubusercontent.com/bryson32" width="100px;" alt=""/><br /><sub><b>Bryson Morgan</b></sub></a><br />Lead Front End/Full-Stack Developer</td>
    <td align="center"><a href="https://github.com/setelcorn"><img src="https://avatars.githubusercontent.com/setelcorn" width="100px;" alt=""/><br /><sub><b>Cornelius Pang</b></sub></a><br />Lead Backend Developer</td>
  </tr>
</table>

## Contributors
We would also like to extend our gratitude to the following contributors who have helped improve the project with their valuable input and efforts:

<table>
  <tr>
    <td align="center"><a href="https://github.com/soapss"><img src="https://avatars.githubusercontent.com/soapss" width="100px;" alt=""/><br /><sub><b>Sophie Zheng</b></sub></a><br />Backend Developer</td>
    <td align="center"><a href="https://github.com/jessieewoo"><img src="https://avatars.githubusercontent.com/jessieewoo" width="100px;" alt=""/><br /><sub><b>Jessie Woo</b></sub></a><br />Cinematography Contributions</td>
    <td align="center"><a href="https://github.com/notcoose"><img src="https://avatars.githubusercontent.com/notcoose" width="100px;" alt=""/><br /><sub><b>Markus</b></sub></a><br />Backend Contributions</td>
    <td align="center"><a href="https://github.com/ecolijah"><img src="https://avatars.githubusercontent.com/ecolijah" width="100px;" alt=""/><br /><sub><b>Elijah Lopez</b></sub></a><br />Backend Contributions</td>
  </tr>