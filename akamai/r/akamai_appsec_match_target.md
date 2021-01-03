# akamai_appsec_match_target

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
    akamai = ">= 1.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "akamai_appsec_match_target" {
  source = "./modules/akamai/r/akamai_appsec_match_target"

  # config_id - (required) is a type of number
  config_id = null
  # json - (required) is a type of string
  json = null
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

variable "json" {
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
resource "akamai_appsec_match_target" "this" {
  config_id = var.config_id
  json      = var.json
  version   = var.version
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = akamai_appsec_match_target.this.id
}

output "match_target_id" {
  description = "returns a number"
  value       = akamai_appsec_match_target.this.match_target_id
}

output "this" {
  value = akamai_appsec_match_target.this
}
```

[top](#index)