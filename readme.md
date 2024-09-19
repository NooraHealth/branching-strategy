# Our Branching Strategy 

Our branching strategy is a mix of two branching strategy git flow and github flow


1. Main Branches:
    1. main/prod: Always reflects a production-ready state.
1. Supporting Branches:
    1. staging: Serves as an integration branch for features.
    1. develop: Serves as an integration branch for features.
    1. Feature branches: Branch off from develop and merge back into develop when they are complete.
    
![curret branch](/current-barnch.jpg)


Lest take an example and show how we need to work.
## Cloning a repositorie

Cloning a repository is a fundamental operation in version control systems like Git. It involves creating a copy of an existing repository, typically from a remote location such as GitHub, Bitbucket, or GitLab, to your local machine. This allows you to work on the project independently and later sync your changes with the original repository.

To clone a repository, you'll need a URL that points to the repository you want to clone. This URL can be obtained from the repository's page on the hosting platform.

### Add sshkey to Github 

Adding an SSH key to your GitHub account allows you to establish a secure connection between your computer and GitHub without needing to supply your username and password every time you push changes. Here’s a step-by-step guide on how to generate an SSH key and add it to your GitHub account:


Step 1: Check for Existing SSH Keys
First, you should check if you already have an SSH key set up on your computer:

```bash 
ls -al ~/.ssh 
```

Look for files named either id_rsa.pub, id_ed25519.pub, or similar. If you see such files, you already have an SSH key. If not, you need to create one.

Step 2: Generate a New SSH Key

If you don’t already have an SSH key, you can generate one using the following command:

```bash 
ssh-keygen -t ed25519 -C "your_email@example.com"
```
1. -t ed25519 specifies the type of key to create. ed25519 is the recommended public-key algorithm.
1. -C "your_email@example.com" adds a label to the key with your email.


Add the SSH Key to Your GitHub Account:

Step 3: Go to GitHub.
1. In the upper-right corner, click your profile photo, then click Settings.
1. In the user settings sidebar, click SSH and GPG keys.
1. Click New SSH key or Add SSH key.
1. In the "Title" field, add a descriptive label for the new key. For example, if you’re using your personal laptop, you might call this key "Personal laptop".
1. Paste your key into the "Key" field.
1. Click Add SSH key.
1. If prompted, confirm your GitHub password.

Afetr adding your ssh key you can start cloning the repositorie

![Clone branch](/clone.png)


## Creating a Feature branches

To create a Feature branches you need to checkout to Develop branch first then you need to create a Feature branches using below command

1. Create a New Branch
It's a good practice to create a new branch for each set of changes you contribute:

```bash 
git checkout -b feature-branch-name
```
Replace feature-branch-name with a descriptive name for your branch.

1. Make Your Changes
Make the changes you propose to contribute to the repository. You can edit files, add files, or delete files.

2. Commit Your Changes
After making your changes, you'll need to stage and commit them:

```bash
git add .
git commit -m "A descriptive message about your changes"
```

The git add . command stages all your changes for commit. Replace the commit message with a clear description of what the changes entail.

3. Push Your Changes
Push your branch to your GitHub fork:

```bash
git push origin feature-branch-name
```


## Creating a PR for your Feature branches

Creating a pull request (PR) on GitHub is a crucial part of contributing to collaborative projects. It allows you to propose changes to a repository that the repository owners or collaborators can review before merging into the main branch. Here's a step-by-step guide to creating a pull request:

1. Navigate to the original repository you created a fork from.
1. You might see a prompt to "Compare & pull request" on your recently pushed branches. Click that button. If you don't see the prompt:
    1. Click on the Pull requests tab, then click the New pull request button.
    1. Use the compare branch drop-down menus to select the branch from your fork (feature-branch-name) as the "compare" branch and the main repository’s branch (often main or master) as the "base" branch.
1. Review the changes between your branch and the base branch. Make sure you're merging your changes into the correct branch.
1. Click Create pull request.
1. Add a title and a detailed description of your changes. Explain why your changes should be included in the main branch, linking any relevant issues or discussions.
1. If your repository runs integration checks (like automated builds or tests), wait for them to complete and ensure they pass.
1. Click Create pull request to submit the PR.

![PR](/PR.png)