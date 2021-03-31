# bigip_ltm_datagroup

[back](../bigip.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    bigip = ">= 1.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "bigip_ltm_datagroup" {
  source = "./modules/bigip/r/bigip_ltm_datagroup"

  # name - (required) is a type of string
  name = null
  # type - (required) is a type of string
  type = null

  record = [{
    data = null
    name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - Name of the Data Group List"
  type        = string
}

variable "type" {
  description = "(required) - The Data Group type (string, ip, integer)"
  type        = string
}

variable "record" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      data = string
      name = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "bigip_ltm_datagroup" "this" {
  name = var.name
  type = var.type

  dynamic "record" {
    for_each = var.record
    content {
      data = record.value["data"]
      name = record.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = bigip_ltm_datagroup.this.id
}

output "this" {
  value = bigip_ltm_datagroup.this
}
```

[top](#index)