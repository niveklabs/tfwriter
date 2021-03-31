# dome9_cloud_security_group_rule

[back](../dome9.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    dome9 = ">= 1.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "dome9_cloud_security_group_rule" {
  source = "./modules/dome9/r/dome9_cloud_security_group_rule"

  # dome9_security_group_id - (required) is a type of string
  dome9_security_group_id = null

  services = [{
    inbound = [{
      description   = null
      name          = null
      open_for_all  = null
      port          = null
      protocol_type = null
      scope = [{
        data = {}
        type = null
      }]
    }]
    outbound = [{
      description   = null
      name          = null
      open_for_all  = null
      port          = null
      protocol_type = null
      scope = [{
        data = {}
        type = null
      }]
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "dome9_security_group_id" {
  description = "(required)"
  type        = string
}

variable "services" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      inbound = set(object(
        {
          description   = string
          name          = string
          open_for_all  = bool
          port          = string
          protocol_type = string
          scope = set(object(
            {
              data = map(string)
              type = string
            }
          ))
        }
      ))
      outbound = set(object(
        {
          description   = string
          name          = string
          open_for_all  = bool
          port          = string
          protocol_type = string
          scope = set(object(
            {
              data = map(string)
              type = string
            }
          ))
        }
      ))
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "dome9_cloud_security_group_rule" "this" {
  dome9_security_group_id = var.dome9_security_group_id

  dynamic "services" {
    for_each = var.services
    content {

      dynamic "inbound" {
        for_each = services.value.inbound
        content {
          description   = inbound.value["description"]
          name          = inbound.value["name"]
          open_for_all  = inbound.value["open_for_all"]
          port          = inbound.value["port"]
          protocol_type = inbound.value["protocol_type"]

          dynamic "scope" {
            for_each = inbound.value.scope
            content {
              data = scope.value["data"]
              type = scope.value["type"]
            }
          }

        }
      }

      dynamic "outbound" {
        for_each = services.value.outbound
        content {
          description   = outbound.value["description"]
          name          = outbound.value["name"]
          open_for_all  = outbound.value["open_for_all"]
          port          = outbound.value["port"]
          protocol_type = outbound.value["protocol_type"]

          dynamic "scope" {
            for_each = outbound.value.scope
            content {
              data = scope.value["data"]
              type = scope.value["type"]
            }
          }

        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = dome9_cloud_security_group_rule.this.id
}

output "this" {
  value = dome9_cloud_security_group_rule.this
}
```

[top](#index)