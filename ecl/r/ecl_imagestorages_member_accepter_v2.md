# ecl_imagestorages_member_accepter_v2

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
module "ecl_imagestorages_member_accepter_v2" {
  source = "./modules/ecl/r/ecl_imagestorages_member_accepter_v2"

  # image_member_id - (required) is a type of string
  image_member_id = null
  # region - (optional) is a type of string
  region = null
  # status - (required) is a type of string
  status = null

  timeouts = [{
    create = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "image_member_id" {
  description = "(required)"
  type        = string
}

variable "region" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(required)"
  type        = string
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
resource "ecl_imagestorages_member_accepter_v2" "this" {
  image_member_id = var.image_member_id
  region          = var.region
  status          = var.status

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = ecl_imagestorages_member_accepter_v2.this.id
}

output "region" {
  description = "returns a string"
  value       = ecl_imagestorages_member_accepter_v2.this.region
}

output "this" {
  value = ecl_imagestorages_member_accepter_v2.this
}
```

[top](#index)