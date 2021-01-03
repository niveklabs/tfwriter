# akamai_appsec_match_target_sequence

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
module "akamai_appsec_match_target_sequence" {
  source = "./modules/akamai/r/akamai_appsec_match_target_sequence"

  # config_id - (required) is a type of number
  config_id = null
  # json - (optional) is a type of string
  json = null
  # sequence_map - (optional) is a type of map of string
  sequence_map = {}
  # type - (required) is a type of string
  type = null
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
  description = "(optional)"
  type        = string
  default     = null
}

variable "sequence_map" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "type" {
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
resource "akamai_appsec_match_target_sequence" "this" {
  config_id    = var.config_id
  json         = var.json
  sequence_map = var.sequence_map
  type         = var.type
  version      = var.version
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = akamai_appsec_match_target_sequence.this.id
}

output "this" {
  value = akamai_appsec_match_target_sequence.this
}
```

[top](#index)