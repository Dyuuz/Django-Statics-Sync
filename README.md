🚀 Task Automation Script 🛠️
A simple Python script to automate static files refresh, server restart, and browser cache clearing for Django projects.

1️⃣First leap
-Django cachebuster integration

django-cachebuster is a Django package designed to handle cache busting for static files. Cache busting ensures that browsers load the most recent versions of your static files (like CSS, JavaScript, and images) by appending a unique version identifier to the file URLs. This helps avoid issues where browsers serve outdated files from cache instead of fetching the latest changes.

🚀 How it works:
- It generates versioned URLs for static files, often by appending a hash or timestamp to the file path
  
(e.g., style.css → style.css?v=abc123).
- When you update a file, the cachebuster automatically assigns a new version, forcing the browser to load the latest file.

🚀 Key Benefits:
1. Prevents Cache Staleness.
2. Automates Versioning: No need to manually rename files or add version query parameters.
3. Improves Performance: Helps maintain performance by leveraging cache for unchanged files while updating modified ones

🛠️ Setup Process 
1. django-cachebuster installation is automated with the python script.

2. Add cachebuster to INSTALLED_APPS
Open your settings.py file and add cachebuster to the INSTALLED_APPS list:

INSTALLED_APPS = [
    # Other apps,
    
    'cachebuster',
]

3. Configure Static Files and Cachebuster Settings
In your settings.py, configure the cachebuster settings. Ensure the following:

 STATIC_URL = '/static/'

# Configure cachebuster storage
STATICFILES_STORAGE = 'cachebuster.storage.CachebusterManifestStaticFilesStorage'

# Optional: Define the cachebuster URL pattern
CACHEBUSTER_URL = '/static/'

This configuration tells Django to use the cachebusting mechanism and ensures the versioning of static files.

4. Update Your Template to Use Cachebuster
In your HTML templates, use the {% static %} tag along with the {{ cachebust }} tag to automatically append a version query string to the static files.

Example:
<script src="{% static 'script.js' %}?{{ cachebust }}"></script>

This will reference the static file and append a versioning query string based on the file's modification timestamp.

2️⃣ Second Leap

🛠️ Installation
- Navigate to the project root.
- Clone the repository.
- Ensure dependencies are installed (django, etc)

🚀 Usage
- Run the script from your Django project root (same directory as manage.py):
- python refresh_static.py

This will:
- Clear the browser cache.
- Auto install django-cachebuster library.
- Restart the server. (Server IP can be modified in the script)

🧠 How It Works
- Restarts the server with runserver.
- Ensure: Appends a cache-busting query parameter to static file URLs.
E.g <script src="{% static 'script.js' %}?{{ cachebust }}"></script>
- Ensure: Static files are correctly linked with {% static %} tags.

⚠️ Notes:
- Browser Must Be Closed: Ensure Chrome, Firefox, or Edge is closed before running the script.
- Admin/Root Permissions: Deleting browser cache may require elevated permissions.
- Firefox Profiles: The script now clears cache for all Firefox profiles dynamically.

💡 Troubleshooting
- If changes don't reflect, use Ctrl+Shift+R to force a hard reload.
- Check settings.py for STATICFILES_DIRS and STATIC_ROOT configurations.

VOILA🥂

