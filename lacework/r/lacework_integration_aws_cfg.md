# lacework_integration_aws_cfg

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
    lacework = ">= 0.2.7"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "lacework_integration_aws_cfg" {
  source = "./modules/lacework/r/lacework_integration_aws_cfg"

  # enabled - (optional) is a type of bool
  enabled = null
  # name - (required) is a type of string
  name = null

  credentials = [{
    external_id = null
    role_arn    = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
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
```

[top](#index)

### Resource

```terraform
resource "lacework_integration_aws_cfg" "this" {
  enabled = var.enabled
  name    = var.name

  dynamic "credentials" {
    for_each = var.credentials
    content {
      external_id = credentials.value["external_id"]
      role_arn    = credentials.value["role_arn"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "created_or_updated_by" {
  description = "returns a string"
  value       = lacework_integration_aws_cfg.this.created_or_updated_by
}

output "created_or_updated_time" {
  description = "returns a string"
  value       = lacework_integration_aws_cfg.this.created_or_updated_time
}

output "id" {
  description = "returns a string"
  value       = lacework_integration_aws_cfg.this.id
}

output "intg_guid" {
  description = "returns a string"
  value       = lacework_integration_aws_cfg.this.intg_guid
}

output "org_level" {
  description = "returns a bool"
  value       = lacework_integration_aws_cfg.this.org_level
}

output "type_name" {
  description = "returns a string"
  value       = lacework_integration_aws_cfg.this.type_name
}

output "this" {
  value = lacework_integration_aws_cfg.this
}
```

[top](#index)