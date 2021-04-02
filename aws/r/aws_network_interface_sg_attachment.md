# aws_network_interface_sg_attachment

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
module "aws_network_interface_sg_attachment" {
  source = "./modules/aws/r/aws_network_interface_sg_attachment"

  # network_interface_id - (required) is a type of string
  network_interface_id = null
  # security_group_id - (required) is a type of string
  security_group_id = null
}
```

[top](#index)

### Variables

```terraform
variable "network_interface_id" {
  description = "(required)"
  type        = string
}

variable "security_group_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_network_interface_sg_attachment" "this" {
  network_interface_id = var.network_interface_id
  security_group_id    = var.security_group_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_network_interface_sg_attachment.this.id
}

output "this" {
  value = aws_network_interface_sg_attachment.this
}
```

[top](#index)