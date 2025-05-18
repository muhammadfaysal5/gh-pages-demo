# gh-pages-demo
THis is my assignment changed
GitHub Pages Demo Assignment Report
Assignment Overview
This assignment involves creating a static website that is automatically deployed to GitHub Pages
using GitHub Actions. It demonstrates how to automate website deployment from a GitHub
repository.
Project Setup and Steps
1. Repository Creation
- Created a new GitHub repository named gh-pages-demo.
- This repository hosts the website source code and deployment workflow.
2. Static Website Files
- Inside the repository, created a folder named src/.
- Added the following files inside src/:
- index.html: Contains the basic HTML content for the website.
- style.css: Contains CSS styles to make the website attractive.
- These files build the static website.
3. GitHub Actions Workflow
- Created the workflow file .github/workflows/deploy.yml with the following configuration:
name: Deploy to GitHub Pages
on:
push:
branches: [ "main" ]
permissions:
contents: write
pages: write
id-token: write
jobs:
deploy:
runs-on: ubuntu-latest
steps:
- name: Checkout code
uses: actions/checkout@v3
- name: Set up deployment directory
run: |
mkdir -p public
cp -r src/* public/
- name: Deploy to GitHub Pages
uses: peaceiris/actions-gh-pages@v3
with:
github_token: ${{ secrets.GITHUB_TOKEN }}
publish_dir: ./public
This workflow triggers on every push to the main branch. It copies files from src/ to a public/ folder
and deploys this folder to the gh-pages branch using the peaceiris/actions-gh-pages action.
4. GitHub Pages Configuration
- In the repository settings under Pages, set the source branch to gh-pages.
- Set the directory to root (/).
- This enables the automatic hosting of the static website.
5. Deployment Verification
- After pushing to the main branch, the workflow ran automatically.
- The website is live at:
https://muhammadfaysal5.github.io/gh-pages-demo/
6. README Update
- Updated README to include the live site link.
- Added a short description about automatic deployment using GitHub Actions and GitHub Pages.
Conclusion
This project showcases a straightforward and effective use of GitHub Actions and GitHub Pages to
automate static website deployment. The workflow simplifies continuous deployment by
automatically updating the live site with every push to the main branch.
Additional Notes
- This foundation can be expanded with more advanced deployment workflows and enhanced
website features as needed.
End of Report