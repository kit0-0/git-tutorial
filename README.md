### What is a Version Control System?

A **version control system (VCS)** is a tool that tracks the history of changes to files over time. It allows multiple people to collaborate on a project, enabling them to work on different parts simultaneously without interfering with each other’s work. A VCS is particularly valuable in software development because it helps manage code changes, making it easier to fix bugs, run tests, and develop new features. The key features of a VCS include:

- **Tracking Changes**: It records changes made to the files, including who made the change and when.
- **Branching and Merging**: It allows developers to create branches to work on new features or bug fixes independently. These branches can later be merged back into the main project.
- **Reversion**: It provides the ability to revert files to a previous state, which is useful when a bug is introduced or when a new feature is not working as expected.
- **Collaboration**: It enables multiple developers to work on the same project simultaneously without overwriting each other’s changes.

### How is it Related to Git and GitHub?

**Git** is an example of a distributed version control system. In a distributed VCS, every developer has a local copy of the entire project history, not just the latest version of files. This setup offers several advantages, such as faster operations and improved collaboration without the need for a constant connection to a central server.

**GitHub** is a web-based platform that uses Git for version control. It provides a cloud-based hosting service for Git repositories, making it easier for developers to store, manage, and collaborate on projects. GitHub enhances Git with additional features like:

- **Pull Requests**: A way to propose changes to a codebase and discuss them before merging.
- **Issue Tracking**: A system to track bugs, enhancements, and other project tasks.
- **Continuous Integration/Continuous Deployment (CI/CD)**: Tools to automatically test and deploy code.
- **Project Management Tools**: Features to manage project milestones and tasks.

### Why is it Important?

Understanding Git and GitHub is crucial for several reasons:

- **Team Collaboration**: Nearly all companies use a version control system for their projects. Knowing Git and GitHub helps you quickly adapt to the workflows and collaborate effectively with your team.
- **Code Management**: With Git, you can manage and track changes efficiently, ensuring that the project history is well-documented and recoverable.
- **Best Practices**: Familiarity with version control practices ensures that you can follow and implement industry-standard workflows, such as branching strategies and code reviews.

### What's the Difference Between Git and GitHub?

- **Git**: A distributed version control system that tracks changes to files and helps manage project history.
- **GitHub**: A platform that hosts Git repositories and provides additional collaboration tools.

### GitHub Flow

**GitHub Flow** is a lightweight, branch-based workflow for managing changes to your project. The steps typically include:

1. **Create a Branch**: For a new feature or bug fix, create a branch from the main codebase.
2. **Add Commits**: Make changes and commit them to your branch.
3. **Open a Pull Request**: When the feature or fix is ready, open a pull request to merge your branch into the main codebase.
4. **Discuss and Review**: Team members can review the changes, discuss them, and suggest improvements.
5. **Merge**: Once the changes are approved, the branch is merged into the main codebase.
6. **Deploy**: After merging, the changes can be deployed to production.

### Important Terms and Commands in Git

**Important Terms:**

- **Repository (Repo)**: A storage location for your project, which contains all of the files and the entire revision history.
- **Branch**: A separate line of development, allowing you to work on different features or fixes independently.
- **Commit**: A record of changes made to the repository. Each commit has a unique ID and includes a message describing the changes.
- **Merge**: Combining changes from one branch into another.
- **Pull Request**: A way to propose changes to the codebase and discuss them before merging.
- **Master/Main**: The default primary branch in a repository.

**Important Commands:**

- **git init**: Initialize a new Git repository.
- **git clone [repo URL]**: Clone an existing repository.
- **git status**: Show the working directory status.
- **git add [file]**: Add a file to the staging area.
- **git commit -m "message"**: Commit changes with a message.
- **git push**: Push changes to the remote repository.
- **git pull**: Fetch and merge changes from the remote repository.
- **git branch**: List, create, or delete branches.
- **git checkout [branch]**: Switch to a different branch.
- **git merge [branch]**: Merge another branch into the current branch.
- **git log**: View commit history.

### Exercise

In this exercise, you will practice Gitflow with an empty repository.

### Instructions

1. **Create a New Repository**
   - Initialize it with an empty README file.
     - Go to GitHub and create a new repository.
     - Check the option to initialize with a README file.

2. **Clone the Repository**
   - Clone the newly created repository to your local machine.
     ```sh
     git clone https://github.com/your-username/your-repo-name.git
     cd your-repo-name
     ```

3. **Create and Push a New Branch**
   - Add a new branch named `dev` (alternative names: `development`, `develop`).
     ```sh
     git checkout -b dev
     ```
   - Push the `dev` branch to GitHub and set the upstream branch.
     ```sh
     git push --set-upstream origin dev
     ```

4. **Set the Default Branch**
   - On GitHub, go to the repository settings.
   - Change the default branch to `dev`.

5. **Create a Feature Branch**
   - Create a feature branch called `add-quotes`.
     ```sh
     git checkout -b add-quotes
     ```

6. **Add Files to the Feature Branch**
   - Add a `programmer.txt` file with the following sentence (typo is needed there):
     ```
     A good programmer is someone who always looks both ways before crosing a one-way street.
     ```
   - Add a `solve.txt` file with the following sentence:
     ```
     "First, solve the problem. Then, write the code." – John Johnson
     ```
   - Add another `test.txt` file. It should be empty.
     ```sh
     echo "A good programmer is someone who always looks both ways before crosing a one-way street." > programmer.txt
     echo "\"First, solve the problem. Then, write the code.\" – John Johnson" > solve.txt
     touch test.txt
     ```

7. **Commit Changes**
   - Commit all files to your feature branch.
     ```sh
     git add programmer.txt solve.txt test.txt
     git commit -m "Add programmer.txt, solve.txt, and test.txt"
     ```

8. **Push Changes to GitHub**
   - Push your changes to GitHub.
     ```sh
     git push --set-upstream origin add-quotes
     ```

In simpler terms, using `--set-upstream` with `git push` does two things at once:

1. **Push your branch to the remote repository**: This means you're sending your local branch (e.g., add-quotes) to a place where others can access it, like GitHub or GitLab.
2. **Remember the connection**: It tells Git to remember that your local branch (e.g., add-quotes) is linked to the branch on the remote repository. This way, in the future, you can just use `git push` or `git pull` without having to specify the branch name every time.

9. **Open a Pull Request**
   - Open a new pull request from `add-quotes` into `dev`.
     - Go to your repository on GitHub.
     - Click on the "Pull requests" tab.
     - Click on the "New pull request" button.
     - Select `add-quotes` as the branch you want to merge from and `dev` as the branch you want to merge into.
     - Add a comment similar to this one:
       ```
       Initialize repo with readme
       ```

10. **Keep Your Pull Request Open**
    - Keep your pull request open. You will need it in the upcoming exercises.

### Summary of Commands

```sh
# Clone the repository
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name

# Create and push dev branch
git checkout -b dev
git push --set-upstream origin dev

# Create feature branch and add files
git checkout -b add-quotes
echo "A good programmer is someone who always looks both ways before crosing a one-way street." > programmer.txt
echo "\"First, solve the problem. Then, write the code.\" – John Johnson" > solve.txt
touch test.txt

# Commit and push changes
git add programmer.txt solve.txt test.txt
git commit -m "Add programmer.txt, solve.txt, and test.txt"
git push --set-upstream origin add-quotes
```
