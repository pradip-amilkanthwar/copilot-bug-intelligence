# Copilot Bug Intelligence Repository

This repository contains a Proof of Concept (POC) for bug intelligence using GitHub Copilot. Always reference these instructions first and fallback to search or bash commands only when you encounter unexpected information that does not match the information provided here.

## Working Effectively

### Repository Setup
- Clone the repository and navigate to the root directory:
  - `git clone <repository-url>`
  - `cd copilot-bug-intelligence`
- Check repository status:
  - `git --no-pager status`
- Examine current repository structure:
  - `ls -la` 
- Review project overview:
  - `cat README.md`

### Development Environment Setup
- Python 3.12+ is available and required for this project
- Verify Python installation:
  - `python3 --version` -- should show Python 3.12.3 or higher
  - `pip --version` -- should show pip 24.0 or higher
- Create virtual environment for Python development:
  - `python3 -m venv venv`
  - `source venv/bin/activate` (Linux/Mac) or `venv\Scripts\activate` (Windows)
  - `pip install --upgrade pip`
- Deactivate virtual environment when done:
  - `deactivate`

### Current Repository State
- **IMPORTANT**: This repository is currently in minimal setup state with only:
  - `README.md` - Basic project description
  - `.gitignore` - Python-focused ignore patterns
  - `.github/copilot-instructions.md` - These instructions
- **No build system exists yet** - Do not expect to build or run application code at this time
- **No dependencies defined yet** - No requirements.txt, setup.py, or pyproject.toml files exist
- **No tests exist yet** - No testing framework is currently set up

## Validation

### Current State Validation
- Always validate the minimal current state before making changes:
  - `find . -name "*.py" | wc -l` -- should return 0 (no Python files yet)
  - `ls .github/` -- should show copilot-instructions.md
  - `git --no-pager log --oneline -5` -- shows recent commits
- **NEVER CANCEL**: If you add build systems or tests in the future, expect initial setup to take 5-10 minutes
- **Manual validation steps for new Python code**:
  - Create a simple test Python file: `echo "print('Hello, World!')" > test.py`
  - Run it: `python3 test.py`
  - Clean up: `rm test.py`

### Future Development Validation
- When Python code is added, always:
  - Run syntax validation: `python3 -m py_compile filename.py`
  - Check for common issues: `python3 -m flake8 filename.py` (after installing flake8)
  - Test imports work: `python3 -c "import filename"`
- When requirements.txt is added:
  - Install dependencies: `pip install -r requirements.txt` -- may take 2-5 minutes depending on packages
  - Freeze current environment: `pip freeze > requirements-current.txt`
- When tests are added:
  - Run with pytest: `python3 -m pytest` -- timing depends on test complexity
  - Run with unittest: `python3 -m unittest discover`

## Common Tasks

### Repository Navigation
- Check current location: `pwd`
- List all files including hidden: `ls -la`
- Find specific file types: `find . -name "*.py"` or `find . -name "*.md"`
- Search for content: `grep -r "search_term" .`

### Git Operations
- Check status: `git --no-pager status`
- View recent commits: `git --no-pager log --oneline -10`
- Check current branch: `git branch`
- View file differences: `git --no-pager diff`

### File Operations
- View file contents: `cat filename`
- Edit files: Use text editor or IDE
- Create directories: `mkdir -p directory/subdirectory`
- Copy files: `cp source destination`

## Project Structure Reference

### Current Repository Root
```
ls -la
total 28
drwxr-xr-x 4 runner docker 4096 . 
drwxr-xr-x 3 runner docker 4096 ..
drwxr-xr-x 7 runner docker 4096 .git
drwxr-xr-x 2 runner docker 4096 .github
-rw-r--r-- 1 runner docker 4688 .gitignore
-rw-r--r-- 1 runner docker   57 README.md
```

### Current README.md Content
```
cat README.md
# copilot-bug-intelligence
copilot bug intelligence POC.
```

### Python Environment Info
```
python3 --version
Python 3.12.3

pip --version  
pip 24.0 from /usr/lib/python3/dist-packages/pip (python 3.12)
```

## Important Notes

### Development Guidelines
- Always work in a virtual environment when Python code is added
- Follow Python PEP 8 style guidelines
- Use meaningful variable names and add documentation
- Test code changes before committing

### Repository Expectations
- This is a POC repository - expect rapid iteration and changes
- Future development may include:
  - Web interfaces (HTML/CSS/JavaScript)
  - Python backend services
  - AI/ML components for bug intelligence
  - Integration with GitHub APIs
- **CRITICAL**: When builds/tests are added, expect initial setup times of 5-15 minutes and NEVER CANCEL long-running operations

### Issue Tracking
- Check open issues before starting work: `gh issue list` (if GitHub CLI is available)
- Current open issues focus on:
  - Creating login page interfaces (Issue #1)
  - Setting up development infrastructure
  - Establishing coding standards

### Future CI/CD Integration
- When GitHub Actions workflows are added, they will be located in `.github/workflows/`
- Expect Python testing workflows to take 3-10 minutes depending on complexity
- Build artifacts may include: lint reports, test coverage, packaged applications

## Quick Commands Reference

### Essential Daily Commands
- Repository status: `git --no-pager status && ls -la`
- Python environment check: `python3 --version && pip --version`
- Find Python files: `find . -name "*.py" -type f`
- Project overview: `cat README.md && cat .gitignore | head -10`

### Future Development Commands (when applicable)
- Install dependencies: `pip install -r requirements.txt`
- Run tests: `python3 -m pytest` or `python3 -m unittest`
- Code formatting: `python3 -m black .` (after installing black)
- Linting: `python3 -m flake8 .` (after installing flake8)

Remember: This repository is currently in initial setup phase. Many standard development commands will not work until the appropriate files and structure are added. Always validate the current state before assuming functionality exists.