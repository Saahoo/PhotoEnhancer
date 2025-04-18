PhotoEnhancer
PhotoEnhancer is a web-based photo editing application that allows users to upload images, apply filters, adjust brightness/contrast/saturation, remove backgrounds, and save edited images. Built with HTML, CSS, and JavaScript, it features a modern, responsive UI and integrates with Supabase for user authentication and the Remove.bg API for background removal.
Features

Image Upload: Upload images (JPG, PNG, etc.) for editing.
Automated Filters:
Vibrant: Enhances color intensity.
Black & White: Converts to grayscale.
Sepia: Applies a sepia tone.
Smooth Skin: Applies a basic blur for smoother skin tones.
HDR Touch: Boosts contrast and vibrancy for an HDR-like effect.


Manual Adjustments:
Brightness: Adjusts image brightness (0–2 range).
Contrast: Adjusts image contrast (0–2 range).
Saturation: Adjusts color intensity (0–2 range).


Background Removal: Removes image backgrounds using the Remove.bg API.
Undo Changes: Reverts to the original uploaded image and resets adjustments.
Save Image: Downloads the edited image as a PNG (requires user authentication).
User Authentication:
Sign up and sign in via Supabase.
Authentication is only required to save images, allowing unauthenticated users to edit freely.


Responsive Design: Works on desktop and mobile devices with a clean, modern UI.
Splash Screen: Displays a branded loading screen with animations on app launch.

Technologies

HTML5: Structure of the web app.
CSS (Tailwind CSS): Styling and responsive design, with custom animations.
JavaScript: Core logic for image processing, authentication, and UI interactions.
Supabase: Handles user authentication (sign-up, sign-in, session management).
Remove.bg API: Provides background removal functionality.
Canvas API: Used for client-side image manipulation.

Project Structure
PhotoEnhancer/
├── index.html      # Main HTML file
├── styles.css      # CSS styles (custom animations)
├── script.js       # JavaScript logic
└── README.md       # Project documentation

Setup
Prerequisites

A modern web browser (Chrome, Firefox, Safari, etc.).
Internet connection for loading external CDNs (Tailwind CSS, Supabase) and APIs (Remove.bg).
A web server to serve the files (e.g., Live Server in VS Code, http-server, or a hosting service like Netlify).

Installation

Clone or Download the Repository:
git clone <repository-url>
cd PhotoEnhancer

Alternatively, download and extract the project files.

Serve the Application:

Using a Local Server:Install http-server (Node.js) globally:npm install -g http-server

Run the server in the project directory:http-server

Access the app at http://localhost:8080.
Using VS Code:Use the Live Server extension to serve index.html.
Using Hosting Services:Deploy to Netlify, Vercel, or similar by uploading the project folder.


Dependencies:

The app uses external CDNs loaded in index.html:
Tailwind CSS: <script src="https://cdn.tailwindcss.com"></script>
Supabase: <script src="https://unpkg.com/@supabase/supabase-js@2"></script>
Google Fonts (Poppins): <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@700&display=swap" rel="stylesheet">


No additional installation is required for these dependencies.


API Keys:

The app uses a hardcoded Remove.bg API key in script.js. For production, replace it with your own key or use a backend proxy to secure it:headers: { 'X-Api-Key': 'jDt6B3qErNzGoTdrpiu1JDFi' }


The Supabase client uses a public anon key. Ensure Supabase Row-Level Security (RLS) is configured to prevent unauthorized access.



Usage

Launch the App:Open index.html via a web server (e.g., http://localhost:8080). The app displays a splash screen with animations for 3 seconds before showing the main interface.

Edit Images:

Upload an Image: Click the file input to upload an image.
Apply Filters: Click buttons (Vibrant, Black & White, Sepia, Smooth Skin, HDR Touch) to apply filters.
Adjust Settings: Use sliders to tweak brightness, contrast, and saturation.
Remove Background: Click "Remove Background" to isolate the foreground using the Remove.bg API.
Undo Changes: Click "Undo Changes" to revert to the original image and reset sliders.


Save Image:

Click "Save Image" to download the edited image as a PNG.
If not signed in, you’ll be prompted to sign in or sign up. Enter your email and password, or create a new account via the "Sign Up" link.
After signing in, the save process completes automatically.


Logout:

If signed in, a "Logout" button appears. Click it to sign out and continue editing without authentication.



Security Considerations

Hardcoded API Keys:

The Remove.bg API key and Supabase anon key are hardcoded in script.js. In production, move these to a backend proxy or environment variables to prevent misuse.
Ensure Supabase RLS is configured to restrict access to authenticated users only.


Client-Side Processing:

Image processing occurs in the browser using the Canvas API, which is secure but may be resource-intensive for large images. Test with various image sizes to ensure performance.



Known Limitations

Undo Functionality: The "Undo Changes" button reverts to the original uploaded image. A full undo/redo stack for individual edits is not implemented.
Background Removal: Relies on the Remove.bg API, which requires an internet connection and a valid API key. Large images may take longer to process.
Error Handling: Errors (e.g., network issues, invalid inputs) are shown via alerts. A more polished UI (e.g., toast notifications) could improve UX.
Accessibility: The app lacks ARIA attributes and full keyboard navigation. Consider adding these for better accessibility.

Future Enhancements

Implement an undo/redo stack to support reverting individual edits.
Add more advanced filters or AI-based enhancements.
Replace alerts with toast notifications for better UX.
Improve accessibility with ARIA labels and keyboard support.
Secure API keys using a backend proxy or environment variables.
Optimize performance for large images using Web Workers.

Contributing
Contributions are welcome! To contribute:

Fork the repository.
Create a new branch (git checkout -b feature/your-feature).
Make changes and commit (git commit -m "Add your feature").
Push to the branch (git push origin feature/your-feature).
Open a

