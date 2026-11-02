# My full Linux CFG.

Clone including all submodules:
```
# 1. Initialize a blank local repository in your current folder
git init

# 2. Link it to your GitHub repository
git remote add origin https://github.com/Tsukidy/linux-cfg/

# 3. Fetch the data from the remote repository
git fetch

# 4. Check out the files directly into your folder
git checkout -f main

# 5. Grab the submodules
git submodule update --init --recursive
```

## Useful Submodule Commands:

### 1. Update submodules to match the main repository

If you want your submodules to check out the exact commits recorded by your parent project, run:
```
git submodule update --init --recursive
```
• --init: Initializes any submodules that haven't been initialized yet.
• --recursive: Looks inside your submodules for any nested submodules and updates those too.

### 2. Pull the latest commits from the submodules' remote branches

If you want to bypass the commit hashes locked by the parent repository and pull the absolute latest HEAD from each submodule's tracked remote branch, use:
```
git submodule update --recursive --remote
```
• --remote: Tells Git to look at the remote tracking branch (configured in .gitmodules) instead of the locked commit.

### 3. Actually "pull" instead of "update"

Alternatively, if you want to explicitly run a git pull on the remote tracking branch (e.g., main or master) across every submodule directory:
```
git submodule foreach --recursive git pull origin main
```
