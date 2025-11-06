# GitHub Pages Setup for Install Redirects

This repository uses GitHub Pages to provide click-to-install functionality for Copilot customizations.

## Enabling GitHub Pages

1. Go to your repository on GitHub: https://github.com/kristofer-tdy/flir-prompt-library
2. Click on **Settings** (gear icon)
3. In the left sidebar, click on **Pages**
4. Under "Build and deployment":
   - Source: **Deploy from a branch**
   - Branch: **main** (or your default branch)
   - Folder: **/ (root)**
5. Click **Save**

GitHub will automatically deploy your site to: `https://kristofer-tdy.github.io/flir-prompt-library/`

## How It Works

When users click the "Install in VS Code" button in the documentation:

1. They're directed to a GitHub Pages URL like:
   ```
   https://kristofer-tdy.github.io/flir-prompt-library/install/instructions?url=<encoded-file-url>
   ```

2. The redirect page (HTML file) in the `install/` directory:
   - Automatically redirects to the `vscode://` protocol URL
   - Opens VS Code and triggers the installation
   - Provides a manual fallback button if auto-redirect fails

## Files

- `/install/instructions/index.html` - Redirect for instructions
- `/install/prompt/index.html` - Redirect for prompts
- `/install/mode/index.html` - Redirect for chat modes
- `/install/agent/index.html` - Redirect for agents

## Testing

After enabling GitHub Pages, test the installation by:

1. Wait a few minutes for GitHub Pages to deploy
2. Click an "Install in VS Code" badge in the docs
3. Verify it opens VS Code and prompts for installation

## Troubleshooting

If the redirect doesn't work:

- Verify GitHub Pages is enabled in repository settings
- Check that the site is deployed at the expected URL
- Wait a few minutes after pushing changes for Pages to rebuild
- Try opening the redirect URL directly in a browser to test

---

**Note**: This approach replaces Microsoft's `aka.ms` URL shortener with our own GitHub Pages-based redirector, giving you full control over the installation links.
