# aws_eks_cluster

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
module "aws_eks_cluster" {
  source = "./modules/aws/r/aws_eks_cluster"

  # enabled_cluster_log_types - (optional) is a type of set of string
  enabled_cluster_log_types = []
  # name - (required) is a type of string
  name = null
  # role_arn - (required) is a type of string
  role_arn = null
  # tags - (optional) is a type of map of string
  tags = {}
  # version - (optional) is a type of string
  version = null

  encryption_config = [{
    provider = [{
      key_arn = null
    }]
    resources = []
  }]

  kubernetes_network_config = [{
    service_ipv4_cidr = null
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]

  vpc_config = [{
    cluster_security_group_id = null
    endpoint_private_access   = null
    endpoint_public_access    = null
    public_access_cidrs       = []
    security_group_ids        = []
    subnet_ids                = []
    vpc_id                    = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "enabled_cluster_log_types" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "role_arn" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "encryption_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      provider = list(object(
        {
          key_arn = string
        }
      ))
      resources = set(string)
    }
  ))
  default = []
}

variable "kubernetes_network_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      service_ipv4_cidr = string
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}

variable "vpc_config" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      cluster_security_group_id = string
      endpoint_private_access   = bool
      endpoint_public_access    = bool
      public_access_cidrs       = set(string)
      security_group_ids        = set(string)
      subnet_ids                = set(string)
      vpc_id                    = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "aws_eks_cluster" "this" {
  enabled_cluster_log_types = var.enabled_cluster_log_types
  name                      = var.name
  role_arn                  = var.role_arn
  tags                      = var.tags
  version                   = var.version

  dynamic "encryption_config" {
    for_each = var.encryption_config
    content {
      resources = encryption_config.value["resources"]

      dynamic "provider" {
        for_each = encryption_config.value.provider
        content {
          key_arn = provider.value["key_arn"]
        }
      }

    }
  }

  dynamic "kubernetes_network_config" {
    for_each = var.kubernetes_network_config
    content {
      service_ipv4_cidr = kubernetes_network_config.value["service_ipv4_cidr"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

  dynamic "vpc_config" {
    for_each = var.vpc_config
    content {
      endpoint_private_access = vpc_config.value["endpoint_private_access"]
      endpoint_public_access  = vpc_config.value["endpoint_public_access"]
      public_access_cidrs     = vpc_config.value["public_access_cidrs"]
      security_group_ids      = vpc_config.value["security_group_ids"]
      subnet_ids              = vpc_config.value["subnet_ids"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_eks_cluster.this.arn
}

output "certificate_authority" {
  description = "returns a list of object"
  value       = aws_eks_cluster.this.certificate_authority
}

output "created_at" {
  description = "returns a string"
  value       = aws_eks_cluster.this.created_at
}

output "endpoint" {
  description = "returns a string"
  value       = aws_eks_cluster.this.endpoint
}

output "id" {
  description = "returns a string"
  value       = aws_eks_cluster.this.id
}

output "identity" {
  description = "returns a list of object"
  value       = aws_eks_cluster.this.identity
}

output "platform_version" {
  description = "returns a string"
  value       = aws_eks_cluster.this.platform_version
}

output "status" {
  description = "returns a string"
  value       = aws_eks_cluster.this.status
}

output "version" {
  description = "returns a string"
  value       = aws_eks_cluster.this.version
}

output "this" {
  value = aws_eks_cluster.this
}
```

[top](#index)