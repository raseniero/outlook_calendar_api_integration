# Outlook Calendar API Integration

This project demonstrates how to integrate with the Microsoft Outlook Calendar API using Python. It includes examples of how to authenticate with Azure Identity and interact with the Microsoft Graph SDK to manage calendar events, retrieve calendar data, and perform other calendar-related operations.

## Features
- Authentication using Azure Identity
- Integration with Microsoft Graph SDK
- Examples of managing calendar events
- Support for both Windows and macOS
- Virtual environment setup included

## Prerequisites
- Python 3.8 or higher
- An Azure account with permissions to access Microsoft Graph API
- Git (for cloning the repository)
- Jupyter Notebook (will be installed in the setup)

## Setup Instructions

### 1. Clone the Repository
```bash
git clone https://github.com/yourusername/outlook_calendar_api_integration.git
cd outlook_calendar_api_integration
```

### 2. Set Up Virtual Environment

#### macOS/Linux
```bash
# Create a virtual environment
python3 -m venv .venv

# Activate the virtual environment
source .venv/bin/activate
```

#### Windows (Command Prompt)
```cmd
# Create a virtual environment
python -m venv .venv

# Activate the virtual environment
.venv\Scripts\activate.bat
```

#### Windows (PowerShell)
```powershell
# Create a virtual environment
python -m venv .venv

# Activate the virtual environment
.venv\Scripts\Activate.ps1
```

### 3. Install Dependencies
```bash
# Upgrade pip
python -m pip install --upgrade pip

# Install required packages
pip install -r requirements.txt

# Install Jupyter if you want to use the notebook
pip install notebook
```

### 4. Configure Environment Variables
Create a `.env` file in the project root with the following content:
```
AZURE_CLIENT_ID=your_client_id
AZURE_CLIENT_SECRET=your_client_secret
AZURE_TENANT_ID=your_tenant_id
USER_ID=your_user_id@yourdomain.com
```

### 5. Run Jupyter Notebook
```bash
# Start Jupyter Notebook
jupyter notebook
```

Then open `outlook_calendar_api.ipynb` in your browser.

## Azure AD App Registration
Before running the application, you need to register an application in Azure AD:

1. Go to [Azure Portal](https://portal.azure.com/)
2. Navigate to Azure Active Directory > App registrations > New registration
3. Enter a name for your application
4. Select the appropriate account type
5. Under API permissions, add the following Microsoft Graph permissions:
   - `Calendars.ReadWrite`
   - `User.Read`
   - `offline_access`
6. Grant admin consent for the permissions
7. Create a client secret in the Certificates & secrets section
8. Note down the Application (client) ID, Directory (tenant) ID, and client secret

## Usage
- Open and run the cells in `outlook_calendar_api.ipynb`
- The notebook includes examples for:
  - Authenticating with Azure AD
  - Listing users
  - Viewing calendar events
  - Creating single and recurring events
  - Managing event attendees

## Troubleshooting
- If you get authentication errors, verify your Azure AD app registration and permissions
- Ensure all environment variables are set correctly in the `.env` file
- Make sure your system clock is synchronized (important for token validation)

## License
This project is licensed under the MIT License.