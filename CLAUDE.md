# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is a Microsoft Outlook Calendar API integration project built with Python. It demonstrates authentication with Azure Identity and interaction with the Microsoft Graph SDK to manage calendar events and retrieve calendar data. The project is implemented as a Jupyter notebook for interactive development and testing.

## Setup and Dependencies

- **Python Version**: Python 3.x
- **Environment**: Uses virtual environment (.venv)
- **Dependencies**: Install with `python3 -m pip install -r requirements.txt`
- **Environment Variables**: Uses `.env` file for Azure credentials (AZURE_CLIENT_ID, AZURE_CLIENT_SECRET, AZURE_TENANT_ID, USER_ID)

## Development Commands

- **Install dependencies**: `python3 -m pip install -r requirements.txt`
- **Run notebook**: `jupyter notebook outlook_calendar_api.ipynb` or use any Jupyter environment
- **Virtual environment**: Project uses `.venv` directory

## Architecture

### Authentication Flow
- Uses Azure Identity with `ClientSecretCredential` for app-only authentication
- Authenticates against Microsoft Graph API using client credentials flow
- Token management handled through Azure Identity library

### Key Components
1. **Environment Configuration** (outlook_calendar_api.ipynb:5): Loads Azure credentials from environment variables
2. **Graph Client Initialization** (outlook_calendar_api.ipynb:6): Sets up Microsoft Graph client with proper authentication
3. **User Management** (outlook_calendar_api.ipynb:14-16): Async functions to retrieve and list Azure AD users
4. **Calendar Operations** (outlook_calendar_api.ipynb:18-19): Calendar view retrieval with timezone handling (PST/PDT conversion)

### Microsoft Graph SDK Usage
- **Users API**: Retrieves user lists with filtering, selection, and ordering capabilities
- **Calendar API**: Fetches calendar events within date ranges with comprehensive event details
- **Async Operations**: All API calls use async/await pattern with nest_asyncio for Jupyter compatibility

### Data Handling
- **Timezone Management**: Uses pytz for PST/PDT timezone conversions
- **Event Processing**: Extracts subject, organizer, time, location, and importance from calendar events
- **Error Handling**: Comprehensive exception handling with detailed error reporting

## Security Considerations
- Never commit `.env` file containing Azure credentials
- Client secrets are masked in output displays
- Access tokens are partially redacted when displayed for debugging