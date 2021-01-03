# fortios_ips_decoder

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
module "fortios_ips_decoder" {
  source = "./modules/fortios/r/fortios_ips_decoder"

  # name - (optional) is a type of string
  name = null

  parameter = [{
    name  = null
    value = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "parameter" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name  = string
      value = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_ips_decoder" "this" {
  name = var.name

  dynamic "parameter" {
    for_each = var.parameter
    content {
      name  = parameter.value["name"]
      value = parameter.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_ips_decoder.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_ips_decoder.this.name
}

output "this" {
  value = fortios_ips_decoder.this
}
```

[top](#index)