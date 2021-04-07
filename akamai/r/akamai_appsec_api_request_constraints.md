# akamai_appsec_api_request_constraints

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
module "akamai_appsec_api_request_constraints" {
  source = "./modules/akamai/r/akamai_appsec_api_request_constraints"

  # action - (required) is a type of string
  action = null
  # api_endpoint_id - (optional) is a type of number
  api_endpoint_id = null
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
variable "action" {
  description = "(required)"
  type        = string
}

variable "api_endpoint_id" {
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

### Resource

```terraform
resource "akamai_appsec_api_request_constraints" "this" {
  # action - (required) is a type of string
  action = var.action
  # api_endpoint_id - (optional) is a type of number
  api_endpoint_id = var.api_endpoint_id
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
  value       = akamai_appsec_api_request_constraints.this.id
}

output "this" {
  value = akamai_appsec_api_request_constraints.this
}
```

[top](#index)