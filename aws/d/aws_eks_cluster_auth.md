# aws_eks_cluster_auth

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aws = ">= 3.35.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_eks_cluster_auth" {
  source = "./modules/aws/d/aws_eks_cluster_auth"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "aws_eks_cluster_auth" "this" {
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.aws_eks_cluster_auth.this.id
}

output "token" {
  description = "returns a string"
  value       = data.aws_eks_cluster_auth.this.token
  sensitive   = true
}

output "this" {
  value = aws_eks_cluster_auth.this
}
```

[top](#index)