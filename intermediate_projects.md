# Intermediate SRE Projects

## 4. Kubernetes Orchestration
**Project: Kubernetes Cluster for Microservices**

### Setup:
- [ ] Install kubectl and minikube on your local machine
- [ ] Set up a small managed Kubernetes cluster (e.g., EKS, AKS, or GKE) for testing

### Tasks:
- [ ] Local Kubernetes setup:
  - [ ] Start a minikube cluster on your local machine
  - [ ] Familiarize yourself with basic kubectl commands
- [ ] Deploy to local cluster:
  - [ ] Create Kubernetes manifests (Deployments, Services) for your microservices
  - [ ] Deploy your application to the minikube cluster
- [ ] Implement Horizontal Pod Autoscaling:
  - [ ] Set up metrics-server in your cluster
  - [ ] Configure HPA for one of your services
- [ ] Set up Ingress:
  - [ ] Install an Ingress controller (e.g., Nginx Ingress)
  - [ ] Configure Ingress resources for your services
- [ ] Use Helm:
  - [ ] Create a Helm chart for your application
  - [ ] Use the chart to deploy to your local and managed clusters
- [ ] Implement blue/green deployment:
  - [ ] Modify your Helm chart to support blue/green deployments
  - [ ] Perform a blue/green deployment of a service update
- [ ] Managed cluster deployment:
  - [ ] Deploy your application to the managed Kubernetes cluster
  - [ ] Verify that all components are working as expected
- [ ] Documentation:
  - [ ] Document the Kubernetes resources used in your project
  - [ ] Write instructions for deploying the application using Helm
- [ ] Clean up:
  - [ ] Remove all resources from your managed Kubernetes cluster
  - [ ] Stop and delete your local minikube cluster

## 5. Monitoring and Observability
**Project: Comprehensive Monitoring Solution**

### Setup:
- [ ] Set up a small Kubernetes cluster (can use minikube or a small managed cluster)
- [ ] Install Helm on your local machine

### Tasks:
- [ ] Deploy Prometheus:
  - [ ] Use Helm to deploy Prometheus Operator
  - [ ] Configure custom ServiceMonitors for your application
- [ ] Set up Grafana:
  - [ ] Deploy Grafana using Helm
  - [ ] Configure data sources to connect to Prometheus
- [ ] Create custom dashboards:
  - [ ] Design and implement custom Grafana dashboards for your microservices
  - [ ] Include panels for key metrics (e.g., request rate, error rate, latency)
- [ ] Implement alerting:
  - [ ] Set up AlertManager
  - [ ] Configure alert rules in Prometheus
  - [ ] Set up notification channels (e.g., email, Slack)
- [ ] Distributed tracing:
  - [ ] Deploy Jaeger to your cluster
  - [ ] Instrument your application code to send traces to Jaeger
- [ ] Logging:
  - [ ] Set up the ELK stack (Elasticsearch, Logstash, Kibana) in your cluster
  - [ ] Configure your applications to send logs to the ELK stack
- [ ] Testing:
  - [ ] Generate load on your application to test monitoring and alerting
  - [ ] Verify that logs and traces are being collected correctly
- [ ] Documentation:
  - [ ] Document your monitoring setup, including all components and their configurations
  - [ ] Create a runbook for common alerting scenarios
- [ ] Clean up:
  - [ ] Remove all monitoring components from your cluster
  - [ ] Delete any persistent volumes used for storing metrics or logs

## 6. Configuration Management with Ansible
**Project: Automated Server Configuration**

### Setup:
- [ ] Install Ansible on your local machine
- [ ] Set up 2-3 small EC2 instances or local VMs for testing

### Tasks:
- [ ] Basic Ansible setup:
  - [ ] Create an inventory file with your test instances
  - [ ] Write a simple playbook to update and upgrade all systems
- [ ] Web server configuration:
  - [ ] Create a playbook to install and configure Nginx on target hosts
  - [ ] Include tasks to deploy a sample website
- [ ] Database server configuration:
  - [ ] Write a playbook to install and configure PostgreSQL
  - [ ] Include tasks to create a database and user
- [ ] Implement roles:
  - [ ] Refactor your playbooks into reusable roles (e.g., common, web, db)
  - [ ] Update your playbooks to use these roles
- [ ] Use Ansible Vault:
  - [ ] Encrypt sensitive data (e.g., database passwords) using Ansible Vault
  - [ ] Update your playbooks to use the encrypted data
- [ ] Dynamic inventory:
  - [ ] Set up dynamic inventory for AWS EC2
  - [ ] Test your playbooks using the dynamic inventory
- [ ] Integrate with CI/CD:
  - [ ] Set up a GitHub Actions workflow to lint and test your Ansible code
  - [ ] Implement a workflow to automatically apply configuration changes
- [ ] Testing:
  - [ ] Use Ansible's check mode to verify playbooks before applying
  - [ ] Implement and run Ansible tests for your roles
- [ ] Documentation:
  - [ ] Document your Ansible setup, including roles and playbooks
  - [ ] Create a guide for adding new servers to the configuration
- [ ] Clean up:
  - [ ] Remove any changes made to test instances
  - [ ] Terminate EC2 instances if used

## 7. Service Mesh with Linkerd
**Project: Service Mesh Implementation**

### Setup:
- [ ] Set up a Kubernetes cluster (can use minikube or a small managed cluster)
- [ ] Install the Linkerd CLI on your local machine

### Tasks:
- [ ] Install Linkerd:
  - [ ] Use the Linkerd CLI to install the control plane on your cluster
  - [ ] Verify the installation using Linkerd's built-in checks
- [ ] Mesh your application:
  - [ ] Add the necessary annotations to your application's Kubernetes manifests
  - [ ] Inject the Linkerd proxy into your application pods
- [ ] Implement traffic splitting:
  - [ ] Deploy two versions of one of your services
  - [ ] Use Linkerd's traffic splitting feature to implement a canary deployment
- [ ] Set up mutual TLS:
  - [ ] Verify that Linkerd has enabled mTLS between your services
  - [ ] Implement a policy to require mTLS for specific services
- [ ] Monitoring and visualization:
  - [ ] Explore Linkerd's built-in dashboards
  - [ ] Set up additional Grafana dashboards for service-specific metrics
- [ ] Implement retries and timeouts:
  - [ ] Configure retry policies for services that may experience transient failures
  - [ ] Set appropriate timeouts for inter-service communications
- [ ] Testing:
  - [ ] Perform chaos testing by intentionally breaking a service and observing Linkerd's behavior
  - [ ] Test the canary deployment process with gradual traffic shifting
- [ ] Documentation:
  - [ ] Document your Linkerd setup and configurations
  - [ ] Create a guide for onboarding new services to the mesh
- [ ] Clean up:
  - [ ] Remove Linkerd from your application namespaces
  - [ ] Uninstall the Linkerd control plane
