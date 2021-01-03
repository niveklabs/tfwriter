# oci_blockchain_osn

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
module "oci_blockchain_osn" {
  source = "./modules/oci/r/oci_blockchain_osn"

  # ad - (required) is a type of string
  ad = null
  # blockchain_platform_id - (required) is a type of string
  blockchain_platform_id = null

  ocpu_allocation_param = [{
    ocpu_allocation_number = null
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
variable "ad" {
  description = "(required)"
  type        = string
}

variable "blockchain_platform_id" {
  description = "(required)"
  type        = string
}

variable "ocpu_allocation_param" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      ocpu_allocation_number = number
    }
  ))
  default = []
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
resource "oci_blockchain_osn" "this" {
  ad                     = var.ad
  blockchain_platform_id = var.blockchain_platform_id

  dynamic "ocpu_allocation_param" {
    for_each = var.ocpu_allocation_param
    content {
      ocpu_allocation_number = ocpu_allocation_param.value["ocpu_allocation_number"]
    }
  }

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
  value       = oci_blockchain_osn.this.id
}

output "osn_key" {
  description = "returns a string"
  value       = oci_blockchain_osn.this.osn_key
}

output "state" {
  description = "returns a string"
  value       = oci_blockchain_osn.this.state
}

output "this" {
  value = oci_blockchain_osn.this
}
```

[top](#index)