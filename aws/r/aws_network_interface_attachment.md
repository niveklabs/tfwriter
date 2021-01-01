# aws_network_interface_attachment

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "aws_network_interface_attachment" {
  source = "./modules/aws/r/aws_network_interface_attachment"

  # device_index - (required) is a type of number
  device_index = null
  # instance_id - (required) is a type of string
  instance_id = null
  # network_interface_id - (required) is a type of string
  network_interface_id = null
}
```

[top](#index)

### Variables

```hcl
variable "device_index" {
  description = "(required)"
  type        = number
}

variable "instance_id" {
  description = "(required)"
  type        = string
}

variable "network_interface_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```hcl
resource "aws_network_interface_attachment" "this" {
  device_index         = var.device_index
  instance_id          = var.instance_id
  network_interface_id = var.network_interface_id
}
```

[top](#index)

### Outputs

```hcl
output "attachment_id" {
  description = "returns a string"
  value       = aws_network_interface_attachment.this.attachment_id
}

output "id" {
  description = "returns a string"
  value       = aws_network_interface_attachment.this.id
}

output "status" {
  description = "returns a string"
  value       = aws_network_interface_attachment.this.status
}

output "this" {
  value = aws_network_interface_attachment.this
}
```

[top](#index)