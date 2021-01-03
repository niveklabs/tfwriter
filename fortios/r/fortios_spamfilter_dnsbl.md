# fortios_spamfilter_dnsbl

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
module "fortios_spamfilter_dnsbl" {
  source = "./modules/fortios/r/fortios_spamfilter_dnsbl"

  # comment - (optional) is a type of string
  comment = null
  # fosid - (required) is a type of number
  fosid = null
  # name - (required) is a type of string
  name = null

  entries = [{
    action = null
    id     = null
    server = null
    status = null
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

variable "fosid" {
  description = "(required)"
  type        = number
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "entries" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action = string
      id     = number
      server = string
      status = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_spamfilter_dnsbl" "this" {
  comment = var.comment
  fosid   = var.fosid
  name    = var.name

  dynamic "entries" {
    for_each = var.entries
    content {
      action = entries.value["action"]
      id     = entries.value["id"]
      server = entries.value["server"]
      status = entries.value["status"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_spamfilter_dnsbl.this.id
}

output "this" {
  value = fortios_spamfilter_dnsbl.this
}
```

[top](#index)