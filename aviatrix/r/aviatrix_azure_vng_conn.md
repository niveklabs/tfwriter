# aviatrix_azure_vng_conn

[back](../aviatrix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aviatrix = ">= 2.18.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aviatrix_azure_vng_conn" {
  source = "./modules/aviatrix/r/aviatrix_azure_vng_conn"

  # connection_name - (required) is a type of string
  connection_name = null
  # primary_gateway_name - (required) is a type of string
  primary_gateway_name = null
}
```

[top](#index)

### Variables

```terraform
variable "connection_name" {
  description = "(required) - Connection name"
  type        = string
}

variable "primary_gateway_name" {
  description = "(required) - Primary gateway name"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_azure_vng_conn" "this" {
  connection_name      = var.connection_name
  primary_gateway_name = var.primary_gateway_name
}
```

[top](#index)

### Outputs

```terraform
output "attached" {
  description = "returns a bool"
  value       = aviatrix_azure_vng_conn.this.attached
}

output "id" {
  description = "returns a string"
  value       = aviatrix_azure_vng_conn.this.id
}

output "vng_name" {
  description = "returns a string"
  value       = aviatrix_azure_vng_conn.this.vng_name
}

output "vpc_id" {
  description = "returns a string"
  value       = aviatrix_azure_vng_conn.this.vpc_id
}

output "this" {
  value = aviatrix_azure_vng_conn.this
}
```

[top](#index)