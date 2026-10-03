# GitHub CLI Setup

This guide explains how to install, authenticate, and use the GitHub CLI (`gh`) on macOS.

## 1. Install GitHub CLI

### macOS

Using Homebrew:

```bash
brew install gh
```

Verify the installation:

```bash
gh --version
```

## 2. Authenticate with GitHub

Run:

```bash
gh auth login
```

Follow the prompts:

- Choose `GitHub.com`
- Choose the authentication method (`HTTPS` or `SSH` depending on your preference)
- Select the browser login flow if prompted
- Complete the sign-in steps in your browser

After login, verify access:

```bash
gh auth status
```

## 3. Common Commands

### Check current user

```bash
gh auth status
```

### Create a repository

```bash
gh repo create my-project --public
```

### Clone a repository

```bash
gh repo clone OWNER/REPO
```

### Create a pull request

```bash
gh pr create --fill
```

### View issues

```bash
gh issue list
```

### View pull requests

```bash
gh pr list
```

## 4. Useful GitHub CLI Workflow

Initialize a git repo and connect it to GitHub:

```bash
git init
git add .
git commit -m "Initial commit"
gh repo create --source=. --public --remote=origin --push
```

## 5. Optional: Use SSH for GitHub

If you want to use SSH instead of HTTPS:

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
cat ~/.ssh/id_ed25519.pub
```

Then add the public key to your GitHub account under:

- GitHub → Settings → SSH and GPG keys → New SSH key

## 6. Troubleshooting

### If `gh` is not recognized

```bash
which gh
```

If nothing is returned, reinstall it with Homebrew:

```bash
brew install gh
```

### Re-authenticate if needed

```bash
gh auth logout
gh auth login
```

## 7. Helpful Resources

- Official docs: https://cli.github.com/manual/
- GitHub CLI GitHub repo: https://github.com/cli/cli

This file was created to help set up GitHub CLI quickly and start using GitHub from the terminal.
