# ovh_dedicated_server_boots

[back](../ovh.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ovh = ">= 0.10.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ovh_dedicated_server_boots" {
  source = "./modules/ovh/d/ovh_dedicated_server_boots"

  # boot_type - (optional) is a type of string
  boot_type = null
  # kernel - (optional) is a type of string
  kernel = null
  # service_name - (required) is a type of string
  service_name = null
}
```

[top](#index)

### Variables

```terraform
variable "boot_type" {
  description = "(optional) - Filter the value of bootType property"
  type        = string
  default     = null
}

variable "kernel" {
  description = "(optional) - Filter the value of kernel property"
  type        = string
  default     = null
}

variable "service_name" {
  description = "(required) - The internal name of your dedicated server."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "ovh_dedicated_server_boots" "this" {
  boot_type    = var.boot_type
  kernel       = var.kernel
  service_name = var.service_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.ovh_dedicated_server_boots.this.id
}

output "result" {
  description = "returns a list of number"
  value       = data.ovh_dedicated_server_boots.this.result
}

output "this" {
  value = ovh_dedicated_server_boots.this
}
```

[top](#index)