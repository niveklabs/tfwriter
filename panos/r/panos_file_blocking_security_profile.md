# panos_file_blocking_security_profile

[back](../panos.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    panos = ">= 1.8.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_file_blocking_security_profile" {
  source = "./modules/panos/r/panos_file_blocking_security_profile"

  # description - (optional) is a type of string
  description = null
  # device_group - (optional) is a type of string
  device_group = null
  # name - (required) is a type of string
  name = null
  # vsys - (optional) is a type of string
  vsys = null

  rule = [{
    action       = null
    applications = []
    direction    = null
    file_types   = []
    name         = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Description"
  type        = string
  default     = null
}

variable "device_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Security profile name"
  type        = string
}

variable "vsys" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rule" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action       = string
      applications = list(string)
      direction    = string
      file_types   = list(string)
      name         = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "panos_file_blocking_security_profile" "this" {
  # description - (optional) is a type of string
  description = var.description
  # device_group - (optional) is a type of string
  device_group = var.device_group
  # name - (required) is a type of string
  name = var.name
  # vsys - (optional) is a type of string
  vsys = var.vsys

  dynamic "rule" {
    for_each = var.rule
    content {
      # action - (optional) is a type of string
      action = rule.value["action"]
      # applications - (optional) is a type of list of string
      applications = rule.value["applications"]
      # direction - (optional) is a type of string
      direction = rule.value["direction"]
      # file_types - (optional) is a type of list of string
      file_types = rule.value["file_types"]
      # name - (required) is a type of string
      name = rule.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_file_blocking_security_profile.this.id
}

output "this" {
  value = panos_file_blocking_security_profile.this
}
```

[top](#index)