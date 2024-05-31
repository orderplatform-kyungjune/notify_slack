# Slack Notification GitHub Action for D-Day Labels

This GitHub Action sends a Slack notification for pull requests with D-Day labels in your repository.

## Usage

To use this action, add the following step to your workflow YAML file.

## Example Workflow

Create a file named `send_slack_notification.yml` in the `.github/workflows` directory of your repository with the following content

```yaml
name: Send Slack Notification for D-Day Labels

on:
  schedule:
    - cron: '59 22 * * *'  # 매일 한국 시간 07:59에 실행

jobs:
  call-workflow:
    runs-on: ubuntu-latest
    steps:
      - name: use notify_slack
        uses: torder-lkj/notify_slack@v1.0.0 # Please make sure to use the latest version.
        with:
          slack_webhook_url: ${{ secrets.SLACK_WEBHOOK_URL }}
```
Please make sure to replace ${{ secrets.SLACK_WEBHOOK_URL }} with your actual slack webhook url.</br>
Also, ensure you are using the latest version of this action.

## Note
- If there are no open pull requests, no Slack notification will be sent.