# akamai_appsec_bypass_network_lists

[back](../akamai.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "akamai_appsec_bypass_network_lists" {
  source = "./modules/akamai/d/akamai_appsec_bypass_network_lists"

  # config_id - (required) is a type of number
  config_id = null
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

variable "version" {
  description = "(required)"
  type        = number
}
```

[top](#index)

### Datasource

```terraform
data "akamai_appsec_bypass_network_lists" "this" {
  # config_id - (required) is a type of number
  config_id = var.config_id
  # version - (required) is a type of number
  version = var.version
}
```

[top](#index)

### Outputs

```terraform
output "bypass_network_list" {
  description = "returns a list of string"
  value       = data.akamai_appsec_bypass_network_lists.this.bypass_network_list
}

output "id" {
  description = "returns a string"
  value       = data.akamai_appsec_bypass_network_lists.this.id
}

output "json" {
  description = "returns a string"
  value       = data.akamai_appsec_bypass_network_lists.this.json
}

output "output_text" {
  description = "returns a string"
  value       = data.akamai_appsec_bypass_network_lists.this.output_text
}

output "this" {
  value = akamai_appsec_bypass_network_lists.this
}
```

[top](#index)