# akamai_appsec_security_policy

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
module "akamai_appsec_security_policy" {
  source = "./modules/akamai/d/akamai_appsec_security_policy"

  # config_id - (required) is a type of number
  config_id = null
  # name - (optional) is a type of string
  name = null
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

variable "name" {
  description = "(optional)"
  type        = string
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
data "akamai_appsec_security_policy" "this" {
  # config_id - (required) is a type of number
  config_id = var.config_id
  # name - (optional) is a type of string
  name = var.name
  # version - (required) is a type of number
  version = var.version
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.akamai_appsec_security_policy.this.id
}

output "output_text" {
  description = "returns a string"
  value       = data.akamai_appsec_security_policy.this.output_text
}

output "policy_id" {
  description = "returns a string"
  value       = data.akamai_appsec_security_policy.this.policy_id
}

output "policy_list" {
  description = "returns a list of string"
  value       = data.akamai_appsec_security_policy.this.policy_list
}

output "this" {
  value = akamai_appsec_security_policy.this
}
```

[top](#index)