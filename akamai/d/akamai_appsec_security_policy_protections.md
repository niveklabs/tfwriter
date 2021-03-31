# akamai_appsec_security_policy_protections

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
module "akamai_appsec_security_policy_protections" {
  source = "./modules/akamai/d/akamai_appsec_security_policy_protections"

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

### Datasource

```terraform
data "akamai_appsec_security_policy_protections" "this" {
  config_id          = var.config_id
  security_policy_id = var.security_policy_id
  version            = var.version
}
```

[top](#index)

### Outputs

```terraform
output "apply_api_constraints" {
  description = "returns a bool"
  value       = data.akamai_appsec_security_policy_protections.this.apply_api_constraints
}

output "apply_application_layer_controls" {
  description = "returns a bool"
  value       = data.akamai_appsec_security_policy_protections.this.apply_application_layer_controls
}

output "apply_botman_controls" {
  description = "returns a bool"
  value       = data.akamai_appsec_security_policy_protections.this.apply_botman_controls
}

output "apply_network_layer_controls" {
  description = "returns a bool"
  value       = data.akamai_appsec_security_policy_protections.this.apply_network_layer_controls
}

output "apply_rate_controls" {
  description = "returns a bool"
  value       = data.akamai_appsec_security_policy_protections.this.apply_rate_controls
}

output "apply_reputation_controls" {
  description = "returns a bool"
  value       = data.akamai_appsec_security_policy_protections.this.apply_reputation_controls
}

output "apply_slow_post_controls" {
  description = "returns a bool"
  value       = data.akamai_appsec_security_policy_protections.this.apply_slow_post_controls
}

output "id" {
  description = "returns a string"
  value       = data.akamai_appsec_security_policy_protections.this.id
}

output "json" {
  description = "returns a string"
  value       = data.akamai_appsec_security_policy_protections.this.json
}

output "output_text" {
  description = "returns a string"
  value       = data.akamai_appsec_security_policy_protections.this.output_text
}

output "this" {
  value = akamai_appsec_security_policy_protections.this
}
```

[top](#index)