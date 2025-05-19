## Generate Kubernetes Manifests from the Helm Chart

1. **Clone the Repository**

   Clone the repository to your local machine:

   ```bash
   git clone https://github.com/pikilisaikiran/grafana-loki.git
   ```

2. **Navigate to the Charts Directory**

   Change into the `charts` directory where the `Chart.yaml` and `values.yaml` files are located. This chart is structured as an umbrella Helm chart.

   ```bash
   cd charts
   ```

3. **Build Helm Dependencies**

   Run the following command to download the dependent charts, including those from the official Grafana Helm repository:

   ```bash
   helm dependency build
   ```

4. **Generate Kubernetes Manifests**

   Render the templates using Helm and output the generated Kubernetes manifests into a file named `out.yaml`:

   ```bash
   helm template . -f values.yaml > out.yaml
   ```

5. **Inspect the Output**

   Open `out.yaml` to view the Kubernetes resources that will be created. You can find and review the Loki configuration and other related deployments in this file.
