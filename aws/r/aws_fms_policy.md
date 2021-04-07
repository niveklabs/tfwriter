# aws_fms_policy

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aws = ">= 3.35.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_fms_policy" {
  source = "./modules/aws/r/aws_fms_policy"

  # delete_all_policy_resources - (optional) is a type of bool
  delete_all_policy_resources = null
  # exclude_resource_tags - (required) is a type of bool
  exclude_resource_tags = null
  # name - (required) is a type of string
  name = null
  # remediation_enabled - (optional) is a type of bool
  remediation_enabled = null
  # resource_tags - (optional) is a type of map of string
  resource_tags = {}
  # resource_type - (optional) is a type of string
  resource_type = null
  # resource_type_list - (optional) is a type of set of string
  resource_type_list = []

  exclude_map = [{
    account = []
    orgunit = []
  }]

  include_map = [{
    account = []
    orgunit = []
  }]

  security_service_policy_data = [{
    managed_service_data = null
    type                 = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "delete_all_policy_resources" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "exclude_resource_tags" {
  description = "(required)"
  type        = bool
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "remediation_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "resource_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "resource_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_type_list" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "exclude_map" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      account = set(string)
      orgunit = set(string)
    }
  ))
  default = []
}

variable "include_map" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      account = set(string)
      orgunit = set(string)
    }
  ))
  default = []
}

variable "security_service_policy_data" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      managed_service_data = string
      type                 = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "aws_fms_policy" "this" {
  # delete_all_policy_resources - (optional) is a type of bool
  delete_all_policy_resources = var.delete_all_policy_resources
  # exclude_resource_tags - (required) is a type of bool
  exclude_resource_tags = var.exclude_resource_tags
  # name - (required) is a type of string
  name = var.name
  # remediation_enabled - (optional) is a type of bool
  remediation_enabled = var.remediation_enabled
  # resource_tags - (optional) is a type of map of string
  resource_tags = var.resource_tags
  # resource_type - (optional) is a type of string
  resource_type = var.resource_type
  # resource_type_list - (optional) is a type of set of string
  resource_type_list = var.resource_type_list

  dynamic "exclude_map" {
    for_each = var.exclude_map
    content {
      # account - (optional) is a type of set of string
      account = exclude_map.value["account"]
      # orgunit - (optional) is a type of set of string
      orgunit = exclude_map.value["orgunit"]
    }
  }

  dynamic "include_map" {
    for_each = var.include_map
    content {
      # account - (optional) is a type of set of string
      account = include_map.value["account"]
      # orgunit - (optional) is a type of set of string
      orgunit = include_map.value["orgunit"]
    }
  }

  dynamic "security_service_policy_data" {
    for_each = var.security_service_policy_data
    content {
      # managed_service_data - (optional) is a type of string
      managed_service_data = security_service_policy_data.value["managed_service_data"]
      # type - (required) is a type of string
      type = security_service_policy_data.value["type"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_fms_policy.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_fms_policy.this.id
}

output "policy_update_token" {
  description = "returns a string"
  value       = aws_fms_policy.this.policy_update_token
}

output "resource_type" {
  description = "returns a string"
  value       = aws_fms_policy.this.resource_type
}

output "resource_type_list" {
  description = "returns a set of string"
  value       = aws_fms_policy.this.resource_type_list
}

output "this" {
  value = aws_fms_policy.this
}
```

[top](#index)