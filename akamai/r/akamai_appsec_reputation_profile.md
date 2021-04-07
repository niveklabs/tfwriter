# akamai_appsec_reputation_profile

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
module "akamai_appsec_reputation_profile" {
  source = "./modules/akamai/r/akamai_appsec_reputation_profile"

  # config_id - (required) is a type of number
  config_id = null
  # reputation_profile - (required) is a type of string
  reputation_profile = null
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

variable "reputation_profile" {
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
resource "akamai_appsec_reputation_profile" "this" {
  # config_id - (required) is a type of number
  config_id = var.config_id
  # reputation_profile - (required) is a type of string
  reputation_profile = var.reputation_profile
  # version - (required) is a type of number
  version = var.version
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = akamai_appsec_reputation_profile.this.id
}

output "reputation_profile_id" {
  description = "returns a number"
  value       = akamai_appsec_reputation_profile.this.reputation_profile_id
}

output "this" {
  value = akamai_appsec_reputation_profile.this
}
```

[top](#index)