# SmartMailX

A Chrome extension that integrates with Gmail to generate AI-powered email replies using Google's Gemini API. The project consists of a Chrome extension, React frontend, and Spring Boot backend.

## Project Structure

```
Email Writer Assistant/
├── email-writer-ext/          # Chrome extension
├── email-writer-react/        # React frontend
└── email-writer-sb/          # Spring Boot backend
```

## Features

- **Gmail Integration**: Chrome extension that adds an "AI Reply" button to Gmail's compose interface
- **AI-Powered Responses**: Generates contextual email replies using Google's Gemini API
- **Tone Customization**: Supports professional, casual, and friendly response tones
- **Standalone Interface**: React-based web interface for testing and standalone use

## Technology Stack

- **Chrome Extension**: JavaScript, Manifest V3
- **Frontend**: React 19, Material-UI, Vite
- **Backend**: Spring Boot 3.5.4, Java 24, WebFlux
- **AI Integration**: Google Gemini API

## Prerequisites

- Java 24
- Node.js 16+
- Google Chrome
- Google Gemini API key

## Installation

### 1. Backend Setup

```bash
cd email-writer-sb
mvn clean install
mvn spring-boot:run
```

The backend will start on `http://localhost:8080`

### 2. Frontend Setup

```bash
cd email-writer-react
npm install
npm run dev
```

The frontend will start on `http://localhost:5173`

## Chrome Extension

### Using the Pre-built Extension

A pre-built version of the Chrome extension is available in the `email-writer-ext` directory. You do not need to build it yourself.

#### To install the extension:

1. Open Chrome and navigate to `chrome://extensions/`
2. Enable "Developer mode"
3. Click "Load unpacked" and select the `email-writer-ext` folder
4. The extension will be installed and active

#### Usage:

1. Open Gmail in Chrome
2. Open an email to reply to
3. Click the "AI Reply" button in the compose toolbar
4. The generated reply will be inserted into the compose box

## Configuration

### API Key Setup

1. Obtain a Google Gemini API key from [Google AI Studio](https://makersuite.google.com/app/apikey)
2. Create a `.env` file in the `email-writer-sb` directory with the following content:

```env
GEMINI_API_KEY=your_api_key_here
GEMINI_API_URL=https://generativelanguage.googleapis.com/v1beta/models/gemini-pro:generateContent?key=
```

> **Note:** The backend is configured to read the Gemini API key and URL from environment variables. Do not commit your `.env` file to version control.

## Web Interface

1. Open the React application in your browser
2. Enter the original email content
3. Select an optional tone preference
4. Click "Generate Reply" to get an AI-generated response

## API Endpoints

### Generate Email Reply

```
POST /api/email/generate
Content-Type: application/json

{
  "emailContent": "Original email content",
  "tone": "professional|casual|friendly"
}
```
## Snapshots<br>
### Extension in Chrome
<img width="800" height="400" alt="EXTENSION" src="https://github.com/user-attachments/assets/c46a9050-343e-4226-9d35-cd09d3d9263e" />

## Demo<br>


https://github.com/user-attachments/assets/3e1bf6d3-744b-4209-be33-6f1ee46277e2









## License

This project is licensed under the MIT License.

## Author

Likhith Poojary
