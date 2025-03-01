# Adding an Upstream Git Server to a Private Repository for Student Projects

## Prerequisites
- A private Git repository already set up on a primary server.
- Access to the upstream Git server.
- SSH keys configured for authentication (if using SSH).

## Step 1: Add the Upstream Repository

To add an upstream Git server as a remote repository, use the following command:

```sh
cd /path/to/your/repo

git remote add upstream git@upstream-server.com:your-repo.git
```

Replace `git@upstream-server.com:your-repo.git` with the actual URL of the upstream Git server.

## Step 2: Verify the Remote Repositories

Check that the upstream remote was added successfully:

```sh
git remote -v
```

This should output something like:

```
origin    git@primary-server.com:your-repo.git (fetch)
origin    git@primary-server.com:your-repo.git (push)
upstream  git@upstream-server.com:your-repo.git (fetch)
upstream  git@upstream-server.com:your-repo.git (push)
```

## Step 3: Fetch Changes from the Upstream Server

To ensure your local repository is up to date with upstream changes:

```sh
git fetch upstream
```

To merge upstream changes into your current branch:

```sh
git merge upstream/main
```

## Step 4: Push Changes to Upstream (If Allowed)

If you have push access to the upstream repository, you can push changes:

```sh
git push upstream main
```

However, in most cases, student repositories are forks of an upstream project, and push access may not be available. Instead, students may need to create pull requests to contribute changes.

## Step 5: Remove or Update the Upstream Remote (If Needed)

To remove the upstream remote:

```sh
git remote remove upstream
```

To update the upstream remote URL:

```sh
git remote set-url upstream git@new-upstream-server.com:your-repo.git
```

## Conclusion
You have successfully added an upstream Git server to your private repository, enabling synchronization with upstream changes and collaboration on student projects.
