This guide explains how to upload your code to a public GitHub repository without exposing your secret API key and then how to deploy it.

Step 1: "Hiding Your Code" (Securing Your API Key)

You cannot "hide" the HTML and JavaScript code in a public repo, but you must hide your secret API key. We have already done this.

advanced_chatbot.html now looks for a GEMINI_API_KEY variable.

config.js is where you store this key.

.gitignore is a file that tells Git "Do not ever track or upload the file named config.js."

This setup is perfect. Your secret key stays on your computer, but your code can be shared publicly.

Step 2: Uploading to GitHub

Create a new repository on GitHub:

Go to GitHub.com and log in.

Click the "+" icon in the top-right and select "New repository."

Give it a name (e.g., ai-chatbot-project).

Make it Public.

Do NOT add a README or .gitignore (we already have them).

Click "Create repository."

Upload your files (Desktop Method):

On your new repository page, click the "Add file" button, then "Upload files."

Drag and drop the following files into the uploader:

advanced_chatbot.html

config.example.js (NOT config.js!)

.gitignore

README.md

Deployment_Guide.md (this file)

Click "Commit changes."

Step 3: Deploying Your Chatbot (Live on the Web)

You can host this project for free on services like Netlify or Vercel. Netlify is very simple for this.

Sign up for Netlify:

Go to Netlify.com and sign up (you can use your GitHub account).

Deploy from GitHub:

In your Netlify dashboard, click "Add new site" -> "Import an existing project."

Connect to GitHub and authorize it.

Select your new repository (ai-chatbot-project).

Build Settings:

Netlify will ask for build settings. This project doesn't have a "build step," so the default settings are fine.

Deploy Site: Click the "Deploy" button. Netlify will pull your code from GitHub and host it.

The FINAL, CRITICAL Step: Adding Your API Key

The deployed site won't work yet because it's missing the config.js file.

This is the most secure way to add your key:

In your Netlify site's dashboard, go to Site configuration > Environment variables.

Click "Add a variable".

For the Key, enter: GEMINI_API_KEY

For the Value, paste your secret Gemini API key.

Click "Save".

Inject the Key into Your HTML:

Netlify won't automatically create config.js. We need to inject the variable.

Go to Site configuration > Snippet injection.

Click "Add snippet".

Insert before: </head>

In the HTML box, paste this script:

<script>
  const GEMINI_API_KEY = "${GEMINI_API_KEY}";
</script>


Click "Save". Netlify will automatically (and securely) replace ${GEMINI_API_KEY} with your saved environment variable before it sends the file to a user.

Redeploy:

Go to the "Deploys" tab for your site.

Click "Trigger deploy" -> "Deploy site."

Wait for it to finish. Your chatbot is now live and secure! You can use the URL (like my-chatbot.netlify.app) to access it.