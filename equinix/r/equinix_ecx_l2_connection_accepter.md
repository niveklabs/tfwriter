# equinix_ecx_l2_connection_accepter

[back](../equinix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    equinix = ">= 1.0.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "equinix_ecx_l2_connection_accepter" {
  source = "./modules/equinix/r/equinix_ecx_l2_connection_accepter"

  # access_key - (required) is a type of string
  access_key = null
  # connection_id - (required) is a type of string
  connection_id = null
  # secret_key - (required) is a type of string
  secret_key = null

  timeouts = [{
    create = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "access_key" {
  description = "(required)"
  type        = string
}

variable "connection_id" {
  description = "(required)"
  type        = string
}

variable "secret_key" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "equinix_ecx_l2_connection_accepter" "this" {
  access_key    = var.access_key
  connection_id = var.connection_id
  secret_key    = var.secret_key

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "aws_connection_id" {
  description = "returns a string"
  value       = equinix_ecx_l2_connection_accepter.this.aws_connection_id
}

output "id" {
  description = "returns a string"
  value       = equinix_ecx_l2_connection_accepter.this.id
}

output "this" {
  value = equinix_ecx_l2_connection_accepter.this
}
```

[top](#index)