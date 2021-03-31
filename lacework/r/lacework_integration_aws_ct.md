# lacework_integration_aws_ct

[back](../lacework.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    lacework = ">= 0.3.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "lacework_integration_aws_ct" {
  source = "./modules/lacework/r/lacework_integration_aws_ct"

  # enabled - (optional) is a type of bool
  enabled = null
  # name - (required) is a type of string
  name = null
  # queue_url - (required) is a type of string
  queue_url = null
  # retries - (optional) is a type of number
  retries = null

  credentials = [{
    external_id = null
    role_arn    = null
  }]

  org_account_mappings = [{
    default_lacework_account = null
    mapping = [{
      aws_accounts     = []
      lacework_account = null
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "enabled" {
  description = "(optional) - The state of the external integration."
  type        = bool
  default     = null
}

variable "name" {
  description = "(required) - The integration name."
  type        = string
}

variable "queue_url" {
  description = "(required) - The SQS Queue URL."
  type        = string
}

variable "retries" {
  description = "(optional) - The number of attempts to create the external integration."
  type        = number
  default     = null
}

variable "credentials" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      external_id = string
      role_arn    = string
    }
  ))
}

variable "org_account_mappings" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      default_lacework_account = string
      mapping = set(object(
        {
          aws_accounts     = set(string)
          lacework_account = string
        }
      ))
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "lacework_integration_aws_ct" "this" {
  enabled   = var.enabled
  name      = var.name
  queue_url = var.queue_url
  retries   = var.retries

  dynamic "credentials" {
    for_each = var.credentials
    content {
      external_id = credentials.value["external_id"]
      role_arn    = credentials.value["role_arn"]
    }
  }

  dynamic "org_account_mappings" {
    for_each = var.org_account_mappings
    content {
      default_lacework_account = org_account_mappings.value["default_lacework_account"]

      dynamic "mapping" {
        for_each = org_account_mappings.value.mapping
        content {
          aws_accounts     = mapping.value["aws_accounts"]
          lacework_account = mapping.value["lacework_account"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "created_or_updated_by" {
  description = "returns a string"
  value       = lacework_integration_aws_ct.this.created_or_updated_by
}

output "created_or_updated_time" {
  description = "returns a string"
  value       = lacework_integration_aws_ct.this.created_or_updated_time
}

output "id" {
  description = "returns a string"
  value       = lacework_integration_aws_ct.this.id
}

output "intg_guid" {
  description = "returns a string"
  value       = lacework_integration_aws_ct.this.intg_guid
}

output "org_level" {
  description = "returns a bool"
  value       = lacework_integration_aws_ct.this.org_level
}

output "type_name" {
  description = "returns a string"
  value       = lacework_integration_aws_ct.this.type_name
}

output "this" {
  value = lacework_integration_aws_ct.this
}
```

[top](#index)