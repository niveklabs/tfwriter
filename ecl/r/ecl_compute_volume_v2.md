# ecl_compute_volume_v2

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
    ecl = ">= 1.13.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ecl_compute_volume_v2" {
  source = "./modules/ecl/r/ecl_compute_volume_v2"

  # availability_zone - (optional) is a type of string
  availability_zone = null
  # description - (optional) is a type of string
  description = null
  # image_id - (optional) is a type of string
  image_id = null
  # image_name - (optional) is a type of string
  image_name = null
  # metadata - (optional) is a type of map of string
  metadata = {}
  # name - (optional) is a type of string
  name = null
  # region - (optional) is a type of string
  region = null
  # size - (required) is a type of number
  size = null
  # source_replica - (optional) is a type of string
  source_replica = null
  # volume_type - (optional) is a type of string
  volume_type = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "availability_zone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "image_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "image_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "metadata" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "size" {
  description = "(required)"
  type        = number
}

variable "source_replica" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "volume_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "ecl_compute_volume_v2" "this" {
  availability_zone = var.availability_zone
  description       = var.description
  image_id          = var.image_id
  image_name        = var.image_name
  metadata          = var.metadata
  name              = var.name
  region            = var.region
  size              = var.size
  source_replica    = var.source_replica
  volume_type       = var.volume_type

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "attachment" {
  description = "returns a set of object"
  value       = ecl_compute_volume_v2.this.attachment
}

output "availability_zone" {
  description = "returns a string"
  value       = ecl_compute_volume_v2.this.availability_zone
}

output "id" {
  description = "returns a string"
  value       = ecl_compute_volume_v2.this.id
}

output "metadata" {
  description = "returns a map of string"
  value       = ecl_compute_volume_v2.this.metadata
}

output "region" {
  description = "returns a string"
  value       = ecl_compute_volume_v2.this.region
}

output "volume_type" {
  description = "returns a string"
  value       = ecl_compute_volume_v2.this.volume_type
}

output "this" {
  value = ecl_compute_volume_v2.this
}
```

[top](#index)