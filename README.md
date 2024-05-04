# VaultShield Deploy App

<p align="center">
    <a href="https://github.com/VaultShield/frontend"><img src="https://img.shields.io/badge/-TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white" alt="TypeScript"></a>
    <a href="https://github.com/VaultShield/backend"><img src="https://img.shields.io/badge/-Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white" alt="Java"></a>
    <a href="https://github.com/VaultShield/backend"><img src="https://img.shields.io/badge/-Golang-00ADD8?style=flat-square&logo=go&logoColor=white" alt="Go"></a>
    <a href="#"><img src="https://img.shields.io/badge/build-passing-brightgreen.svg?style=flat-square" alt="Build Status"></a>
    <a href="https://maven.apache.org/"><img src="https://img.shields.io/badge/Maven-3.9.6-blue.svg?style=flat-square" alt="Maven"></a>
    <a href="https://www.docker.com/"><img src="https://img.shields.io/badge/Docker-25.0.2-blue.svg?style=flat-square" alt="Docker"></a>
    <a href="https://opensource.org/licenses/MIT"><img src="https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square" alt="License: MIT"></a>
    <a href="https://yarnpkg.com/"><img src="https://img.shields.io/badge/yarn-%232C8EBB.svg?style=flat-square&logo=yarn&logoColor=white" alt="Yarn"></a>
    <a href="https://vitejs.dev/"><img src="https://img.shields.io/badge/Vite-B73BFE?style=flat-square&logo=vite&logoColor=FFD62E" alt="Vite.js"></a>
</p>


## Overview

Welcome to the deploy repository, a comprehensive solution featuring separate frontend and backend components. This repository uses Git submodules to manage the relationship between the different parts of the project efficiently.

## Prerequisites

Before you begin, ensure you have met the following requirements:
- **Docker**: You will need Docker to run the containers for the database and the application. Download it from [Docker's website](https://www.docker.com/get-started).
- **Ports**: Make sure you have port 8080 **(API)**, 8085 **(Go/Export)**, 8082 **(Java/Encryption)** and 5432 **(POSTGRESQL)** not used by another resource
- No, you don't need Java or Maven! You just have to run the script correctly.

## Cloning the Repository

To clone this project along with its submodules, you need to run the following command:

```bash
git clone --recurse-submodules https://github.com/VaultShield/app.git
```
This command clones the main repository and initializes and updates each submodule in the repository.

## Initial Setup
After cloning the repository, ensure all submodules are fully updated and in the correct state:
```bash
git submodule update --init --recursive --remote
```
The default is to use master, but if you need to deploy another branch, access the branch and make a git switch to the branch you need

## Configure the project
You will need to create a **.env** following the specifications of the .env.example

example:
```env
JWT_SECRET=EXAMPLE_64_CHARACTERS
JWT_RECOVER=EXAMPLE_64_CHARACTERS
POSTGRES_PASSWORD=EXAMPLE_20_CHARACTERS
```

and you need add a **.env.local** in frontend

example:
```env
VITE_SECRET_KEY=PASS
VITE_BASE_URL=http://localhost:8080/
VITE_REGISTER_URL=api/auth/register
VITE_LOGIN_URL=api/auth/login
VITE_REFRESH_TOKEN_URL=api/auth/refreshtoken
VITE_RECOVER_URL=api/auth/recover
VITE_USER_URL=api/user/
VITE_SEARCH_USER_URL=api/user/search
VITE_CREDENTIAL_URL=api/credential/
VITE_ADD_CREDENTIAL_URL=api/credential/insert
VITE_FINDALL_CREDENTIAL_URL=api/credential/find-all/
```

Fill in the necessary data and save it in a file called ".env" and ".env.local"

## Running the Project
for windows:
```bash
.\start.ps1
```
for MacOs or Linux users
```bash
./start.sh
```

**And you get it!!**

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
