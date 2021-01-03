# dome9_cloudaccount_aws

[back](../dome9.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    dome9 = ">= 1.20.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "dome9_cloudaccount_aws" {
  source = "./modules/dome9/r/dome9_cloudaccount_aws"

  # name - (required) is a type of string
  name = null
  # organizational_unit_id - (optional) is a type of string
  organizational_unit_id = null

  credentials = [{
    api_key      = null
    arn          = null
    iam_user     = null
    is_read_only = null
    secret       = null
    type         = null
  }]

  net_sec = [{
    regions = [{
      hidden             = null
      name               = null
      new_group_behavior = null
      region             = null
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "organizational_unit_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "credentials" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      api_key      = string
      arn          = string
      iam_user     = string
      is_read_only = bool
      secret       = string
      type         = string
    }
  ))
}

variable "net_sec" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      regions = list(object(
        {
          hidden             = bool
          name               = string
          new_group_behavior = string
          region             = string
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
resource "dome9_cloudaccount_aws" "this" {
  name                   = var.name
  organizational_unit_id = var.organizational_unit_id

  dynamic "credentials" {
    for_each = var.credentials
    content {
      api_key  = credentials.value["api_key"]
      arn      = credentials.value["arn"]
      iam_user = credentials.value["iam_user"]
      secret   = credentials.value["secret"]
      type     = credentials.value["type"]
    }
  }

  dynamic "net_sec" {
    for_each = var.net_sec
    content {

      dynamic "regions" {
        for_each = net_sec.value.regions
        content {
          new_group_behavior = regions.value["new_group_behavior"]
          region             = regions.value["region"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "allow_read_only" {
  description = "returns a bool"
  value       = dome9_cloudaccount_aws.this.allow_read_only
}

output "creation_date" {
  description = "returns a string"
  value       = dome9_cloudaccount_aws.this.creation_date
}

output "external_account_number" {
  description = "returns a string"
  value       = dome9_cloudaccount_aws.this.external_account_number
}

output "full_protection" {
  description = "returns a bool"
  value       = dome9_cloudaccount_aws.this.full_protection
}

output "iam_safe" {
  description = "returns a set of object"
  value       = dome9_cloudaccount_aws.this.iam_safe
}

output "id" {
  description = "returns a string"
  value       = dome9_cloudaccount_aws.this.id
}

output "is_fetching_suspended" {
  description = "returns a bool"
  value       = dome9_cloudaccount_aws.this.is_fetching_suspended
}

output "vendor" {
  description = "returns a string"
  value       = dome9_cloudaccount_aws.this.vendor
}

output "this" {
  value = dome9_cloudaccount_aws.this
}
```

[top](#index)