# daemonset for windows_exporter
This is a Kubernetes daemonset for the [Windows exporter](https://github.com/prometheus-community/windows_exporter), hardware and Windows metrics.

## How it works?
There are 2 containers inside the daemonset

### wmiinstaller
Responsible for installing the windows_exporter on the windows node.

### node-exporter-proxy
Port-forward scraping requests to the `/metrics` endpoint to the node, which has wmi installed by wmiinstaller.