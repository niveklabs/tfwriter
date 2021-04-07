# oci_database_exadata_iorm_config

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_database_exadata_iorm_config" {
  source = "./modules/oci/r/oci_database_exadata_iorm_config"

  # db_system_id - (required) is a type of string
  db_system_id = null
  # objective - (optional) is a type of string
  objective = null

  db_plans = [{
    db_name           = null
    flash_cache_limit = null
    share             = null
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "db_system_id" {
  description = "(required)"
  type        = string
}

variable "objective" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "db_plans" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      db_name           = string
      flash_cache_limit = string
      share             = number
    }
  ))
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "oci_database_exadata_iorm_config" "this" {
  # db_system_id - (required) is a type of string
  db_system_id = var.db_system_id
  # objective - (optional) is a type of string
  objective = var.objective

  dynamic "db_plans" {
    for_each = var.db_plans
    content {
      # db_name - (required) is a type of string
      db_name = db_plans.value["db_name"]
      # share - (required) is a type of number
      share = db_plans.value["share"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
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
  value       = oci_database_exadata_iorm_config.this.id
}

output "lifecycle_details" {
  description = "returns a string"
  value       = oci_database_exadata_iorm_config.this.lifecycle_details
}

output "objective" {
  description = "returns a string"
  value       = oci_database_exadata_iorm_config.this.objective
}

output "state" {
  description = "returns a string"
  value       = oci_database_exadata_iorm_config.this.state
}

output "this" {
  value = oci_database_exadata_iorm_config.this
}
```

[top](#index)