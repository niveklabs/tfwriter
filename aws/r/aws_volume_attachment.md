# aws_volume_attachment

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
module "aws_volume_attachment" {
  source = "./modules/aws/r/aws_volume_attachment"

  # device_name - (required) is a type of string
  device_name = null
  # force_detach - (optional) is a type of bool
  force_detach = null
  # instance_id - (required) is a type of string
  instance_id = null
  # skip_destroy - (optional) is a type of bool
  skip_destroy = null
  # volume_id - (required) is a type of string
  volume_id = null
}
```

[top](#index)

### Variables

```terraform
variable "device_name" {
  description = "(required)"
  type        = string
}

variable "force_detach" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "instance_id" {
  description = "(required)"
  type        = string
}

variable "skip_destroy" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "volume_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_volume_attachment" "this" {
  device_name  = var.device_name
  force_detach = var.force_detach
  instance_id  = var.instance_id
  skip_destroy = var.skip_destroy
  volume_id    = var.volume_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_volume_attachment.this.id
}

output "this" {
  value = aws_volume_attachment.this
}
```

[top](#index)