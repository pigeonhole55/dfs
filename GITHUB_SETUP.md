# GitHub Setup & Push Instructions

## Prerequisites

Make sure Git is installed on your system:
- Download from: https://git-scm.com/download/win
- Or use GitHub Desktop: https://desktop.github.com/

## Step-by-Step: Push to GitHub

### 1. Open Terminal/PowerShell in your project directory

Navigate to: `C:\Users\bousk\Desktop\df`

### 2. Initialize Git Repository (if not already initialized)

```powershell
git init
```

### 3. Add All Files

```powershell
git add .
```

### 4. Make Your First Commit

```powershell
git commit -m "Initial commit: Delta Force Heli 101 simulation"
```

### 5. Add Remote Repository

```powershell
git remote add origin https://github.com/pigeonhole55/df.git
```

### 6. Rename Branch to Main

```powershell
git branch -M main
```

### 7. Push to GitHub

```powershell
git push -u origin main
```

**Note:** If this is a new repository, GitHub might ask you to authenticate. You can:
- Use a Personal Access Token (recommended)
- Or use GitHub Desktop for easier authentication

## If You Get Authentication Errors

1. **Create a Personal Access Token:**
   - Go to GitHub → Settings → Developer settings → Personal access tokens → Tokens (classic)
   - Generate new token (classic)
   - Select scope: `repo` (full control)
   - Copy the token

2. **Use Token for Authentication:**
   - When prompted for password, paste the token instead

## After Pushing to GitHub

### Deploy to Azure (Recommended for Students)

1. Go to https://portal.azure.com
2. Create a new Static Web App resource
3. Connect it to your GitHub repository `pigeonhole55/df`
4. Azure will automatically deploy on every push!

### Deploy to Vercel (Alternative)

1. Go to https://vercel.com
2. Sign in with GitHub
3. Import repository `pigeonhole55/df`
4. Click Deploy - it's that simple!

## Quick Commands Summary

```powershell
# Initialize (first time only)
git init

# Add all files
git add .

# Commit
git commit -m "Initial commit: Delta Force Heli 101 simulation"

# Add remote
git remote add origin https://github.com/pigeonhole55/df.git

# Rename branch
git branch -M main

# Push
git push -u origin main
```

## Troubleshooting

**"Git is not recognized"**
- Install Git from https://git-scm.com/download/win
- Restart your terminal/PowerShell after installation

**"Repository not found"**
- Make sure the repository `pigeonhole55/df` exists on GitHub
- Create it at https://github.com/new if it doesn't exist

**"Authentication failed"**
- Use a Personal Access Token instead of password
- Or use GitHub Desktop for easier setup

