# configure-alertmanager-with-Prometheus

## Step 1: Clone the GitHub Repository

```bash
https://github.com/singhnirbhai/configure-alertmanager-with-Prometheus
```
## Step 2: Configure Alerts

```bash
cd prometheus && vim config-map.yaml
```
## Step 3: Apply Prometheus Manifests
```bash
kubectl create ns monitoring
kubectl apply -f .
```
## Step 4: Create Slack Webhook URL

To integrate Alertmanager with a Slack channel, create a Slack webhook URL.

Create a channel on Slack.

Visit the Slack API page: Slack API

Sign in to your workspace and create a new app from scratch. Specify the app name and select the workspace.

In the settings menu on the left side, click on "Incoming Webhooks".

Activate Incoming Webhooks and copy the webhook URL.

## Add Slack Webhook URL to Alertmanager Configmap
```bash
cd alert-manager
vim AlertManagerConfigmap.yaml
```
Apply the Alertmanager configuration:

```bash
kubectl apply -f .
```
## Step 6: Access the UI
Verify that everything is running correctly. Port forward Prometheus and Alertmanager to access their UIs.
```bash
kubectl port-forward service/prometheus-service 9090
kubectl port-forward service/alertmanager 9093
```
