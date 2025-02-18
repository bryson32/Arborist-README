<h1 align="center">Arborist: Revolutionizing Code Analysis</h1><br>
<p align="center">
  <img alt="Arborist Overview" src="./arborist.png"/>
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
## 🚀 Voice-Activated Code Generation
Harness the power of your voice to generate code quickly and effortlessly. Perfect for speeding up your workflow and making coding more accessible.

## 📊 Diagram Generation
Automatically create detailed diagrams to visualize and understand complex codebases. This feature helps you see the bigger picture and navigate your projects with ease.

## 🔄 Prompt Branching
Our branching chat feature allows you to revisit previous points in your conversation without losing context. This ensures a smooth and continuous workflow, making it easier to manage your coding tasks.

## 📈 Visualization Modules
Generate visual representations of your code structures and flow. These visual aids are invaluable for better comprehension and documentation, making your code more maintainable and easier to share.

# Getting Started

### Prerequisites

Before you begin, ensure you have Node.js installed on your machine. You can download it from [nodejs.org](https://nodejs.org/).


### Installation

To install Arborist, follow these steps:

1. **Clone the Repository**
   
   First, clone the repository from GitHub:

   ```bash
   git clone https://github.com/Rivaan-P/Voicecode-web.git
   
2. **Navigate to the Project Directory**

    Locate the cloned repository in your files and open in the CLI
    
3. **Install Dependencies**

    ```bash
    npm install
    # or
    yarn install
    # or
    pnpm install
    # or
    bun install
    ```

    ```Install Gource on Mac
    brew install gource
    ```

4. **Then, run the development server**

    ```bash
    npm run dev
    # or
    yarn dev
    # or
    pnpm dev
    # or
    bun dev
    ```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

You can start editing the page by modifying `app/page.js`. The page auto-updates as you edit the file thanks to hot-reloading.

This project uses [`next/font`](https://nextjs.org/docs/basic-features/font-optimization) to automatically optimize and load Inter, a custom Google Font.
<p/><br>

# Architecture

```
$PROJECT_ROOT
├───src
|   ├───app
|   │   ├───api
|   │   │   └───chat        // for the gemini chat api
|   │   ├───chat            // chat page
|   │   │   └───settings
|   │   ├───login
|   |   └───page.js         // main page
|   ├───components
|   │   ├───branchingtree
|   |   ├───chatui
|   │   ├───filedirectory
|   │   ├───navbar          // logo, navMenu, MenuBar
|   │   ├───ui              // shadcn library
|   │   └───Resizable.jsx   // for the /chat resizable
|   ├───hooks               // hooks for shortcut keyboard
|   └───lib                 // shadcn utils
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

### User Flow
1. **Setup**
  - The user logs into Arborist, or continues as a guest

2. **Provide Intructions**
  - The user speaks or types in a command, for example "Create a new function called helloWorld", or "Whats causing the issue on line 234 in example.cpp?"
  - The Instruction Elaborator refines the command by asking clarifying questions to the user to ensure clarity and accuracy in its response. For example, it might ask, "what would you like this function to do?", or "Where would you like this function to go?"
  - Or for a debug example, "Whats the error message?"

3. **Response**
  - The Primary Code Model processes the refined instructions and generates the appropriate code/analysis 
  - In this process, the model is working hard to make sure no issues or bugs go through to the final output

4. **Output**
  - If a command was made to edit any of the code, the change summarizer will provide a precise summary of changes, and this response will be available to be read aloud using our TTS feature.

5. **Visualization**
  - Our powerful visualization feature can be accessed at any time, given your code base is uploaded to the UI. The user can request a visualization of the code structure at any given moment, and the visualization module will generate impressive diagrams to help the user understand the codebase.- Whether it be a new onboarding engineer that wants to learn a large codebase quickly, or a current team member who just wants to analyze changes his peers made while he was on vacation, our diagram generation feature provides a brilliant solution to the time consuming task of understanding large and complex codebases.
  
6. **Our Unique Branching Feature**
  - To ensure the chatbot remains contextually precise at all times, we have implemented a branching tree for chats, accessible and viewable in the bottom left of the UI.
  - The tree consists of nodes, where each node represents a point in your chat history. At first when youre proceeding through the chat bot normally, this tree will generate a straight line of nodes, but if at any point you decide you need to go to a previous point in your chat without needing to completely delete your current session, for the sake of context for the AI, you can click on a node, and it will bring you back to that point in history. (Note that although any chats that were created past this node that you clicked will dissapear, they are still there, you just need to click back on the most recent node that you were on before you clicked to this new one)
  - The use cases for this feature might not seem obvious at first, but as you work through your code base using Arborist, you will surely encounter a scenario where this feature proves beneficial. For example, what if you had Arborist change up a file to write a new method, but then realized you wanted to review the initial setup before the changes were made? With the branching feature, you can easily navigate back to the point before the changes without losing the context of your current session. Combined with the previously mentioned diagram generation and our models amazing debugging capabilities, this allows you to compare the previous and new states of the code effortlessly.

### The Interface/UI

## Learn More

To learn more about Next.js, take a look at the following resources:

- [Next.js Documentation](https://nextjs.org/docs) - learn about Next.js features and API.
- [Learn Next.js](https://nextjs.org/learn) - an interactive Next.js tutorial.

You can check out [the Next.js GitHub repository](https://github.com/vercel/next.js/) - your feedback and contributions are welcome!

<p/><br>

## Deploy on Vercel

The easiest way to deploy your Next.js app is to use the [Vercel Platform](https://vercel.com/new?utm_medium=default-template&filter=next.js&utm_source=create-next-app&utm_campaign=create-next-app-readme) from the creators of Next.js.

Check out our [Next.js deployment documentation](https://nextjs.org/docs/deployment) for more details.

<!--  [DEMO]: https://github.com/Rivaan-P/Voicecode-web/assets/69108782/2104bca4-b012-4737-a66d-78344f833900 -->
[DEMO]: https://github.com/Rivaan-P/Voicecode-web/assets/69108782/83c0809a-d84a-4241-ac6e-7afb0cdb13f3

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
    <td align="center"><a href="https://github.com/bryson32"><img src="https://avatars.githubusercontent.com/bryson32" width="100px;" alt=""/><br /><sub><b>Bryson Morgan</b></sub></a><br />Full-Stack Developer</td>
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