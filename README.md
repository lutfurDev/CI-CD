# git_action

A new Flutter project.

## Getting Started

This project is a starting point for a Flutter application.

A few resources to get you started if this is your first Flutter project:

- [Lab: Write your first Flutter app](https://docs.flutter.dev/get-started/codelab)
- [Cookbook: Useful Flutter samples](https://docs.flutter.dev/cookbook)

For help getting started with Flutter development, view the
[online documentation](https://docs.flutter.dev/), which offers tutorials,
samples, guidance on mobile development, and a full API reference.

## CI/CD

A GitHub Actions workflow is added at `.github/workflows/build-apk-notify-teams.yml`.

### What it does

- Runs when code is merged/pushed to `master`.
- Runs quality checks: format, analyze, test.
- Builds `app-release.apk`.
- Uploads APK as a GitHub Actions artifact.
- Sends a message to Microsoft Teams with the workflow run link.

### Required secret

Add this repository secret in GitHub:

- `TEAMS_WEBHOOK_URL`

> Important: the Teams chat/channel URL is **not** a webhook URL.
> You must create an **Incoming Webhook** (or a Teams Workflow webhook) and use that URL as `TEAMS_WEBHOOK_URL`.

### How to set the secret

1. Open your GitHub repo.
2. Go to **Settings** -> **Secrets and variables** -> **Actions**.
3. Click **New repository secret**.
4. Name: `TEAMS_WEBHOOK_URL`
5. Value: paste your Teams webhook URL.

After that, every push/merge to `master` will build APK and send notification automatically.
