# Terraform AWS EKS Configuration

This Terraform project is designed to provision and manage an Amazon EKS (Elastic Kubernetes Service) cluster on AWS. Amazon EKS provides a scalable and highly available Kubernetes control plane to deploy, manage, and scale containerized applications using Kubernetes on AWS.

## Prerequisites

Before you begin, ensure you have the following prerequisites installed:

- Terraform (>= 0.12.0)
- AWS CLI
- kubectl

Additionally, you need to have an AWS account and appropriate IAM permissions to create and manage resources such as EKS clusters, IAM roles, VPCs, subnets, etc.

## Configuration

1. **Clone this repository:**

   ```bash
   git clone <repository-url>
   cd terraform-aws-eks
   ```

2. **Initialize Terraform:**

   ```bash
   terraform init
   ```

3. **Configure AWS credentials:**

   Make sure your AWS credentials are properly configured. You can set them using environment variables, AWS CLI configuration, or AWS shared credentials file.

4. **Customize variables (optional):**

   Review and customize the variables in `variables.tf` to match your requirements. You can adjust parameters such as cluster name, instance types, subnets, etc.

5. **Deploy the infrastructure:**

   ```bash
   terraform apply
   ```

6. **Configure kubectl:**

   After provisioning the EKS cluster, configure kubectl to connect to the cluster:

   ```bash
   aws eks --region <region> update-kubeconfig --name <cluster-name>
   ```

## Usage

Once the EKS cluster is provisioned and configured, you can start deploying and managing containerized applications using Kubernetes. Use `kubectl` to interact with the cluster and deploy your workloads.

For example, to deploy a sample application:

```bash
kubectl apply -f <path-to-manifest>
```

## Cleanup

To avoid incurring unnecessary costs, don't forget to destroy the resources when they are no longer needed:

```bash
terraform destroy
```

## Contributing

Contributions are welcome! Please feel free to submit issues, feature requests, or pull requests.

## License

This project is licensed under the [MIT License](LICENSE).
