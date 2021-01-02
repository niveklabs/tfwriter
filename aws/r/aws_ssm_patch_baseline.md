# aws_ssm_patch_baseline

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
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_ssm_patch_baseline" {
  source = "./modules/aws/r/aws_ssm_patch_baseline"

  # approved_patches - (optional) is a type of set of string
  approved_patches = []
  # approved_patches_compliance_level - (optional) is a type of string
  approved_patches_compliance_level = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # operating_system - (optional) is a type of string
  operating_system = null
  # rejected_patches - (optional) is a type of set of string
  rejected_patches = []
  # tags - (optional) is a type of map of string
  tags = {}

  approval_rule = [{
    approve_after_days  = null
    compliance_level    = null
    enable_non_security = null
    patch_filter = [{
      key    = null
      values = []
    }]
  }]

  global_filter = [{
    key    = null
    values = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "approved_patches" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "approved_patches_compliance_level" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "operating_system" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rejected_patches" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "approval_rule" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      approve_after_days  = number
      compliance_level    = string
      enable_non_security = bool
      patch_filter = list(object(
        {
          key    = string
          values = list(string)
        }
      ))
    }
  ))
  default = []
}

variable "global_filter" {
  description = "nested block: NestingList, min items: 0, max items: 4"
  type = set(object(
    {
      key    = string
      values = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_ssm_patch_baseline" "this" {
  approved_patches                  = var.approved_patches
  approved_patches_compliance_level = var.approved_patches_compliance_level
  description                       = var.description
  name                              = var.name
  operating_system                  = var.operating_system
  rejected_patches                  = var.rejected_patches
  tags                              = var.tags

  dynamic "approval_rule" {
    for_each = var.approval_rule
    content {
      approve_after_days  = approval_rule.value["approve_after_days"]
      compliance_level    = approval_rule.value["compliance_level"]
      enable_non_security = approval_rule.value["enable_non_security"]

      dynamic "patch_filter" {
        for_each = approval_rule.value.patch_filter
        content {
          key    = patch_filter.value["key"]
          values = patch_filter.value["values"]
        }
      }

    }
  }

  dynamic "global_filter" {
    for_each = var.global_filter
    content {
      key    = global_filter.value["key"]
      values = global_filter.value["values"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_ssm_patch_baseline.this.id
}

output "this" {
  value = aws_ssm_patch_baseline.this
}
```

[top](#index)