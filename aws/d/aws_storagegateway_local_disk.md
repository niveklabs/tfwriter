# aws_storagegateway_local_disk

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
module "aws_storagegateway_local_disk" {
  source = "./modules/aws/d/aws_storagegateway_local_disk"

  # disk_node - (optional) is a type of string
  disk_node = null
  # disk_path - (optional) is a type of string
  disk_path = null
  # gateway_arn - (required) is a type of string
  gateway_arn = null
}
```

[top](#index)

### Variables

```terraform
variable "disk_node" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "disk_path" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gateway_arn" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "aws_storagegateway_local_disk" "this" {
  # disk_node - (optional) is a type of string
  disk_node = var.disk_node
  # disk_path - (optional) is a type of string
  disk_path = var.disk_path
  # gateway_arn - (required) is a type of string
  gateway_arn = var.gateway_arn
}
```

[top](#index)

### Outputs

```terraform
output "disk_id" {
  description = "returns a string"
  value       = data.aws_storagegateway_local_disk.this.disk_id
}

output "disk_node" {
  description = "returns a string"
  value       = data.aws_storagegateway_local_disk.this.disk_node
}

output "disk_path" {
  description = "returns a string"
  value       = data.aws_storagegateway_local_disk.this.disk_path
}

output "id" {
  description = "returns a string"
  value       = data.aws_storagegateway_local_disk.this.id
}

output "this" {
  value = aws_storagegateway_local_disk.this
}
```

[top](#index)