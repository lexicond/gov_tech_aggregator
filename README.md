# Government GitHub Repository Analysis - Technical Assessment

Welcome to the AI Scan technical challenge for i.AI 👩‍💻

The Prime Minister wants to ensure that we are making the most of international GovTech! In this exercise, you'll be asked to scan international AI codebases using your AI and scanning skills.

This technical assessment can involve analysing Government GitHub repositories using methods of your choice, we're open to any approach that demonstrates your capabilities, however, we have provided you with a python pre-built notebook that provides some initial results.

## Potential Opportunities
The choice of AI opportunity to pursue is yours! 
Some potential topics that you could investigate are below:

- What are specific projects that i.AI can use or collaborate with? What would be the next steps?
- Are there areas of duplication? Where can we make efficiencies by deduplicating across the world?
- What supporting structures would enable better collaboration?
- What would be a sensible schema to categorise types of projects?
- How would you think about the UK Government's strategy differently after reviewing other country's approaches?
- How could we build a technical solution that could productise the scan of international Githubs?

## Different Archetypes of Solutions
We would like you to use this task to showcase your technical skillset spike.

We will deliberately hiring a range of technical capbilities within the team beyond a base level of comfort with coding and AI.

For those who are more comfortable with production grade software, we would encourage you to build off this codebase into a working prototype.

For those who are not as comfortable, please feel free to use other AI methods to solve this problem. Please note that this will not score as highly on the technical score.

## Scoring
We will be assessing over 3 criteria:
- Impact of analysis
- Technical capability shown
- Communication

## Challenge Structure
This interview will take place over 4 hours.
- **Part 1**: Analyse the Government Github Community: https://government.github.com/community/
- **Part 2**: Present your analysis and approach in any format you find most appropriate
Please send a copy of your outputs to your HR contact. If relevant please include a zip file of your code.

## Guidelines
* Try to use AI tools, we actively encourage their use
* Try to build an efficient and fast solution
* Be prepared to talk about key decisions and tradeoffs
* There is no single correct solution that we are looking for
* You are not expected to complete a full scan, but you should be able to explain how you could bring your solution to impact with further time

# GovTech Aggregator
The pipeline is designed to gather and analyze GitHub repositories from government organizations.

The pipeline is particularly useful for:
- Analyzing government open-source projects
- Understanding the types of projects different government organizations are working on
- Categorizing and summarizing government technology initiatives
- Creating a searchable database of government GitHub repositories

## Time Estimate for using the Aggregator
- Setup: 10 minutes
- Implementation: 10 mins

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
