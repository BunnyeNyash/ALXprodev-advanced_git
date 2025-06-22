# Git-Flows Project

## Overview
This project introduces learners to **Git-Flow**, a branching model for Git proposed by Vincent Driessen. Git-Flow provides a structured approach to managing features, releases, and hotfixes in collaborative software development. It is ideal for large-scale projects with multiple developers, ensuring organized codebases, seamless collaboration, and stable releases.

## Repository:
- GitHub Repository: [ALXprodev-advanced_git](https://github.com/BunnyeNyash/ALXprodev-advanced_git.git)

## Learning Objectives
By completing this project, learners will:
- Understand the purpose and structure of Git-Flow.
- Identify the roles of different branch types (`main`, `develop`, `feature/*`, `release/*`, `hotfix/*`).
- Apply Git-Flow in collaborative development projects.
- Manage feature development, releases, and hotfixes using Git best practices.

## Learning Outcomes
Learners will be able to:
- Explain how Git-Flow manages large codebases and team contributions.
- Create and manage branches following the Git-Flow model.
- Use Git commands to initiate and complete features, releases, and hotfixes.
- Integrate Git-Flow into CI/CD pipelines for automated testing and deployments.

## Git-Flow Branch Types
- **main (or master)**: Stores production-ready code.
- **develop**: Integrates features for ongoing development.
- **feature/***: Used for developing new features.
- **release/***: Prepares code for production releases.
- **hotfix/***: Handles critical bug fixes for production code.

## Setup Instructions
1. **Install Git-Flow**:
   - Follow the installation guide for your system: [Git-Flow](https://skoch.github.io/Git-Workflow/).
   - Verify installation: `git flow version`.

2. **Clone the Repository**:
   - `git clone https://github.com/BunnyeNyash/ALXprodev-advanced_git.git`.

3. **Initialize Git-Flow**:
   - Navigate to the repository: `cd ALXprodev-advanced_git`.
   - Initialize Git-Flow with default settings: `git flow init -d`.

## Tasks

### Task 0: Setting up Git-Flow
**Objective**: Initialize a Git-Flow workflow.  
**Instructions**:
1. Install `git-flow` if not already installed.
2. Create an empty repository named `ALXprodev-advanced_git` on GitHub.
3. Clone the repository locally.
4. Create a `develop` branch: `git checkout -b develop`.
5. Push the `develop` branch: `git push origin develop`.
6. Initialize Git-Flow: `git flow init -d`.
7. Create an empty `README.md` file.
8. Commit and push: `git add README.md && git commit -m "Initial README" && git push origin develop`.

**Repo**:
- GitHub Repository: `ALXprodev-advanced_git`
- File: `README.md`

  
### Task 1: Creating a Feature Branch
**Objective**: Learn to work with feature branches in Git-Flow.  
**Instructions**:
1. Create a feature branch: `git flow feature start implement-login`.
2. Create a directory `login-page` and add a `README.md` file with the content: `Login Feature Coming soon`.
3. Commit changes: `git add login-page/README.md && git commit -m "feat: scaffolding login page"`.
4. Push the branch: `git push origin feature/implement-login`.

**Repo**:
- GitHub Repository: `ALXprodev-advanced_git`
- Directory: `login-page`
- File: `login-page/README.md`


### Task 2: Creating a Release Branch
**Objective**: Understand the release process in Git-Flow.  
**Instructions**:
1. Create a feature branch: `git flow feature start implement-signup`.
2. Create a directory `signup-page` and add a `README.md` file with the content: `feature coming soon`.
3. Commit and push: `git add signup-page/README.md && git commit -m "feat: scaffolding signup page" && git push origin feature/implement-signup`.
4. Merge both feature branches (`feature/implement-login`, `feature/implement-signup`) into `develop`:
   - `git flow feature finish implement-login`
   - `git flow feature finish implement-signup`
   - Resolve conflicts if any.
5. Create a release branch: `git flow release start 1.0.0`.
6. Update `signup-page/README.md` by adding: `data requirements: email, firstName, lastName, profilePic`.
7. Commit and push: `git add signup-page/README.md && git commit -m "Update signup README for release" && git push origin release/1.0.0`.
8. Merge the release branch: `git flow release finish 1.0.0`.
9. Tag the release: `git tag v1.0.0 && git push origin main --tags`.

**Repo**:
- GitHub Repository: `ALXprodev-advanced_git`
- Directories: `login-page`, `signup-page`
- Files: `login-page/README.md`, `signup-page/README.md`


### Task 3: Git Hooks and Automation
**Objective**: Implement Git hooks to automate Git-Flow processes.  
**Instructions**:
1. Create a `pre-commit` hook in `.git/hooks/pre-commit` to check if each directory has a `README.md` file.
2. Create a `post-merge` hook in `.git/hooks/post-merge` to log merges into the `main` branch.
3. Ensure hooks are executable: `chmod +x .git/hooks/pre-commit .git/hooks/post-merge`.

**Repo**:
- GitHub Repository: `ALXprodev-advanced_git`


## Git-Flow Best Practices
| Best Practice | Description |
|---------------|-------------|
| Start with develop | Branch off from `develop` for new features, not `main`. |
| Feature Isolation | Keep each feature in its own branch to reduce merge conflicts. |
| Merge via Pull Requests | Use pull requests for all merges to ensure code review. |
| Keep main clean | Only push production-ready code to `main`. |
| Tag Releases | Use Git tags on `main` to mark official release points (e.g., `v1.0.0`). |
| Use hotfix/* for urgent bugs | Apply emergency fixes via `hotfix/` branches and merge back to `develop`. |
| Document your workflow | Maintain clear documentation in the project’s README. |

## Common Git-Flow Commands
```bash
git flow init                   # Initialize Git-Flow
git flow feature start <name>   # Start a new feature branch
git flow feature finish <name>  # Finish feature and merge into develop
git flow release start <x.x.x>  # Start a release branch
git flow release finish <x.x.x> # Merge release into main and develop
git flow hotfix start <x.x.x>   # Start a hotfix branch
git flow hotfix finish <x.x.x>  # Finish hotfix and merge into main & develop
```

## Resources
- [Git-Flow by Vincent Driessen](https://nvie.com/posts/a-successful-git-branching-model/)
- [Git-Flow Installation Guide](https://github.com/nvie/gitflow/wiki/Installation)
- [Git Hooks Documentation](https://git-scm.com/docs/githooks)
