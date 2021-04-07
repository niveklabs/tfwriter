# thunder_slb_template_dynamic_service

[back](../thunder.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    thunder = ">= 0.4.16"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "thunder_slb_template_dynamic_service" {
  source = "./modules/thunder/r/thunder_slb_template_dynamic_service"

  # name - (optional) is a type of string
  name = null
  # user_tag - (optional) is a type of string
  user_tag = null
  # uuid - (optional) is a type of string
  uuid = null

  dns_server = [{
    ipv4_dns_server = null
    ipv6_dns_server = null
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

variable "user_tag" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dns_server" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      ipv4_dns_server = string
      ipv6_dns_server = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "thunder_slb_template_dynamic_service" "this" {
  # name - (optional) is a type of string
  name = var.name
  # user_tag - (optional) is a type of string
  user_tag = var.user_tag
  # uuid - (optional) is a type of string
  uuid = var.uuid

  dynamic "dns_server" {
    for_each = var.dns_server
    content {
      # ipv4_dns_server - (optional) is a type of string
      ipv4_dns_server = dns_server.value["ipv4_dns_server"]
      # ipv6_dns_server - (optional) is a type of string
      ipv6_dns_server = dns_server.value["ipv6_dns_server"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_slb_template_dynamic_service.this.id
}

output "this" {
  value = thunder_slb_template_dynamic_service.this
}
```

[top](#index)