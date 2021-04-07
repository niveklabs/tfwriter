# profitbricks_s3_key

[back](../profitbricks.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    profitbricks = ">= 1.6.5"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "profitbricks_s3_key" {
  source = "./modules/profitbricks/r/profitbricks_s3_key"

  # active - (optional) is a type of bool
  active = null
  # user_id - (required) is a type of string
  user_id = null

  timeouts = [{
    create  = null
    default = null
    delete  = null
    update  = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "active" {
  description = "(optional) - Whether this key should be active or not."
  type        = bool
  default     = null
}

variable "user_id" {
  description = "(required) - The ID of the user that owns the key."
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create  = string
      default = string
      delete  = string
      update  = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "profitbricks_s3_key" "this" {
  # active - (optional) is a type of bool
  active = var.active
  # user_id - (required) is a type of string
  user_id = var.user_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # default - (optional) is a type of string
      default = timeouts.value["default"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = profitbricks_s3_key.this.id
}

output "secret_key" {
  description = "returns a string"
  value       = profitbricks_s3_key.this.secret_key
}

output "this" {
  value = profitbricks_s3_key.this
}
```

[top](#index)