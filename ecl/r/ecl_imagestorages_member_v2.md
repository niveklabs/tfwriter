# ecl_imagestorages_member_v2

[back](../ecl.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ecl = ">= 2.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ecl_imagestorages_member_v2" {
  source = "./modules/ecl/r/ecl_imagestorages_member_v2"

  # image_id - (required) is a type of string
  image_id = null
  # member_id - (required) is a type of string
  member_id = null
  # region - (optional) is a type of string
  region = null

  timeouts = [{
    create = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "image_id" {
  description = "(required)"
  type        = string
}

variable "member_id" {
  description = "(required)"
  type        = string
}

variable "region" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "ecl_imagestorages_member_v2" "this" {
  # image_id - (required) is a type of string
  image_id = var.image_id
  # member_id - (required) is a type of string
  member_id = var.member_id
  # region - (optional) is a type of string
  region = var.region

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "created_at" {
  description = "returns a string"
  value       = ecl_imagestorages_member_v2.this.created_at
}

output "id" {
  description = "returns a string"
  value       = ecl_imagestorages_member_v2.this.id
}

output "region" {
  description = "returns a string"
  value       = ecl_imagestorages_member_v2.this.region
}

output "schema" {
  description = "returns a string"
  value       = ecl_imagestorages_member_v2.this.schema
}

output "status" {
  description = "returns a string"
  value       = ecl_imagestorages_member_v2.this.status
}

output "updated_at" {
  description = "returns a string"
  value       = ecl_imagestorages_member_v2.this.updated_at
}

output "this" {
  value = ecl_imagestorages_member_v2.this
}
```

[top](#index)