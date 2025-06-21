# AI Chat Interface 🤖💬

![GitHub release](https://img.shields.io/github/release/kadi-ux/ai-chat-interface.svg?style=flat-square&color=blue) [![Download](https://img.shields.io/badge/Download%20Latest%20Release-blue.svg?style=flat-square)](https://github.com/kadi-ux/ai-chat-interface/releases)

Welcome to the AI Chat Interface repository! This project offers a privacy-first chat solution powered by OpenAI. Users can securely communicate while maintaining control over their data. Below, you'll find detailed information about the project, its features, and how to get started.

## Table of Contents

1. [Overview](#overview)
2. [Features](#features)
3. [Technologies Used](#technologies-used)
4. [Installation](#installation)
5. [Usage](#usage)
6. [API Documentation](#api-documentation)
7. [Contributing](#contributing)
8. [License](#license)
9. [Contact](#contact)

## Overview

The AI Chat Interface is designed with user privacy in mind. Users provide their own OpenAI API keys, ensuring that no data is stored on our servers. Built using React and Vite for the frontend, and Node.js with Express for the backend, this project allows for real-time messaging and a responsive design. 

This repository aims to serve as a comprehensive solution for those looking to integrate AI chat functionality while prioritizing user privacy.

## Features

- **Privacy-First Approach**: Users maintain control of their data by using their own OpenAI API keys.
- **Real-Time Messaging**: Experience seamless communication with real-time updates.
- **Responsive Design**: The interface adapts to different screen sizes, ensuring a smooth experience on both mobile and desktop devices.
- **Secure API Proxy**: The backend securely handles API requests, protecting user data.
- **Easy Setup**: The project is straightforward to install and run locally.

## Technologies Used

- **Frontend**: React, Vite, Tailwind CSS
- **Backend**: Node.js, Express
- **API**: OpenAI API
- **Database**: None (no data stored on servers)

## Installation

To get started with the AI Chat Interface, follow these steps:

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/kadi-ux/ai-chat-interface.git
   ```

2. **Navigate to the Project Directory**:
   ```bash
   cd ai-chat-interface
   ```

3. **Install Dependencies**:
   For the frontend:
   ```bash
   cd frontend
   npm install
   ```

   For the backend:
   ```bash
   cd backend
   npm install
   ```

4. **Set Up Environment Variables**:
   Create a `.env` file in the backend directory and add your OpenAI API key:
   ```env
   OPENAI_API_KEY=your_api_key_here
   ```

5. **Run the Application**:
   Start the backend server:
   ```bash
   cd backend
   npm start
   ```

   Start the frontend development server:
   ```bash
   cd frontend
   npm run dev
   ```

Now, you can access the application at `http://localhost:3000`.

## Usage

Once the application is running, you can interact with the chat interface. Here’s how to use it:

1. **Open the Chat Interface**: Navigate to the URL where the frontend is running (usually `http://localhost:3000`).
2. **Enter Your API Key**: You will be prompted to enter your OpenAI API key. This step is crucial as it allows the application to connect to the OpenAI API securely.
3. **Start Chatting**: Type your messages in the chat box and press enter. The AI will respond in real-time.

For detailed usage instructions and examples, check the [Releases section](https://github.com/kadi-ux/ai-chat-interface/releases).

## API Documentation

The AI Chat Interface uses the OpenAI API for generating responses. Here’s a brief overview of how it works:

- **Endpoint**: The backend serves as a proxy for OpenAI API requests. All requests from the frontend are sent to the backend, which then forwards them to OpenAI.
- **Request Format**: The request body should include the user’s message and any additional parameters required by the OpenAI API.
- **Response Format**: The backend will return the AI’s response, which the frontend will display in the chat interface.

### Example Request

```json
{
  "message": "Hello, how are you?",
  "parameters": {
    "max_tokens": 150,
    "temperature": 0.7
  }
}
```

### Example Response

```json
{
  "response": "I'm just a computer program, but I'm here to help you!"
}
```

## Contributing

We welcome contributions to the AI Chat Interface! If you want to help improve the project, please follow these steps:

1. **Fork the Repository**: Click the "Fork" button at the top right of the page.
2. **Create a New Branch**: Use a descriptive name for your branch.
   ```bash
   git checkout -b feature/your-feature-name
   ```
3. **Make Your Changes**: Implement your feature or fix a bug.
4. **Commit Your Changes**:
   ```bash
   git commit -m "Add your message here"
   ```
5. **Push to Your Fork**:
   ```bash
   git push origin feature/your-feature-name
   ```
6. **Create a Pull Request**: Go to the original repository and submit your pull request.

Please ensure that your code follows the project's style guidelines and that you test your changes before submitting.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contact

For any questions or feedback, feel free to reach out:

- **GitHub**: [kadi-ux](https://github.com/kadi-ux)
- **Email**: kadi@example.com

Thank you for checking out the AI Chat Interface! We hope you enjoy using it. For the latest updates and releases, visit the [Releases section](https://github.com/kadi-ux/ai-chat-interface/releases).