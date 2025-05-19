# 🔍 SonarQube GitHub Actions CI Integration

Automate your code quality checks using GitHub Actions and SonarQube with this robust, optimized workflow. This setup ensures seamless integration of SonarQube into your CI pipeline using Node.js, Java, and GitHub’s powerful Actions runner system.

📍 **Repo URL**: [https://github.com/Lalatenduswain/sonarqube-github-actions-ci](https://github.com/Lalatenduswain/sonarqube-github-actions-ci)

---

## 📌 Features

- ✅ Automatically triggers on `push` and `pull_request` to `main`, `develop`, or `staging`
- 📦 Installs Node.js and project dependencies
- ☕ Java 17 setup for SonarScanner
- ♻️ Smart caching for faster SonarScanner CLI setup
- 🔐 Uses GitHub Secrets for secure SonarQube token handling
- 💬 Verbose logging enabled for debugging (`-X` flag)

---

## 📖 Installation Guide

### 🔧 Prerequisites

Ensure the following are available on your system or self-hosted runner:

- `Node.js` (v22 or compatible)
- `Java 17` (Temurin distribution recommended)
- `wget`, `unzip`
- `npm`
- `sudo` privileges (required for `apt-get` installations on self-hosted runners)
- GitHub Repository Secrets:
  - `SONAR_TOKEN`: Your SonarQube authentication token
  - `SONAR_HOST_URL`: SonarQube server URL

### 🛠️ Setup Instructions

1. **Clone the repository**  
   ```bash
   git clone https://github.com/Lalatenduswain/sonarqube-github-actions-ci.git
   cd sonarqube-github-actions-ci
````

2. **Add GitHub Actions Workflow**
   Place the `sonarqube.yml` file under `.github/workflows/` in your project repo.

3. **Configure your GitHub secrets**
   Go to:
   `Settings` → `Secrets and variables` → `Actions` → Add:

   * `SONAR_TOKEN`
   * `SONAR_HOST_URL`

4. **Customize your `sonar.projectKey` if needed**

---

## 📂 GitHub Actions Workflow Explanation

The core workflow file is: `.github/workflows/sonarqube.yml`

This GitHub Action automates the following steps:

* Checks out code from the repo
* Sets up Node.js (v22) for dependency installation
* Installs Java 17 (required by SonarScanner CLI)
* Caches and installs SonarScanner CLI
* Adds the scanner to system PATH
* Runs the SonarQube scan and uploads results to the specified server

---

## ⚙️ Script Explanation

+ScriptName = **sonarqube-github-actions-ci**

This workflow script:

* Reduces repeated downloads using GitHub's cache action
* Is CI/CD-friendly for JS/TS/Node.js applications
* Allows easy customization and integration into mono-repos or microservices architecture

📁 **Workflow File Location**:
`.github/workflows/sonarqube.yml`

---

## 🧪 Disclaimer | Running the Script

**Author:** Lalatendu Swain
🌐 [GitHub](https://github.com/Lalatenduswain) | [Website](https://blog.lalatendu.info/)

This script is provided as-is and may require modifications or updates based on your specific environment and requirements.
Use it at your own risk. The authors of the script are not liable for any damages or issues caused by its usage.

---

## 💖 Support & Donations

If you find this project helpful, feel free to show your support:
☕ [Buy Me a Coffee](https://www.buymeacoffee.com/lalatendu.swain)

---

## 🛟 Support or Contact

Encountering issues? Don't hesitate to:

* Submit an issue: [GitHub Issues](https://github.com/Lalatenduswain/sonarqube-github-actions-ci/issues)
* Mention your environment setup and logs for faster assistance

---
