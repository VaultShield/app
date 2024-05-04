# VaultShield Deploy App

## Overview

Welcome to the deploy repository, a comprehensive solution featuring separate frontend and backend components. This repository uses Git submodules to manage the relationship between the different parts of the project efficiently.

## Cloning the Repository

To clone this project along with its submodules, you need to run the following command:

```bash
git clone --recurse-submodules https://github.com/your-username/project-name.git
```
This command clones the main repository and initializes and updates each submodule in the repository.

## Initial Setup
After cloning the repository, ensure all submodules are fully updated and in the correct state:
```bash
git submodule update --init --recursive --remote
```
## Running the Project
for windows:
```bash
.\start.ps1
```
for MacOs or Linux users
```bash
./start.sh
```

## Updating Submodules
You can use the latest submodule update available with the develop's branches:
```bash
# Navigate to the submodule directory
cd backend #example

# Pull the latest changes
git pull origin develop # develop is the latest develop branch updated, but it may not be stable

# Go back to the main project directory
cd ../..

# Start the proyect
./start.sh
```

## Update Submodules remote repositories for contributors
To update the submodules to the latest commits available from their respective upstream branches, use the following commands:
```bash
# Navigate to the submodule directory
cd frontend #example

# Pull the latest changes
git pull origin develop # develop is the latest develop branch updated, but it may not be stable

# Go back to the main project directory
cd ../..

# Add the submodule changes
git add frontend

# Commit and push the submodule updates
git commit -m "Updated submodule to latest version"
git push
```
or...
```bash
git submodule update --init --recursive --remote
```

## License
This project is licensed under the MIT License, and the submodules too.