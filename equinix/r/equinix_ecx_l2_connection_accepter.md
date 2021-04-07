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
    equinix = ">= 1.1.0-beta"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "equinix_ecx_l2_connection_accepter" {
  source = "./modules/equinix/r/equinix_ecx_l2_connection_accepter"

  # access_key - (optional) is a type of string
  access_key = null
  # aws_profile - (optional) is a type of string
  aws_profile = null
  # connection_id - (required) is a type of string
  connection_id = null
  # secret_key - (optional) is a type of string
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
  description = "(optional) - Access Key used to accept connection on provider side"
  type        = string
  default     = null
}

variable "aws_profile" {
  description = "(optional) - AWS Profile Name for retrieving credentials from shared credentials file"
  type        = string
  default     = null
}

variable "connection_id" {
  description = "(required) - Identifier of layer 2 connection that will be accepted"
  type        = string
}

variable "secret_key" {
  description = "(optional) - Secret Key used to accept connection on provider side"
  type        = string
  default     = null
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
  # access_key - (optional) is a type of string
  access_key = var.access_key
  # aws_profile - (optional) is a type of string
  aws_profile = var.aws_profile
  # connection_id - (required) is a type of string
  connection_id = var.connection_id
  # secret_key - (optional) is a type of string
  secret_key = var.secret_key

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "access_key" {
  description = "returns a string"
  value       = equinix_ecx_l2_connection_accepter.this.access_key
  sensitive   = true
}

output "aws_connection_id" {
  description = "returns a string"
  value       = equinix_ecx_l2_connection_accepter.this.aws_connection_id
}

output "id" {
  description = "returns a string"
  value       = equinix_ecx_l2_connection_accepter.this.id
}

output "secret_key" {
  description = "returns a string"
  value       = equinix_ecx_l2_connection_accepter.this.secret_key
  sensitive   = true
}

output "this" {
  value = equinix_ecx_l2_connection_accepter.this
}
```

[top](#index)