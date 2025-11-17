# Deployment Guide

This document explains how to deploy the Hugo documentation site to GitHub Pages.

## Prerequisites

- Repository must be public or have GitHub Pages enabled for private repositories
- Administrator access to repository settings

## Setup Instructions

### 1. Enable GitHub Pages

1. Navigate to your repository on GitHub: https://github.com/Ric2Dev/yu-dev
2. Click on **Settings** (top navigation bar)
3. In the left sidebar, click on **Pages** (under "Code and automation")
4. Under **Build and deployment**:
   - **Source**: Select `GitHub Actions` from the dropdown
   - The workflow will automatically detect the `.github/workflows/hugo.yml` file

### 2. Trigger the Deployment

The site will automatically deploy when:
- Changes are pushed to the `main` branch
- You manually trigger the workflow from the Actions tab

To manually trigger:
1. Go to the **Actions** tab in your repository
2. Click on "Deploy Hugo site to Pages" workflow
3. Click "Run workflow" button
4. Select the `main` branch
5. Click "Run workflow"

### 3. Verify Deployment

1. After the workflow completes (usually 1-2 minutes), go to the **Actions** tab
2. Click on the latest workflow run to see the details
3. If successful, you'll see a green checkmark
4. The deployment URL will be displayed in the workflow summary
5. Visit: https://ric2dev.github.io/yu-dev/

## Workflow Details

The deployment workflow:
1. **Installs Hugo** (v0.146.0 Extended) and Dart Sass
2. **Checks out** the repository with submodules (theme)
3. **Configures** GitHub Pages settings
4. **Builds** the site with Hugo (minified and optimized)
5. **Uploads** the build artifacts
6. **Deploys** to GitHub Pages

## Troubleshooting

### Workflow Fails

If the workflow fails:
1. Check the Actions tab for error messages
2. Verify Hugo version compatibility
3. Ensure theme submodule is properly initialized
4. Check for syntax errors in content files

### Site Not Loading

If the site deploys but doesn't load:
1. Verify GitHub Pages is enabled in Settings
2. Check if the correct branch/source is selected
3. Clear browser cache and try again
4. Wait a few minutes for DNS propagation

### Permission Errors

If you get permission errors:
1. Verify the workflow has required permissions
2. Check repository settings allow Actions to deploy Pages
3. Ensure you have admin access to the repository

## Updating Content

To update the documentation:
1. Edit or add markdown files in the `content/` directory
2. Commit and push to the `main` branch
3. The workflow will automatically rebuild and deploy

## Custom Domain (Optional)

To use a custom domain:
1. Go to Settings > Pages
2. Enter your custom domain in the "Custom domain" field
3. Follow the DNS configuration instructions
4. Update `baseURL` in `hugo.toml` to your custom domain

## Monitoring

- **Build Status**: Check the Actions tab for build status badges
- **Deployment History**: View past deployments in the Actions tab
- **Site Analytics**: Configure GitHub Pages analytics if needed
