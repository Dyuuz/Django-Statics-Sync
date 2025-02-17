🚀 Task Automation Script 🛠️
A simple Python script to automate static files refresh, server restart, and browser cache clearing for Django projects.

⚙️ Features
- Clears Django static files cache.
- Restarts the Django development server.
- Ensures the browser loads the latest JavaScript, CSS, and other static files.

🛠️ Installation
- Clone the repository.
= Navigate to the project root.
- Ensure dependencies are installed (django)

🚀 Usage
- Run the script from your Django project root (same directory as manage.py):
- python refresh_static.py

This will:
- Clear the browser cache.
- Restart the server.

🧠 How It Works
- Restarts the server with runserver.
- Appends a cache-busting query parameter to static file URLs.
- Ensure: Static files are correctly linked with {% static %} tags.

  ⚠️ Notes:
- Browser Must Be Closed: Ensure Chrome, Firefox, or Edge is closed before running the script.
- Admin/Root Permissions: Deleting browser cache may require elevated permissions.
- Firefox Profiles: The script now clears cache for all Firefox profiles dynamically.

💡 Troubleshooting
- If changes don't reflect, use Ctrl+Shift+R to force a hard reload.
- Check settings.py for STATICFILES_DIRS and STATIC_ROOT configurations.

