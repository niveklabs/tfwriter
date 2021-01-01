# aws_lightsail_static_ip_attachment

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
module "aws_lightsail_static_ip_attachment" {
  source = "./modules/aws/r/aws_lightsail_static_ip_attachment"

  # instance_name - (required) is a type of string
  instance_name = null
  # static_ip_name - (required) is a type of string
  static_ip_name = null
}
```

[top](#index)

### Variables

```hcl
variable "instance_name" {
  description = "(required)"
  type        = string
}

variable "static_ip_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```hcl
resource "aws_lightsail_static_ip_attachment" "this" {
  instance_name  = var.instance_name
  static_ip_name = var.static_ip_name
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = aws_lightsail_static_ip_attachment.this.id
}

output "ip_address" {
  description = "returns a string"
  value       = aws_lightsail_static_ip_attachment.this.ip_address
}

output "this" {
  value = aws_lightsail_static_ip_attachment.this
}
```

[top](#index)