# akamai_appsec_security_policy_protections

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
module "akamai_appsec_security_policy_protections" {
  source = "./modules/akamai/r/akamai_appsec_security_policy_protections"

  # apply_api_constraints - (required) is a type of bool
  apply_api_constraints = null
  # apply_application_layer_controls - (required) is a type of bool
  apply_application_layer_controls = null
  # apply_botman_controls - (required) is a type of bool
  apply_botman_controls = null
  # apply_network_layer_controls - (required) is a type of bool
  apply_network_layer_controls = null
  # apply_rate_controls - (required) is a type of bool
  apply_rate_controls = null
  # apply_reputation_controls - (required) is a type of bool
  apply_reputation_controls = null
  # apply_slow_post_controls - (required) is a type of bool
  apply_slow_post_controls = null
  # config_id - (required) is a type of number
  config_id = null
  # security_policy_id - (required) is a type of string
  security_policy_id = null
  # version - (required) is a type of number
  version = null
}
```

[top](#index)

### Variables

```terraform
variable "apply_api_constraints" {
  description = "(required)"
  type        = bool
}

variable "apply_application_layer_controls" {
  description = "(required)"
  type        = bool
}

variable "apply_botman_controls" {
  description = "(required)"
  type        = bool
}

variable "apply_network_layer_controls" {
  description = "(required)"
  type        = bool
}

variable "apply_rate_controls" {
  description = "(required)"
  type        = bool
}

variable "apply_reputation_controls" {
  description = "(required)"
  type        = bool
}

variable "apply_slow_post_controls" {
  description = "(required)"
  type        = bool
}

variable "config_id" {
  description = "(required)"
  type        = number
}

variable "security_policy_id" {
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
resource "akamai_appsec_security_policy_protections" "this" {
  # apply_api_constraints - (required) is a type of bool
  apply_api_constraints = var.apply_api_constraints
  # apply_application_layer_controls - (required) is a type of bool
  apply_application_layer_controls = var.apply_application_layer_controls
  # apply_botman_controls - (required) is a type of bool
  apply_botman_controls = var.apply_botman_controls
  # apply_network_layer_controls - (required) is a type of bool
  apply_network_layer_controls = var.apply_network_layer_controls
  # apply_rate_controls - (required) is a type of bool
  apply_rate_controls = var.apply_rate_controls
  # apply_reputation_controls - (required) is a type of bool
  apply_reputation_controls = var.apply_reputation_controls
  # apply_slow_post_controls - (required) is a type of bool
  apply_slow_post_controls = var.apply_slow_post_controls
  # config_id - (required) is a type of number
  config_id = var.config_id
  # security_policy_id - (required) is a type of string
  security_policy_id = var.security_policy_id
  # version - (required) is a type of number
  version = var.version
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = akamai_appsec_security_policy_protections.this.id
}

output "output_text" {
  description = "returns a string"
  value       = akamai_appsec_security_policy_protections.this.output_text
}

output "this" {
  value = akamai_appsec_security_policy_protections.this
}
```

[top](#index)