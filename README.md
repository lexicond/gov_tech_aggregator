# Government GitHub Repository Analysis - Technical Assessment

This technical assessment involves analyzing government GitHub repositories using Python. The task requires setting up a development environment, working with GitHub's API, and processing data from various government repositories.

## Prerequisites

- Python 3.8 or higher
- Git
- A GitHub account
- Basic understanding of Python, APIs, and data processing

## Setup Instructions

### 1. Clone the Repository
```bash
git clone [repository-url]
cd gov_tech_aggregator
```

### 2. Set Up Python Environment

#### Using venv (Recommended)
```bash
# Create a virtual environment
python -m venv venv

# Activate the virtual environment
# On Windows:
venv\Scripts\activate
# On macOS/Linux:
source venv/bin/activate
```

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

If requirements.txt is not available, install the following packages:
```bash
pip install requests PyYAML python-dotenv pandas jupyter
```

### 4. GitHub Token Setup

1. **Create a GitHub Personal Access Token (PAT)**:
   - Go to [GitHub.com](https://github.com) and sign in
   - Click your profile picture → Settings
   - Scroll to "Developer settings" (bottom of left sidebar)
   - Click "Personal access tokens" → "Tokens (classic)"
   - Click "Generate new token" → "Generate new token (classic)"
   - Configure the token:
     - Name: "Government GitHub Scraper"
     - Expiration: 30-90 days (recommended)
     - Select scopes:
       - `repo` (Full control of private repositories)
       - `read:org` (Read organization data)
       - `read:user` (Read user data)
       - `user:email` (Read user email addresses)
   - Click "Generate token"
   - **IMPORTANT**: Copy the token immediately - you won't see it again!

2. **Create .env File**:
   - Create a new file named `.env` in the project root
   - Add your token:
   ```
   GITHUB_TOKEN=your_token_here
   ```
   - Make sure `.env` is in your `.gitignore`

### 5. Running the Notebook

1. **Start Jupyter Notebook**:
```bash
jupyter notebook
```

2. **Open the Assessment**:
   - Navigate to `test_nb.ipynb`
   - Run the cells in sequence

## Assessment Overview

The notebook contains code to:
1. Fetch government GitHub accounts from a YAML file
2. Retrieve repository details for each account
3. Process and analyze the repository data
4. Generate a markdown report

## Common Issues and Solutions

### Rate Limiting
- GitHub's API has rate limits (60 requests/hour for unauthenticated, 5000 for authenticated)
- If you hit rate limits, implement delays between requests

### Token Issues
- If you get authentication errors, verify your token is:
  - Correctly copied to the `.env` file
  - Has the required permissions
  - Hasn't expired

### Environment Issues
- If packages aren't found, ensure:
  - Virtual environment is activated
  - All dependencies are installed
  - Python version is 3.8 or higher

## Expected Output

The script should generate:
1. A markdown file with repository details
2. A CSV file with the same data
3. Console output showing progress

## Assessment Criteria

Candidates will be evaluated on:
1. Ability to set up the development environment
2. Understanding of API usage and rate limiting
3. Error handling and debugging skills
4. Code organization and documentation
5. Problem-solving approach

## Time Estimate
- Setup: 15-30 minutes
- Implementation: 1-2 hours
- Testing and refinement: 30 minutes

## Additional Resources

- [GitHub API Documentation](https://docs.github.com/en/rest)
- [Python Requests Library](https://docs.python-requests.org/)
- [Jupyter Notebook Documentation](https://jupyter-notebook.readthedocs.io/)

## Support

If you encounter any issues:
1. Check the common issues section
2. Review the GitHub API documentation
3. Search for similar issues on Stack Overflow
4. Contact the assessment administrator

## Notes

- Keep your GitHub token secure and never commit it to version control
- Consider implementing rate limiting and pagination for large datasets
- Add error handling for API failures
- Document any assumptions or decisions made during implementation 