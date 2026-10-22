# My full Linux CFG.

Clone including all submodules:
```
bash
git clone --recurse-submodules -j8 https://github.com/Tsukidy/linux-cfg/
```

## Useful Submodule Commands:

### 1. Update submodules to match the main repository

If you want your submodules to check out the exact commits recorded by your parent project, run:
```
bash
git submodule update --init --recursive
```
• --init: Initializes any submodules that haven't been initialized yet.
• --recursive: Looks inside your submodules for any nested submodules and updates those too.

### 2. Pull the latest commits from the submodules' remote branches

If you want to bypass the commit hashes locked by the parent repository and pull the absolute latest HEAD from each submodule's tracked remote branch, use:
```
bash
git submodule update --recursive --remote
```
• --remote: Tells Git to look at the remote tracking branch (configured in .gitmodules) instead of the locked commit.

### 3. Actually "pull" instead of "update"

Alternatively, if you want to explicitly run a git pull on the remote tracking branch (e.g., main or master) across every submodule directory:
```
bash
git submodule foreach --recursive git pull origin main
```
