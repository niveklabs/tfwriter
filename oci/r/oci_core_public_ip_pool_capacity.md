# oci_core_public_ip_pool_capacity

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
module "oci_core_public_ip_pool_capacity" {
  source = "./modules/oci/r/oci_core_public_ip_pool_capacity"

  # byoip_id - (required) is a type of string
  byoip_id = null
  # cidr_block - (required) is a type of string
  cidr_block = null
  # public_ip_pool_id - (required) is a type of string
  public_ip_pool_id = null

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
variable "byoip_id" {
  description = "(required)"
  type        = string
}

variable "cidr_block" {
  description = "(required)"
  type        = string
}

variable "public_ip_pool_id" {
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
resource "oci_core_public_ip_pool_capacity" "this" {
  # byoip_id - (required) is a type of string
  byoip_id = var.byoip_id
  # cidr_block - (required) is a type of string
  cidr_block = var.cidr_block
  # public_ip_pool_id - (required) is a type of string
  public_ip_pool_id = var.public_ip_pool_id

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
  value       = oci_core_public_ip_pool_capacity.this.id
}

output "this" {
  value = oci_core_public_ip_pool_capacity.this
}
```

[top](#index)