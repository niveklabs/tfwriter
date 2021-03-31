# aws_storagegateway_upload_buffer

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
    aws = ">= 3.34.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_storagegateway_upload_buffer" {
  source = "./modules/aws/r/aws_storagegateway_upload_buffer"

  # disk_id - (optional) is a type of string
  disk_id = null
  # disk_path - (optional) is a type of string
  disk_path = null
  # gateway_arn - (required) is a type of string
  gateway_arn = null
}
```

[top](#index)

### Variables

```terraform
variable "disk_id" {
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

### Resource

```terraform
resource "aws_storagegateway_upload_buffer" "this" {
  disk_id     = var.disk_id
  disk_path   = var.disk_path
  gateway_arn = var.gateway_arn
}
```

[top](#index)

### Outputs

```terraform
output "disk_id" {
  description = "returns a string"
  value       = aws_storagegateway_upload_buffer.this.disk_id
}

output "disk_path" {
  description = "returns a string"
  value       = aws_storagegateway_upload_buffer.this.disk_path
}

output "id" {
  description = "returns a string"
  value       = aws_storagegateway_upload_buffer.this.id
}

output "this" {
  value = aws_storagegateway_upload_buffer.this
}
```

[top](#index)