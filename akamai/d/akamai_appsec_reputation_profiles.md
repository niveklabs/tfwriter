# akamai_appsec_reputation_profiles

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
module "akamai_appsec_reputation_profiles" {
  source = "./modules/akamai/d/akamai_appsec_reputation_profiles"

  # config_id - (required) is a type of number
  config_id = null
  # reputation_profile_id - (optional) is a type of number
  reputation_profile_id = null
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

variable "reputation_profile_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "version" {
  description = "(required)"
  type        = number
}
```

[top](#index)

### Datasource

```terraform
data "akamai_appsec_reputation_profiles" "this" {
  config_id             = var.config_id
  reputation_profile_id = var.reputation_profile_id
  version               = var.version
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.akamai_appsec_reputation_profiles.this.id
}

output "json" {
  description = "returns a string"
  value       = data.akamai_appsec_reputation_profiles.this.json
}

output "output_text" {
  description = "returns a string"
  value       = data.akamai_appsec_reputation_profiles.this.output_text
}

output "this" {
  value = akamai_appsec_reputation_profiles.this
}
```

[top](#index)