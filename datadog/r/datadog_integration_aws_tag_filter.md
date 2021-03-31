# datadog_integration_aws_tag_filter

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
module "datadog_integration_aws_tag_filter" {
  source = "./modules/datadog/r/datadog_integration_aws_tag_filter"

  # account_id - (required) is a type of string
  account_id = null
  # namespace - (required) is a type of string
  namespace = null
  # tag_filter_str - (required) is a type of string
  tag_filter_str = null
}
```

[top](#index)

### Variables

```terraform
variable "account_id" {
  description = "(required) - Your AWS Account ID without dashes."
  type        = string
}

variable "namespace" {
  description = "(required) - The namespace associated with the tag filter entry. Allowed enum values: 'elb', 'application_elb', 'sqs', 'rds', 'custom', 'network_elb,lambda'"
  type        = string
}

variable "tag_filter_str" {
  description = "(required) - The tag filter string."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "datadog_integration_aws_tag_filter" "this" {
  account_id     = var.account_id
  namespace      = var.namespace
  tag_filter_str = var.tag_filter_str
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = datadog_integration_aws_tag_filter.this.id
}

output "this" {
  value = datadog_integration_aws_tag_filter.this
}
```

[top](#index)