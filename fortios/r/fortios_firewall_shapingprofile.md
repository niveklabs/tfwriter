# fortios_firewall_shapingprofile

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.6.18"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_firewall_shapingprofile" {
  source = "./modules/fortios/r/fortios_firewall_shapingprofile"

  # comment - (optional) is a type of string
  comment = null
  # default_class_id - (required) is a type of number
  default_class_id = null
  # profile_name - (required) is a type of string
  profile_name = null

  shaping_entries = [{
    class_id                        = null
    guaranteed_bandwidth_percentage = null
    id                              = null
    maximum_bandwidth_percentage    = null
    priority                        = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "comment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "default_class_id" {
  description = "(required)"
  type        = number
}

variable "profile_name" {
  description = "(required)"
  type        = string
}

variable "shaping_entries" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      class_id                        = number
      guaranteed_bandwidth_percentage = number
      id                              = number
      maximum_bandwidth_percentage    = number
      priority                        = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_firewall_shapingprofile" "this" {
  comment          = var.comment
  default_class_id = var.default_class_id
  profile_name     = var.profile_name

  dynamic "shaping_entries" {
    for_each = var.shaping_entries
    content {
      class_id                        = shaping_entries.value["class_id"]
      guaranteed_bandwidth_percentage = shaping_entries.value["guaranteed_bandwidth_percentage"]
      id                              = shaping_entries.value["id"]
      maximum_bandwidth_percentage    = shaping_entries.value["maximum_bandwidth_percentage"]
      priority                        = shaping_entries.value["priority"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_firewall_shapingprofile.this.id
}

output "this" {
  value = fortios_firewall_shapingprofile.this
}
```

[top](#index)