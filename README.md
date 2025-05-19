# 🔍 SonarQube GitHub Actions CI Integration

Automate code quality and security analysis with this GitHub Actions workflow for SonarQube. This setup integrates SonarQube into your CI pipeline, supporting Node.js and Java-based projects, and is optimized for performance and ease of use.

📍 **Repo URL**: [https://github.com/Lalatenduswain/sonarqube-github-actions-ci](https://github.com/Lalatenduswain/sonarqube-github-actions-ci)

---

## 📌 Features

- ✅ Triggers on `push` and `pull_request` events for `main`, `staging`, and `develop` branches
- 📦 Sets up Node.js (v22) and installs project dependencies
- ☕ Configures Java 17 for SonarScanner CLI
- ♻️ Caches SonarScanner CLI for faster builds
- 🔐 Securely handles SonarQube credentials via GitHub Secrets
- 💬 Includes verbose logging for debugging (`-X` flag)
- 🏠 Supports self-hosted or GitHub-hosted runners (`ubuntu-latest`)

---

## 📖 Installation Guide

### 🔧 Prerequisites

Ensure the following are available on your system or runner:

- `Node.js` (v22 or compatible)
- `Java 17` (Temurin distribution recommended)
- `wget`, `unzip` (for self-hosted runners)
- `npm` for dependency installation
- `sudo` privileges (for `apt-get` on self-hosted runners)
- GitHub Repository Secrets:
  - `SONAR_TOKEN`: SonarQube authentication token
  - `SONAR_HOST_URL`: SonarQube server URL (e.g., `https://sonarqube.yourdomain.com`)

### 🛠️ Setup Instructions

1. **Clone or Fork the Repository**  
   ```bash
   git clone https://github.com/Lalatenduswain/sonarqube-github-actions-ci.git
   cd sonarqube-github-actions-ci
   ```

2. **Add the Workflow File**  
   Copy the provided `sonarqube.yml` to your project’s `.github/workflows/` directory.

3. **Configure GitHub Secrets**  
   Navigate to:  
   `Settings` → `Secrets and variables` → `Actions` → `New repository secret`  
   Add:
   - `SONAR_TOKEN` (from SonarQube: `User > My Account > Security`)
   - `SONAR_HOST_URL` (your SonarQube server URL)

4. **Customize Workflow (Optional)**  
   - Update `sonar.projectKey` (e.g., `euml-vipasana`) to match your SonarQube project.
   - Modify `sonar.sources` to target specific directories (e.g., `src`).
   - Switch `runs-on` to `ubuntu-latest` if using GitHub-hosted runners.

5. **Push Changes**  
   Commit and push to `main`, `staging`, or `develop` to trigger the workflow.

---

## 📂 GitHub Actions Workflow Explanation

The workflow file is located at: `.github/workflows/sonarqube.yml`

### Workflow Steps

- **Checkout Code**: Retrieves the repository code.
- **Set up Node.js**: Installs Node.js v22 for JavaScript/TypeScript projects.
- **Install Dependencies**: Runs `npm install` for project dependencies.
- **Set up Java 17**: Installs Java 17 for SonarScanner.
- **Install unzip**: Ensures `unzip` is available for extracting SonarScanner.
- **Cache SonarScanner**: Caches SonarScanner CLI (v5.0.1.3006) for faster builds.
- **Download SonarScanner**: Downloads and extracts SonarScanner if not cached.
- **Add to PATH**: Makes SonarScanner executable accessible.
- **Run SonarQube Scan**: Executes the scan and uploads results to the SonarQube server.

---

## ⚙️ Script Explanation

**Script Name**: `SonarQube Scan`

This workflow:
- Optimizes build times with caching for SonarScanner CLI.
- Supports Node.js-based projects with Java-based analysis.
- Is flexible for monorepos or microservices by allowing source directory customization.
- Uses secure secret management for SonarQube credentials.

📁 **Workflow File Location**:  
`.github/workflows/sonarqube.yml`

---

## 🧪 Disclaimer | Running the Script

**Author**: Lalatendu Swain  
🌐 [GitHub](https://github.com/Lalatenduswain) | [Website](https://blog.lalatendu.info/)

This script is provided as-is and may require adjustments for your environment. The author is not liable for any issues or damages caused by its use. Test thoroughly before using in production.

---

## 💖 Support & Donations

If this project helps you, consider showing support:  
☕ [Buy Me a Coffee](https://www.buymeacoffee.com/lalatendu.swain)

---

## 🛟 Support or Contact

Having issues? Reach out:
- File an issue: [GitHub Issues](https://github.com/Lalatenduswain/sonarqube-github-actions-ci/issues)
- Include your environment details and logs for quicker resolution.

---

## 🔗 Additional Resources

- [SonarQube Documentation](https://docs.sonarqube.org/)
- [GitHub Actions Documentation](https://docs.github.com/en/actions)
- [Setup Node.js Action](https://github.com/actions/setup-node)
- [Setup Java Action](https://github.com/actions/setup-java)

---
