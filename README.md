AI Event Scanner & Calendar Assistant

This is a single-page web application that uses AI to scan images and PDFs for event information and adds them to your Google Calendar. It's designed to quickly digitize event details from flyers, posters, or any document, saving you the time of manual entry.

✨ Features
AI-Powered Information Extraction: Uses the Gemini AI model to recognize and extract event details like title, date, time, host, location, and remarks.

Google Calendar Integration: Directly adds the extracted event information to your primary Google Calendar with one click.

Multiple Input Methods:

File Upload: Select an image or PDF file from your device.

Drag & Drop: Drag a file directly onto the upload area.

Camera Capture: Use your device's camera to take a photo of a document.

Editable Fields: Review and edit the extracted information before adding it to your calendar.

Localized AI Responses: The AI is prompted to provide extracted information in Traditional Chinese (zh-tw).

🚀 How to Use
1. Initial Setup (One-Time)
To use the Google Calendar and AI scanning features, you need to link the application to your own Google Cloud project.

Create Google Cloud Credentials:

Go to the Google Cloud Console.

Create a new project if you don't have one.

Enable the Google Calendar API and the Generative Language API.

Go to Credentials and create an API Key.

Create an OAuth 2.0 Client ID for a "Web application".

Deploy the Application:

Save the index.html file from this project.

Deploy it to a hosting service like Zeabur, Vercel, or Netlify to get a permanent URL. This guide assumes deployment on Zeabur.

Configure Credentials:

In your OAuth 2.0 Client ID settings, add your app's URL (e.g., https://your-app.zeabur.app) to both the Authorized JavaScript origins and Authorized redirect URIs.

In your API Key settings, ensure there are no API restrictions, or that it is explicitly allowed to use the "Generative Language API".

Publish the App:

In the OAuth consent screen section of the Google Cloud Console, change the publishing status from "Testing" to "In production" to avoid authorization errors.

2. Using the App
Enter Credentials: Open the app, expand the "Google Calendar Settings" section, and paste your API Key and Client ID. Click "Save & Initialize".

Upload a File: Use the file picker, drag-and-drop, or the camera to upload an image or PDF of your event.

Scan with AI: A preview will appear. Click "Scan File with AI".

Review & Edit: The AI will populate the "Extracted Information" fields. You can click on any field to edit the text.

Add to Calendar: Click "Add to Google Calendar". You may be asked to sign in to your Google account and grant permission the first time.

🛠️ Technologies Used
HTML, CSS, JavaScript: The core of the web application.

Tailwind CSS: For styling the user interface.

Google Generative AI (Gemini): For the AI-powered text extraction.

Google Calendar API: For creating calendar events.

Google Identity Services: For OAuth 2.0 authentication.

PDF.js: For rendering PDF previews in the browser.

🤝 Contributing
Contributions are welcome! If you have ideas for new features or improvements, please feel free to fork the repository and submit a pull request.

Fork the Project

Create your Feature Branch (git checkout -b feature/AmazingFeature)

Commit your Changes (git commit -m 'Add some AmazingFeature')

Push to the Branch (git push origin feature/AmazingFeature)

Open a Pull Request

📄 License
This project is licensed under the MIT License. See the LICENSE file for details.
