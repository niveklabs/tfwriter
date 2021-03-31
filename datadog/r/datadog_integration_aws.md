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
    datadog = ">= 2.24.0"
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
  description = "(required) - Your AWS Account ID without dashes."
  type        = string
}

variable "account_specific_namespace_rules" {
  description = "(optional) - Enables or disables metric collection for specific AWS namespaces for this AWS account only. A list of namespaces can be found at the [available namespace rules API endpoint](https://docs.datadoghq.com/api/v1/aws-integration/#list-namespace-rules)."
  type        = map(bool)
  default     = null
}

variable "excluded_regions" {
  description = "(optional) - An array of AWS regions to exclude from metrics collection."
  type        = list(string)
  default     = null
}

variable "filter_tags" {
  description = "(optional) - Array of EC2 tags (in the form `key:value`) defines a filter that Datadog uses when collecting metrics from EC2. Wildcards, such as `?` (for single characters) and `*` (for multiple characters) can also be used. Only hosts that match one of the defined tags will be imported into Datadog. The rest will be ignored. Host matching a given tag can also be excluded by adding `!` before the tag. e.x. `env:production,instance-type:c1.*,!region:us-east-1`."
  type        = list(string)
  default     = null
}

variable "host_tags" {
  description = "(optional) - Array of tags (in the form `key:value`) to add to all hosts and metrics reporting through this integration."
  type        = list(string)
  default     = null
}

variable "role_name" {
  description = "(required) - Your Datadog role delegation name."
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