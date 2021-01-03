# fortios_webfilter_content

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
module "fortios_webfilter_content" {
  source = "./modules/fortios/r/fortios_webfilter_content"

  # comment - (optional) is a type of string
  comment = null
  # fosid - (required) is a type of number
  fosid = null
  # name - (required) is a type of string
  name = null

  entries = [{
    action       = null
    lang         = null
    name         = null
    pattern_type = null
    score        = null
    status       = null
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
      action       = string
      lang         = string
      name         = string
      pattern_type = string
      score        = number
      status       = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_webfilter_content" "this" {
  comment = var.comment
  fosid   = var.fosid
  name    = var.name

  dynamic "entries" {
    for_each = var.entries
    content {
      action       = entries.value["action"]
      lang         = entries.value["lang"]
      name         = entries.value["name"]
      pattern_type = entries.value["pattern_type"]
      score        = entries.value["score"]
      status       = entries.value["status"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_webfilter_content.this.id
}

output "this" {
  value = fortios_webfilter_content.this
}
```

[top](#index)