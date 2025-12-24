
# Deployment to GitHub Pages

This guide explains how to deploy your Docusaurus textbook to GitHub Pages, a free and easy way to host your project publicly.

The process involves two main steps:
1.  Configuring your Docusaurus project.
2.  Setting up a GitHub Actions workflow to automate deployment.

## 1. Configure `docusaurus.config.js`

You need to tell Docusaurus the correct URLs for your project. Open the `docusaurus.config.js` file in the root of your project and set the following fields:

-   `title`: Your website title.
-   `url`: The URL where your site will live. For GitHub Pages, it's `https://<your-username>.github.io`.
-   `baseUrl`: The subdirectory of your project. This is usually `/<your-repo-name>/`.
-   `organizationName`: Your GitHub username.
-   `projectName`: Your GitHub repository name.

**Example:**

If your GitHub username is `my-user` and your repository is `physical-ai-textbook`, the configuration would look like this:

```javascript
// docusaurus.config.js

const config = {
  title: 'Physical AI & Humanoid Robotics',
  url: 'https://my-user.github.io',
  baseUrl: '/physical-ai-textbook/',
  organizationName: 'my-user', // Your GitHub username.
  projectName: 'physical-ai-textbook', // Your repo name.

  // ... other config
};
```

## 2. Set up GitHub Actions for Automatic Deployment

GitHub Actions can automatically build and deploy your site whenever you push changes to your `main` branch.

### Step 1: Create the Workflow File

1.  In your project root, create a directory path `.github/workflows/`.
2.  Inside that folder, create a new file named `deploy.yml`.

### Step 2: Add the Workflow Content

Copy and paste the following content into your `deploy.yml` file:

```yaml
name: Deploy to GitHub Pages

on:
  push:
    branches:
      - main # Or your default branch
  pull_request:
    branches:
      - main

jobs:
  deploy:
    name: Deploy
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v3

      - name: Setup Node.js
        uses: actions/setup-node@v3
        with:
          node-version: 18
          cache: npm

      - name: Install dependencies
        run: npm install

      - name: Build website
        run: npm run build

      - name: Deploy to GitHub Pages
        uses: peaceiris/actions-gh-pages@v3
        if: github.ref == 'refs/heads/main' # Only deploy from main branch
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_dir: ./build
          user_name: 'github-actions[bot]'
          user_email: 'github-actions[bot]@users.noreply.github.com'

```

### Step 3: Configure Repository Settings

1.  Go to your repository on GitHub.
2.  Click on the **Settings** tab.
3.  In the left sidebar, click on **Pages**.
4.  Under the "Build and deployment" section, change the **Source** from "Deploy from a branch" to **"GitHub Actions"**.

## 3. How it Works

1.  **Push to `main`:** Whenever you push a commit to your `main` branch, the GitHub Actions workflow will automatically trigger.
2.  **Checkout & Build:** The action will check out your code, install all the Node.js dependencies, and run the `npm run build` command to generate the static site in the `./build` directory.
3.  **Deploy:** The `peaceiris/actions-gh-pages` action takes the contents of the `./build` directory and pushes it to a special branch in your repository called `gh-pages`.
4.  **Live Site:** GitHub Pages is automatically configured to serve the files from this `gh-pages` branch, making your site live.

Your textbook will now be available at `https://<your-username>.github.io/<your-repo-name>/`.
