<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Voice-to-Notion</title>
</head>
<body>

<h1>Voice-to-Notion</h1> 
<p>Video demonstration: <a href="https://yurigushiken.com/2023/04/11/voice-to-notion-python-app/" target="_blank">https://yurigushiken.com/2023/04/11/voice-to-notion-python-app/</a></p>

<h2>Requirements</h2>
<ul>
<li>OpenAI API key - acquire at <a href="https://openai.com/api/" target="_blank">https://openai.com/api/</a></li>
<li>Google Drive API key - acquire at <a href="https://developers.google.com/workspace/guides/create-project" target="_blank">https://developers.google.com/workspace/guides/create-project</a></li>
<li>Notion API integration token - acquire by creating an integration at <a href="https://www.notion.so/my-integrations" target="_blank">https://www.notion.so/my-integrations</a></li>
<li>Notion parent page ID - ID of the parent page in Notion to add new pages under</li>
<li>Local folder path - folder path on your computer to monitor for new audio files</li>
</ul>

<h2>Overview</h2>
<p>This tool is an automated workflow that converts voice recordings to text using OpenAI's API and then uploads the text to Notion. It is implemented in Python and consists of two main scripts: <code>voicetotext.py</code> and <code>texttonotion.py</code>. Together these two scripts make up the voice-to-notion workflow.</p>

<h2>How it Works</h2>
<p>Voice-to-Notion continuously monitors a specified folder for new voice recordings. When it detects a new recording, it transcribes the audio to text, generates a summary, and creates a new page in a specified Notion database. The new page includes the transcript, the summary, and a shareable link to the original file in Google Drive.</p>

<h2>Typical User Workflow</h2>
<ol>
<li>Record an audio message</li>
<li>Save it to Google Drive monitored folder</li>
<li><code>voicetotext.py</code> converts it to text</li>
<li><code>texttonotion.py</code> uploads it to Notion</li>
</ol>

<h2>Usage</h2>
<h3>Setup</h3>
<ol>
<li>Acquire API keys and credentials as listed in the Requirements section.</li>
<li>Create a <code>config.json</code> file in the project directory with the following structure:
<pre>
<code>{
    "openai_api_key": "your-openai-api-key",
    "google_drive_api_key": "your-google-drive-api-key",
    "notion_api_key": "your-notion-api-key",
    "notion_parent_page_id": "your-notion-parent-page-id",
    "folder_path": "path-to-your-monitored-folder"
}</code>
</pre>
</li>
<li>Configure your Google Drive API:
<ul>
<li>Follow the instructions <a href="https://developers.google.com/workspace/guides/create-project" target="_blank">here</a> to create a project and obtain your credentials.</li>
<li>Save your <code>credentials.json</code> file in the project directory.</li>
</ul>
</li>
<li>Install the necessary Python packages:
<pre><code>pip install openai google-api-python-client notion-client pydub</code></pre>
</li>
</ol>

<h3>Running the Scripts</h3>
<ol>
<li><strong>voicetotext.py</strong>:
<ul>
<li>This script monitors the specified folder for new audio files, converts them to text, and generates a summary and headline.</li>
<li>Ensure the <code>config.json</code> file is correctly configured.</li>
<li>Run the script:
<pre><code>python voicetotext.py</code></pre>
</li>
</ul>
</li>
<li><strong>texttonotion.py</strong>:
<ul>
<li>This script uploads the generated text files to Notion.</li>
<li>Ensure the <code>config.json</code> file is correctly configured.</li>
<li>Run the script:
<pre><code>python texttonotion.py</code></pre>
</li>
</ul>
</li>
</ol>

<h3>To Use:</h3>
<ol>
<li>Save new audio recordings to the monitored Google Drive folder.</li>
<li>The scripts will automatically process and upload them to Notion.</li>
</ol>

<h2>Features</h2>
<ul>
<li>Continuous monitoring of a folder</li>
<li>Transcription with OpenAI</li>
<li>Summary generation</li>
<li>Upload to Notion</li>
</ul>

</body>
</html>
