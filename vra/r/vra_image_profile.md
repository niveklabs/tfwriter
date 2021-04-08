# vra_image_profile

[back](../vra.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vra = ">= 0.3.5"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vra_image_profile" {
  source = "./modules/vra/r/vra_image_profile"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # region_id - (required) is a type of string
  region_id = null

  image_mapping = [{
    cloud_config = null
    constraints = [{
      expression = null
      mandatory  = null
    }]
    description        = null
    external_id        = null
    external_region_id = null
    image_id           = null
    image_name         = null
    name               = null
    organization       = null
    os_family          = null
    owner              = null
    private            = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - A human-friendly description."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - A human-friendly name used as an identifier in APIs that support this option."
  type        = string
}

variable "region_id" {
  description = "(required) - The if of the region for which this profile is defined as in vRealize Automation(vRA)."
  type        = string
}

variable "image_mapping" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      cloud_config = string
      constraints = set(object(
        {
          expression = string
          mandatory  = bool
        }
      ))
      description        = string
      external_id        = string
      external_region_id = string
      image_id           = string
      image_name         = string
      name               = string
      organization       = string
      os_family          = string
      owner              = string
      private            = bool
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "vra_image_profile" "this" {
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # region_id - (required) is a type of string
  region_id = var.region_id

  dynamic "image_mapping" {
    for_each = var.image_mapping
    content {
      # cloud_config - (optional) is a type of string
      cloud_config = image_mapping.value["cloud_config"]
      # image_id - (optional) is a type of string
      image_id = image_mapping.value["image_id"]
      # image_name - (optional) is a type of string
      image_name = image_mapping.value["image_name"]
      # name - (required) is a type of string
      name = image_mapping.value["name"]

      dynamic "constraints" {
        for_each = image_mapping.value.constraints
        content {
          # expression - (required) is a type of string
          expression = constraints.value["expression"]
          # mandatory - (required) is a type of bool
          mandatory = constraints.value["mandatory"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "created_at" {
  description = "returns a string"
  value       = vra_image_profile.this.created_at
}

output "external_region_id" {
  description = "returns a string"
  value       = vra_image_profile.this.external_region_id
}

output "id" {
  description = "returns a string"
  value       = vra_image_profile.this.id
}

output "owner" {
  description = "returns a string"
  value       = vra_image_profile.this.owner
}

output "updated_at" {
  description = "returns a string"
  value       = vra_image_profile.this.updated_at
}

output "this" {
  value = vra_image_profile.this
}
```

[top](#index)