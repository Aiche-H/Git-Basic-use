# **Version Control and Update Procedures**

## Version Control Guidelines

- We will use Git for version control.

### Branching Strategy

- **main** branch: Represents the stable, production-ready code.
- **feature/[feature_name]** branches: Used for developing new features.

## **Workflow own repo**

1. ### **Clone the repo you want to work on** (if it already exists)

   ```bash
   git clone <repository_url>
   ```

2. ### **Initialize a new Git repository** (if the repo doesn't exist yet)

   ```bash
   git init
   ```

   **Explanation:**

   - The `git init` command creates a new, empty Git repository in the current working directory.
   - This is typically the first Git command you run in a new project directory.

3. ### **If the repo is already cloned to your local environment** (fetching and merging updates)

   ```bash
   git fetch origin main
   git diff <merge-base>  # (Optional) Review changes before merging
   git merge origin/main
   ```

4. ### **Alternatively, if confident there are no conflicts** (fetching and merging updates)

   ```bash
   git pull origin main
   ```

   ### **Explanation:**

   - `git fetch` retrieves the latest changes from the remote repository (origin) without merging them into your local branch.
   - `git diff <merge-base>` (optional) allows you to review the differences between your local branch and the remote main branch before merging.
   - `git merge origin/main` merges the changes from the remote main branch into your local branch.
   - `git pull` is a shortcut that combines `git fetch` and `git merge` into a single command.

5. ### **Create a new feature branch:**

   ```bash
   git checkout -b <new_branch_name>
   ```

   **Explanation:**

   - `git checkout -b` creates a new branch named `<new_branch_name>` and switches to it.

6. ### **After you're done with your work on the new branch:**

   ```bash
   git add .
   git commit -m "<commit message>"
   git push origin <current_working_branch_name>
   ```

   **Explanation:**

   - `git add .` stages all changes in your working directory for the next commit.
   - `git commit -m "<commit message>"` creates a commit with a descriptive message.
   - `git push origin <current_working_branch_name>` pushes your changes to the remote repository (origin) under the current branch name.

   **Alternatively (combining commands):**

   ```bash
   git commit -am "<comment here>"
   git push origin <current_working_branch_name>
   ```

   - `git commit -am` combines `git add` and `git commit -m` into a single step.

## Working on a Repo You Are Not a Collaborator On

### Branching Strategy on fork

- **main** branch: Represents the stable, production-ready code.
- **feature/[feature_name]** branches: Used for developing new features.

## **Workflow forked repo**

1. ### **Fork the repository on GitHub:**

   - Visit the repository you want to work on.
   - Click the "Fork" button at the top-right corner of the page.
   - Choose a destination repository for your fork, such as your personal account.

2. ### **Clone the forked repository to your local machine:**

   ```bash
   git clone <your_forked_repository_url>
   ```

3. ### **Set up upstream remote:**

   ```bash
   git remote add upstream <original_repository_url>
   ```

   **Explanation:**

   - This command adds the original repository as an upstream remote, allowing you to fetch changes from it.

4. ### **Fetch changes from upstream:**

   ```bash
   git fetch upstream
   ```

   **Explanation:**

   - This command fetches the latest changes from the upstream repository without merging them into your local branch.

5. ### **Create a feature branch:**

   ```bash
   git checkout -b <new_branch_name>
   ```

   **Explanation:**

   - `git checkout -b` creates a new branch named `<new_branch_name>` and switches to it.

6. ### **After you're done with you are work on the new branch:**

   ```bash
   git add .
   git commit -m "<commit message>"
   git push origin <current_working_branch_name>
   ```

   **Explanation:**

   - `git add .` stages all changes in your working directory for the next commit.
   - `git commit -m "<commit message>"` creates a commit with a descriptive message.
   - `git push origin <current_working_branch_name>` pushes your changes to the remote repository (origin) under the current branch name.

   **Alternatively (combining commands):**

   ```bash
   git commit -am "<comment here>"
   git push origin <current_working_branch_name>
   ```

   - `git commit -am` combines `git add` and `git commit -m` into a single step.

7. ### **Create a pull request on GitHub:**

   - Go to your forked repository on GitHub.
   - Go to the "Pull Requests" tab.
   - Click "New pull request."
   - Select the feature/your_feature_name branch as the "head repository" and the main branch of the original repository as the "base repository."
   - Provide a clear description of your changes and submit the pull request.

**Additional Tips:**

- **Keep your forked repository up-to-date** by regularly fetching changes from the upstream repository.
- **Use descriptive commit messages** to clearly explain the changes you've made.
- **Review and resolve any merge conflicts** that may arise when updating your local branch.
- **Consider using a linter or code formatter** to maintain code consistency and quality.
- **If you're working with a team,** communicate and collaborate effectively to ensure smooth development and merging of changes.

By following these guidelines, you can effectively fork and contribute to repositories on GitHub while maintaining a well-organized and efficient workflow.

**Here are some additional Git instructions that might be useful for basic usage:**

## **Working with Remote Repositories:**

- ### **Fetching changes:**

  ```bash
  git fetch <remote> <branch>
  ```

  This fetches changes from the specified remote repository and branch, storing them locally without merging them into your current branch.

- ### **Pushing changes:**

  ```bash
  git push <remote> <branch>
  ```

  This pushes your local changes to the specified remote repository and branch.

- ### **Renaming a remote:**

  ```bash
  git remote rename <old_name> <new_name>
  ```

  This renames a remote repository.

- ### **Removing a remote:**

  ```bash
  git remote rm <remote_name>
  ```

  This removes a remote repository.

## **Working with Branches:**

- ### **Listing branches:**

  ```bash
  git branch
  ```

  This lists all local branches.

- ### **Creating a new branch:**

  ```bash
  git branch <new_branch_name>
  ```

  This creates a new branch from the current branch.

- ### **Switching to a different branch:**

  ```bash
  git checkout <branch_name>
  ```

  This switches to the specified branch.

- ### **Deleting a branch:**

  ```bash
  git branch -d <branch_name>
  ```

  This deletes a local branch.

- ### **Merging branches:**

  ```bash
  git merge <branch_name>
  ```

  This merges the specified branch into the current branch.

- ### **Rebasing a branch:**

  ```bash
  git rebase <upstream_branch>
  ```

  This reapplies your commits on top of the specified upstream branch.

## **Undoing Changes:**

- ### **Reverting a commit:**

  ```bash
  git revert <commit_hash>
  ```

  This creates a new commit that undoes the changes introduced by the specified commit.

- ### **Resetting to a previous commit:**

  ```bash
  git reset --hard <commit_hash>
  ```

  This resets your current branch to the specified commit, discarding any uncommitted changes.

## **Viewing Commit History:**

- ### **Viewing commit logs:**
  
  ```bash
  git log
  ```

  This shows the commit history for the current branch.

- ### **Viewing commit details:**

  ```bash
  git show <commit_hash>
  ```

  This shows the details of a specific commit.

## **Ignoring Files:**

- ### **Creating a .gitignore file:**

  Create a file named `.gitignore` in the root of your project.

- ### **Adding patterns to ignore:**

  List patterns (e.g., filenames, directories) that you want Git to ignore in the `.gitignore` file.

**Remember to replace `<remote>`, `<branch_name>`, `<commit_hash>`, and other placeholders with the appropriate values for your specific use cases.**

## Generating an SSH Key

**1. Check for Existing Keys (Optional):**

Open a file explorer window and navigate to the following directory:

```
C:\Users\<Your Username>\.ssh
```

**Note:** Replace `<Your Username>` with your actual username on the computer.

- If you see any files named `id_rsa` and `id_rsa.pub`, you already have an SSH key pair. You can skip to step 5 to test the connection.
- If the `.ssh` folder doesn't exist or doesn't contain these files, proceed to step 2.

**2. Generate a New SSH Key Pair (if needed):**

Open a terminal window (Command Prompt, PowerShell, etc.).

Type the following command and press Enter:

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```

**Replace "<your_email@example.com>" with your actual email address.**

- You will be prompted to enter a passphrase (optional) for added security. It's generally recommended to set a strong passphrase.
- When prompted, press Enter twice to accept the default location for the key files.

**3. Locate Your Public Key:**

Open a text editor (e.g., Notepad) and navigate to the `.ssh` folder in your user directory (same location as step 1).

Open the file named `id_rsa.pub`. This file contains your public SSH key.

**Copy the entire contents of the `id_rsa.pub` file.**

**4. Add Public Key to GitHub:**

- Log in to your GitHub account.
- Click on your profile picture in the top-right corner and select "Settings".
- In the left sidebar, navigate to "SSH and GPG keys".
- Click on "New SSH key".
- Paste the copied public key content into the "Key" field.
- Give your key a descriptive title (e.g., "Your Computer").
- Click "Add SSH key".

**5. Configure Git to Use SSH (Optional):**

Open a terminal window.

Type the following command and press Enter:

```bash
git config --global core.sshCommand "ssh -i ~/.ssh/id_rsa"
```

**Important:** This command assumes your private key file is named `id_rsa`. If you used a different name during generation (step 2), replace `id_rsa` with the actual filename.

This step configures Git to use your SSH key for authentication when connecting to remote Git repositories (like GitHub). Skipping this step means you'll need to use your username and password for authentication.

**6. Test SSH Connectivity:**

Open a terminal window.

Type the following command and press Enter:

```bash
ssh -T git@github.com
```

**If successful:** You should see a message like "Hi [your username]! You've connected to GitHub using SSH."

**Congratulations!** You have now generated an SSH key and configured Git (optionally) to use it for secure and convenient access to remote Git repositories.
