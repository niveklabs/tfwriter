# akamai_appsec_bypass_network_lists

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
module "akamai_appsec_bypass_network_lists" {
  source = "./modules/akamai/r/akamai_appsec_bypass_network_lists"

  # bypass_network_list - (required) is a type of list of string
  bypass_network_list = []
  # config_id - (required) is a type of number
  config_id = null
  # version - (required) is a type of number
  version = null
}
```

[top](#index)

### Variables

```terraform
variable "bypass_network_list" {
  description = "(required)"
  type        = list(string)
}

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

### Resource

```terraform
resource "akamai_appsec_bypass_network_lists" "this" {
  bypass_network_list = var.bypass_network_list
  config_id           = var.config_id
  version             = var.version
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = akamai_appsec_bypass_network_lists.this.id
}

output "output_text" {
  description = "returns a string"
  value       = akamai_appsec_bypass_network_lists.this.output_text
}

output "this" {
  value = akamai_appsec_bypass_network_lists.this
}
```

[top](#index)