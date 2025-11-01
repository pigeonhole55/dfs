# Deploy to Azure Static Web Apps (Student Free Tier)

This guide will help you deploy your Delta Force Heli 101 simulation to Azure Static Web Apps.

## Prerequisites
- Azure account (student free tier works!)
- GitHub account
- The files are already set up in this directory

## Step-by-Step Deployment

### Option 1: Deploy via Azure Portal (Easiest)

1. **Go to Azure Portal**
   - Visit https://portal.azure.com
   - Sign in with your student account

2. **Create Static Web App**
   - Click "Create a resource"
   - Search for "Static Web Apps"
   - Click "Create"

3. **Configure the App**
   - **Subscription**: Select your student subscription (free tier)
   - **Resource Group**: Create new or use existing
   - **Name**: Choose a unique name (e.g., "delta-force-heli")
   - **Plan type**: Free (FREE)
   - **Region**: Choose closest to you
   - **Source**: GitHub
   - **Sign in with GitHub**: Authorize Azure to access your GitHub

4. **GitHub Repository Settings**
   - **Organization**: Your GitHub username (pigeonhole55)
   - **Repository**: df (or the repository where this code is)
   - **Branch**: `main` (or `master` if that's your default)
   - **Build Presets**: Custom
   - **App location**: `/` (root)
   - **Api location**: Leave empty
   - **Output location**: `dist` (Vite builds to dist folder)

5. **Review and Create**
   - Click "Review + create"
   - Click "Create"

6. **Get Deployment Token**
   - After creation, go to your Static Web App
   - Click "Manage deployment token"
   - Copy the token

7. **Add GitHub Secret**
   - Go to your GitHub repository
   - Settings → Secrets and variables → Actions
   - Click "New repository secret"
   - Name: `AZURE_STATIC_WEB_APPS_API_TOKEN`
   - Value: Paste the deployment token
   - Click "Add secret"

8. **Trigger Deployment**
   - Push any change to your repository, OR
   - Go to Actions tab and manually run the workflow

### Option 2: Deploy via Azure CLI

```bash
# Install Azure CLI if you don't have it
# Then login
az login

# Create resource group (if needed)
az group create --name delta-force-rg --location eastus

# Create static web app
az staticwebapp create \
  --name delta-force-heli \
  --resource-group delta-force-rg \
  --location eastus \
  --sku Free \
  --source https://github.com/YOUR_USERNAME/YOUR_REPO \
  --branch main \
  --app-location "/" \
  --output-location ""

# Get deployment token
az staticwebapp secrets list \
  --name delta-force-heli \
  --resource-group delta-force-rg
```

## Important Notes

1. **Image File**: Make sure `terry musa.jpg` is in the same directory as `index.html` (root of repository)

2. **File Structure**:
   ```
   your-repo/
   ├── package.json
   ├── vite.config.ts
   ├── src/
   ├── index.html
   ├── terry musa.jpg
   └── .github/workflows/azure-static-web-apps.yml
   ```
   
   **Note**: This is a Vite project that needs to be built. The workflow file will automatically run `npm install && npm run build` and deploy the `dist` folder.

3. **First Deployment**: It may take 5-10 minutes for the first deployment to complete

4. **Custom Domain** (Optional): 
   - After deployment, go to your Static Web App in Azure Portal
   - Click "Custom domains"
   - You can add a custom domain for free!

5. **URL**: Your app will be available at:
   `https://your-app-name.azurestaticapps.net`

## Troubleshooting

- **Build fails**: Check that `index.html` is in the root directory
- **Image not loading**: Verify `terry musa.jpg` is committed to the repository
- **CORS issues**: Static Web Apps handles this automatically - no CORS issues!

## Cost

**This is completely FREE on the student tier!** Azure Static Web Apps free tier includes:
- 100 GB bandwidth per month
- Unlimited custom domains
- SSL certificates (automatic HTTPS)

Enjoy your deployed simulation! 🚁💥

