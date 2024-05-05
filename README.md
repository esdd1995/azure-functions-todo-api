#  Todo API for Azure Functions (Node.js)

[![Deploy to Azure](https://github.com/sinedied/azure-functions-todo-api/actions/workflows/deploy.yml/badge.svg)](https://github.com/sinedied/azure-functions-todo-api/actions/workflows/deploy.yml)
[![MIT License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)

This streamlined Todo API leverages Azure Functions and Node.js to manage tasks. 

**Note:** Entries are stored in-memory, so restarting the server clears all data.

## API Reference

| Route                 | Description                                     |
|------------------------|-------------------------------------------------|
| `GET /api/`            | Retrieves server information                         |
| `GET /api/users/:userId/tasks` | Fetches tasks for a user (creates user if needed) |
| `POST /api/users/:userId/tasks`  | Adds a new task for a user (creates user if needed). Payload: `{ "description": "<task_description>" }` |
| `PATCH /api/users/:userId/tasks/:taskId`  | Updates a specific task. Payload: `{ "completed": <boolean> }` |
| `DELETE /api/users/:userId/tasks/:taskId` | Deletes a specific task                             |

## Run Locally

**Prerequisites:**

- Node.js (https://nodejs.org/en)
- Azure Functions Core Tools (https://learn.microsoft.com/en-us/azure/azure-functions/functions-run-local)

1. Navigate to the project directory: `cd api && npm install`
2. Start the API server: `npm start` (Accessible at `http://localhost:7071/api/`)

## Deploy to Azure

**Requirements:**

- Azure Account (https://azure.microsoft.com/en-us/free)
- Azure CLI (https://learn.microsoft.com/en-us/cli/azure/install-azure-cli-windows)
- GitHub CLI (https://github.com/cli/cli)

**Windows Users:**

For script execution, consider using either Windows Subsystem for Linux (WSL) (https://learn.microsoft.com/en-us/windows/wsl/) or Git Bash (https://git-scm.com/downloads).

1. Run `.azure/setup.sh` and follow the on-screen instructions. The initial deployment will start automatically.

Subsequent commits to the repository will trigger automatic redeployments using GitHub Actions (https://github.com/features/actions).

**Cleanup:**

To remove deployed resources, execute `.azure/setup.sh --terminate`.

