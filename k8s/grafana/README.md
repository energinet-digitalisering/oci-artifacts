# Grafana

Grafana allows you to query, visualize, alert on and understand your metrics no matter where they are stored.

These manifests install the official Grafana Helm chart without any modifications.

To view the Grafana Web UI, you can should port forward port 3000 from the Grafana pod to your local machine. Grafana autogenerates a password for the admin user, and stores it in a Secret. You can copy the password to your clipboard by running: `kubectl -n grafana get secret grafana -o yaml | yq '.data.admin-password' | base64 -d | pbcopy`. To print the password in your terminal, replace `| pbcopy` with `; echo` - the `echo` is to ensure the Grafana password is printed on its own line without your shell prompt.
