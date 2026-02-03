# Detectify Helm Charts

Official Helm charts for deploying Detectify services on Kubernetes.

## Internal Scanning Agent

The Internal Scanning Agent enables you to scan web applications that are not exposed to the public internet. Deploy the agent within your infrastructure to scan internal APIs, staging environments, and applications behind firewalls using the same vulnerability detection engine as Detectify's external scanning.

### Key Features

- **Private network scanning** – Scan applications that external scanners cannot reach
- **Secure by design** – Outbound-only TLS 1.3 communication, no inbound firewall rules required
- **Data stays local** – Only scan metadata and results are sent to Detectify; your application data never leaves your network

### Architecture

The agent consists of containerized services:

| Component | Description |
|-----------|-------------|
| Scan Scheduler | Manages scans and receives job assignments |
| Scan Manager | Executes security tests |
| Chrome Controller | Handles browser automation for JavaScript-heavy applications |
| Redis | Manages job queues and state |
| Pushgateway | Optional metrics aggregation for Prometheus |

## Usage

```bash
# Add the Detectify Helm repository
helm repo add detectify https://detectify.github.io/helm-charts

# Update your local chart cache
helm repo update

# Search for available charts
helm search repo detectify

# Install a chart
helm install <release-name> detectify/<chart-name> -f values.yaml
```

## Prerequisites

Internal Scanning is an add-on feature that requires account enablement. Contact Detectify to enable this feature for your account.

## Documentation

For detailed documentation on configuration, deployment, and troubleshooting, visit:

- [Internal Scanning Agent Documentation](https://docs.detectify.com/internal-scanning-agent)
- [Detectify Documentation](https://docs.detectify.com)

## Support

If you encounter issues or have questions, contact [Detectify Support](https://support.detectify.com).
