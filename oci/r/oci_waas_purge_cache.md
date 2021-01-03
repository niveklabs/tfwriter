# oci_waas_purge_cache

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
    oci = ">= 4.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_waas_purge_cache" {
  source = "./modules/oci/r/oci_waas_purge_cache"

  # resources - (optional) is a type of list of string
  resources = []
  # waas_policy_id - (required) is a type of string
  waas_policy_id = null

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
variable "resources" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "waas_policy_id" {
  description = "(required)"
  type        = string
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
resource "oci_waas_purge_cache" "this" {
  resources      = var.resources
  waas_policy_id = var.waas_policy_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
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
  value       = oci_waas_purge_cache.this.id
}

output "this" {
  value = oci_waas_purge_cache.this
}
```

[top](#index)