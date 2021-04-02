# aws_lightsail_instance_public_ports

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
module "aws_lightsail_instance_public_ports" {
  source = "./modules/aws/r/aws_lightsail_instance_public_ports"

  # instance_name - (required) is a type of string
  instance_name = null

  port_info = [{
    cidrs     = []
    from_port = null
    protocol  = null
    to_port   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "instance_name" {
  description = "(required)"
  type        = string
}

variable "port_info" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      cidrs     = set(string)
      from_port = number
      protocol  = string
      to_port   = number
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "aws_lightsail_instance_public_ports" "this" {
  instance_name = var.instance_name

  dynamic "port_info" {
    for_each = var.port_info
    content {
      cidrs     = port_info.value["cidrs"]
      from_port = port_info.value["from_port"]
      protocol  = port_info.value["protocol"]
      to_port   = port_info.value["to_port"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_lightsail_instance_public_ports.this.id
}

output "this" {
  value = aws_lightsail_instance_public_ports.this
}
```

[top](#index)