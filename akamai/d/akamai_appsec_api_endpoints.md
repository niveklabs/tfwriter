# akamai_appsec_api_endpoints

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
module "akamai_appsec_api_endpoints" {
  source = "./modules/akamai/d/akamai_appsec_api_endpoints"

  # api_name - (optional) is a type of string
  api_name = null
  # config_id - (required) is a type of number
  config_id = null
  # security_policy_id - (optional) is a type of string
  security_policy_id = null
  # version - (required) is a type of number
  version = null
}
```

[top](#index)

### Variables

```terraform
variable "api_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "config_id" {
  description = "(required)"
  type        = number
}

variable "security_policy_id" {
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
data "akamai_appsec_api_endpoints" "this" {
  # api_name - (optional) is a type of string
  api_name = var.api_name
  # config_id - (required) is a type of number
  config_id = var.config_id
  # security_policy_id - (optional) is a type of string
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
  value       = data.akamai_appsec_api_endpoints.this.id
}

output "id_list" {
  description = "returns a list of number"
  value       = data.akamai_appsec_api_endpoints.this.id_list
}

output "json" {
  description = "returns a string"
  value       = data.akamai_appsec_api_endpoints.this.json
}

output "output_text" {
  description = "returns a string"
  value       = data.akamai_appsec_api_endpoints.this.output_text
}

output "this" {
  value = akamai_appsec_api_endpoints.this
}
```

[top](#index)