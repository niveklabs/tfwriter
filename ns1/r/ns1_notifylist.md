# ns1_notifylist

[back](../ns1.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ns1 = ">= 1.9.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ns1_notifylist" {
  source = "./modules/ns1/r/ns1_notifylist"

  # name - (required) is a type of string
  name = null

  notifications = [{
    config = {}
    type   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "notifications" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      config = map(string)
      type   = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "ns1_notifylist" "this" {
  name = var.name

  dynamic "notifications" {
    for_each = var.notifications
    content {
      config = notifications.value["config"]
      type   = notifications.value["type"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = ns1_notifylist.this.id
}

output "this" {
  value = ns1_notifylist.this
}
```

[top](#index)