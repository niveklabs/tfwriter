# akamai_appsec_api_request_constraints

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
module "akamai_appsec_api_request_constraints" {
  source = "./modules/akamai/d/akamai_appsec_api_request_constraints"

  # api_id - (optional) is a type of number
  api_id = null
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
variable "api_id" {
  description = "(optional)"
  type        = number
  default     = null
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

### Datasource

```terraform
data "akamai_appsec_api_request_constraints" "this" {
  # api_id - (optional) is a type of number
  api_id = var.api_id
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
  value       = data.akamai_appsec_api_request_constraints.this.id
}

output "json" {
  description = "returns a string"
  value       = data.akamai_appsec_api_request_constraints.this.json
}

output "output_text" {
  description = "returns a string"
  value       = data.akamai_appsec_api_request_constraints.this.output_text
}

output "this" {
  value = akamai_appsec_api_request_constraints.this
}
```

[top](#index)