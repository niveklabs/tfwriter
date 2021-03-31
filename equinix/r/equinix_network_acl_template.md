# equinix_network_acl_template

[back](../equinix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    equinix = ">= 1.1.0-beta"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "equinix_network_acl_template" {
  source = "./modules/equinix/r/equinix_network_acl_template"

  # description - (optional) is a type of string
  description = null
  # metro_code - (required) is a type of string
  metro_code = null
  # name - (required) is a type of string
  name = null

  inbound_rule = [{
    dst_port        = null
    protocol        = null
    sequence_number = null
    source_type     = null
    src_port        = null
    subnets         = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - ACL template description"
  type        = string
  default     = null
}

variable "metro_code" {
  description = "(required) - ACL template location metro code"
  type        = string
}

variable "name" {
  description = "(required) - ACL template name"
  type        = string
}

variable "inbound_rule" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      dst_port        = string
      protocol        = string
      sequence_number = number
      source_type     = string
      src_port        = string
      subnets         = list(string)
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "equinix_network_acl_template" "this" {
  description = var.description
  metro_code  = var.metro_code
  name        = var.name

  dynamic "inbound_rule" {
    for_each = var.inbound_rule
    content {
      dst_port = inbound_rule.value["dst_port"]
      protocol = inbound_rule.value["protocol"]
      src_port = inbound_rule.value["src_port"]
      subnets  = inbound_rule.value["subnets"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "device_acl_status" {
  description = "returns a string"
  value       = equinix_network_acl_template.this.device_acl_status
}

output "device_id" {
  description = "returns a string"
  value       = equinix_network_acl_template.this.device_id
}

output "id" {
  description = "returns a string"
  value       = equinix_network_acl_template.this.id
}

output "uuid" {
  description = "returns a string"
  value       = equinix_network_acl_template.this.uuid
}

output "this" {
  value = equinix_network_acl_template.this
}
```

[top](#index)