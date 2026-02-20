# Power BI Git Demo

A demonstration Power BI project showing how to integrate a Power BI report and semantic model with GitHub using Microsoft Fabric's Git integration feature.

## Contents

| Item | Description |
|---|---|
| `My new report.Report/` | Power BI report definition (PBIR format) |
| `My new report.SemanticModel/` | Semantic model definition (TMDL format) with embedded sample sales data |
| `My new report.pbip` | Power BI project file for opening in Power BI Desktop |

## Syncing This Repo to Microsoft Fabric

### Prerequisites

- A Microsoft Fabric workspace (Trial, Power BI Premium, or Fabric capacity)
- A GitHub account with access to this repository
- Fabric workspace Admin or Member role

### Step 1 — Connect Your Fabric Workspace to GitHub

1. Open your **Fabric workspace** in [app.fabric.microsoft.com](https://app.fabric.microsoft.com)
2. Click **Workspace settings** (gear icon in the top right of the workspace)
3. Select **Git integration** from the left menu
4. Under **Git provider**, select **GitHub**
5. Click **Connect to GitHub** and authorize Fabric to access your GitHub account
6. Fill in the connection details:
   - **Organization**: your GitHub username or org
   - **Repository**: `powerbi-git-demo`
   - **Branch**: `main`
   - **Git folder**: `/` (root)
7. Click **Connect and sync**

### Step 2 — Initial Sync

1. After connecting, Fabric will compare the workspace with the repository
2. Click **Sync** to pull the report and semantic model into your workspace
3. The items **My new report** (Report) and **My new report** (Semantic Model) will appear in your workspace

### Step 3 — Refresh the Semantic Model

After syncing, the semantic model is deployed but not yet loaded with data. You must trigger a refresh:

1. In your workspace, find the **My new report** semantic model
2. Click the `...` menu → **Refresh now**
3. Wait for the refresh to complete (status shows a green checkmark)
4. Open the **My new report** report — it should now display data

### Updating the Report from Git

Whenever changes are pushed to the `main` branch:

1. Go to your Fabric workspace
2. Click **Workspace settings** → **Git integration**
3. Click **Update all** to pull the latest changes from GitHub

### Publishing Changes from Fabric Back to Git

1. Make changes to your report or semantic model in Fabric
2. Go to **Workspace settings** → **Git integration**
3. Staged changes will appear — click **Commit** to push them back to GitHub

## Local Development with Power BI Desktop

1. Clone this repository
2. Open `My new report.pbip` in Power BI Desktop (version 2.137+)
3. Make edits and save — changes are written directly to the TMDL/PBIR source files
4. Commit and push via Git to sync back to Fabric

## License

This project is licensed under the MIT License — see [LICENSE](LICENSE) for details.
