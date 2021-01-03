# datadog_integration_aws

[back](../datadog.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    datadog = ">= 2.18.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "datadog_integration_aws" {
  source = "./modules/datadog/r/datadog_integration_aws"

  # account_id - (required) is a type of string
  account_id = null
  # account_specific_namespace_rules - (optional) is a type of map of bool
  account_specific_namespace_rules = {}
  # excluded_regions - (optional) is a type of list of string
  excluded_regions = []
  # filter_tags - (optional) is a type of list of string
  filter_tags = []
  # host_tags - (optional) is a type of list of string
  host_tags = []
  # role_name - (required) is a type of string
  role_name = null
}
```

[top](#index)

### Variables

```terraform
variable "account_id" {
  description = "(required)"
  type        = string
}

variable "account_specific_namespace_rules" {
  description = "(optional)"
  type        = map(bool)
  default     = null
}

variable "excluded_regions" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "filter_tags" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "host_tags" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "role_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "datadog_integration_aws" "this" {
  account_id                       = var.account_id
  account_specific_namespace_rules = var.account_specific_namespace_rules
  excluded_regions                 = var.excluded_regions
  filter_tags                      = var.filter_tags
  host_tags                        = var.host_tags
  role_name                        = var.role_name
}
```

[top](#index)

### Outputs

```terraform
output "external_id" {
  description = "returns a string"
  value       = datadog_integration_aws.this.external_id
}

output "id" {
  description = "returns a string"
  value       = datadog_integration_aws.this.id
}

output "this" {
  value = datadog_integration_aws.this
}
```

[top](#index)