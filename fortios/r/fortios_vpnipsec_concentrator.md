# fortios_vpnipsec_concentrator

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
module "fortios_vpnipsec_concentrator" {
  source = "./modules/fortios/r/fortios_vpnipsec_concentrator"

  # name - (optional) is a type of string
  name = null
  # src_check - (optional) is a type of string
  src_check = null

  member = [{
    name = null
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

variable "src_check" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "member" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_vpnipsec_concentrator" "this" {
  name      = var.name
  src_check = var.src_check

  dynamic "member" {
    for_each = var.member
    content {
      name = member.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_vpnipsec_concentrator.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_vpnipsec_concentrator.this.name
}

output "src_check" {
  description = "returns a string"
  value       = fortios_vpnipsec_concentrator.this.src_check
}

output "this" {
  value = fortios_vpnipsec_concentrator.this
}
```

[top](#index)