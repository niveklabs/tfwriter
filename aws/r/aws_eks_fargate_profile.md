# aws_eks_fargate_profile

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "aws_eks_fargate_profile" {
  source = "./modules/aws/r/aws_eks_fargate_profile"

  # cluster_name - (required) is a type of string
  cluster_name = null
  # fargate_profile_name - (required) is a type of string
  fargate_profile_name = null
  # pod_execution_role_arn - (required) is a type of string
  pod_execution_role_arn = null
  # subnet_ids - (optional) is a type of set of string
  subnet_ids = []
  # tags - (optional) is a type of map of string
  tags = {}

  selector = [{
    labels    = {}
    namespace = null
  }]

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "cluster_name" {
  description = "(required)"
  type        = string
}

variable "fargate_profile_name" {
  description = "(required)"
  type        = string
}

variable "pod_execution_role_arn" {
  description = "(required)"
  type        = string
}

variable "subnet_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "selector" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      labels    = map(string)
      namespace = string
    }
  ))
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_eks_fargate_profile" "this" {
  cluster_name           = var.cluster_name
  fargate_profile_name   = var.fargate_profile_name
  pod_execution_role_arn = var.pod_execution_role_arn
  subnet_ids             = var.subnet_ids
  tags                   = var.tags

  dynamic "selector" {
    for_each = var.selector
    content {
      labels    = selector.value["labels"]
      namespace = selector.value["namespace"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_eks_fargate_profile.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_eks_fargate_profile.this.id
}

output "status" {
  description = "returns a string"
  value       = aws_eks_fargate_profile.this.status
}

output "this" {
  value = aws_eks_fargate_profile.this
}
```

[top](#index)