# fortios_system_apiuser_setting

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
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_system_apiuser_setting" {
  source = "./modules/fortios/r/fortios_system_apiuser_setting"

  # accprofile - (required) is a type of string
  accprofile = null
  # comments - (optional) is a type of string
  comments = null
  # name - (required) is a type of string
  name = null
  # vdom - (required) is a type of list of string
  vdom = []

  trusthost = [{
    ipv4_trusthost = null
    type           = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "accprofile" {
  description = "(required)"
  type        = string
}

variable "comments" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "vdom" {
  description = "(required)"
  type        = list(string)
}

variable "trusthost" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      ipv4_trusthost = string
      type           = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_apiuser_setting" "this" {
  # accprofile - (required) is a type of string
  accprofile = var.accprofile
  # comments - (optional) is a type of string
  comments = var.comments
  # name - (required) is a type of string
  name = var.name
  # vdom - (required) is a type of list of string
  vdom = var.vdom

  dynamic "trusthost" {
    for_each = var.trusthost
    content {
      # ipv4_trusthost - (required) is a type of string
      ipv4_trusthost = trusthost.value["ipv4_trusthost"]
      # type - (required) is a type of string
      type = trusthost.value["type"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_system_apiuser_setting.this.id
}

output "this" {
  value = fortios_system_apiuser_setting.this
}
```

[top](#index)