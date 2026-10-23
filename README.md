# API-STAT
API Security Testing Automation Tool APIs are the #1 attack surface in modern applications.  Industry needs an automated tool that discovers all APIs, tests for OWASP API Top 10 vulnerabilities, and generates developer-friendly remediation reports.

**Terminal commands to execute the app**
1. Open the project in VS Code
Open Terminal → New Terminal and navigate to your project folder.

PowerShell example:
cd "$env:USERPROFILE\Downloads\API-STAT-config-check-final\API-STAT"


Check the project files:
dir


Expected files and folders include main.py, requirements.txt, run.bat, app, frontend, and docs.
2. Check Python and create a virtual environment
python --version
python -m venv venv


Activate the environment:
.\venv\Scripts\Activate.ps1


If activation is blocked by PowerShell policy, you can run the project's Python executable directly using the commands below without activating the environment.
3. Install project dependencies
.\venv\Scripts\python.exe -m pip install --upgrade pip
.\venv\Scripts\python.exe -m pip install -r requirements.txt


Verify important dependencies if needed:
.\venv\Scripts\python.exe -m pip show Flask
.\venv\Scripts\python.exe -m pip show python-dotenv


4. Configure environment variables
If the project contains .env.example, copy it to .env:
Copy-Item .env.example .env


Edit .env and enter the required configuration values, such as database connection settings and API keys, if your project requires them.

Important: Never upload .env, passwords, API keys, database credentials, or other secrets to GitHub.
5. Run the API-STAT application
Choose one of these methods.

Method A — Run the batch file:
.\run.bat


Method B — Run the Python application directly:
.\venv\Scripts\python.exe main.py


Open the application in your browser:
- Main application: http://127.0.0.1:5000
- Dashboard: http://127.0.0.1:5000/dashboard
Keep the terminal open while the application is running. Press Ctrl+C to stop it.
6. API-STAT terminal commands
The following commands were mentioned in your earlier project workflow. They are application-specific commands, not standard PowerShell commands.
help
site-config
header-config
tls-config
cors-config
method-config
api-docs
sitemap-map
js-route-map
api-discover
full-report


Run them in the API-STAT interface or CLI that supports them. For URL-based security checks, use only systems you own or have explicit permission to test.

Other CLI commands previously associated with the project were:
python cli.py status
python cli.py config test
python cli.py api live <authorized-url>
python cli.py scan files <path>
python cli.py report 1 --format html


These CLI commands require the corresponding cli.py interface and argument syntax to exist in your current project version.
7. Troubleshooting: recreate the virtual environment
Use this only if the environment is corrupted or dependencies cannot be installed.
Remove-Item -Recurse -Force venv -ErrorAction SilentlyContinue
python -m venv venv
.\venv\Scripts\python.exe -m pip install --upgrade pip
.\venv\Scripts\python.exe -m pip install -r requirements.txt
.\venv\Scripts\python.exe main.py


Earlier project setup attempts also used Python 3.12 and Python 3.14-specific environments. Prefer the Python version supported by your project's dependencies rather than switching versions unnecessarily.
8. Prepare the project for GitHub
Create or verify a .gitignore file in the project root. It should exclude at least:
.venv/
venv/
.venv314/
__pycache__/
*.py[cod]
.env
.env.*
!.env.example
.pytest_cache/
.coverage
dist/
build/


Check that .env and virtual-environment folders are not being committed.
9. Upload API-STAT to GitHub
Create an empty repository on GitHub first. Then run these commands in the VS Code terminal from the project root.

Check Git:
git --version


Initialize the repository if it has not already been initialized:
git init


Review the files:
git status


Stage and commit the project:
git add .
git status
git commit -m "Initial commit: API-STAT security testing tool"


Set the main branch:
git branch -M main


Connect your GitHub repository. Replace the example URL with your actual repository URL:
git remote add origin https://github.com/YOUR-USERNAME/YOUR-REPOSITORY.git


Push the code:
git push -u origin main


If origin already exists, check it instead of adding it again:
git remote -v


If you need to correct the URL:
git remote set-url origin https://github.com/YOUR-USERNAME/YOUR-REPOSITORY.git
git push -u origin main


10. Commands for future updates
Whenever you modify the project and want to upload the latest changes:
git status
git add .
git commit -m "Describe your changes"
git push


Replace "Describe your changes" with a meaningful message, such as "Improve API discovery and security reports".
