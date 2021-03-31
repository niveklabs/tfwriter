# akamai_appsec_selected_hostnames

[back](../akamai.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    akamai = ">= 1.5.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "akamai_appsec_selected_hostnames" {
  source = "./modules/akamai/r/akamai_appsec_selected_hostnames"

  # config_id - (required) is a type of number
  config_id = null
  # hostnames - (required) is a type of list of string
  hostnames = []
  # mode - (required) is a type of string
  mode = null
  # version - (required) is a type of number
  version = null
}
```

[top](#index)

### Variables

```terraform
variable "config_id" {
  description = "(required)"
  type        = number
}

variable "hostnames" {
  description = "(required)"
  type        = list(string)
}

variable "mode" {
  description = "(required)"
  type        = string
}

variable "version" {
  description = "(required)"
  type        = number
}
```

[top](#index)

### Resource

```terraform
resource "akamai_appsec_selected_hostnames" "this" {
  config_id = var.config_id
  hostnames = var.hostnames
  mode      = var.mode
  version   = var.version
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = akamai_appsec_selected_hostnames.this.id
}

output "this" {
  value = akamai_appsec_selected_hostnames.this
}
```

[top](#index)