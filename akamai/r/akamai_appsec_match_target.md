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
    akamai = ">= 1.5.0"
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
  # match_target - (required) is a type of string
  match_target = null
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

variable "match_target" {
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
  config_id    = var.config_id
  match_target = var.match_target
  version      = var.version
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