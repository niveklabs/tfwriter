# aws_appmesh_virtual_router

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aws = ">= 3.35.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_appmesh_virtual_router" {
  source = "./modules/aws/r/aws_appmesh_virtual_router"

  # mesh_name - (required) is a type of string
  mesh_name = null
  # mesh_owner - (optional) is a type of string
  mesh_owner = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}

  spec = [{
    listener = [{
      port_mapping = [{
        port     = null
        protocol = null
      }]
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "mesh_name" {
  description = "(required)"
  type        = string
}

variable "mesh_owner" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "spec" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      listener = list(object(
        {
          port_mapping = list(object(
            {
              port     = number
              protocol = string
            }
          ))
        }
      ))
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "aws_appmesh_virtual_router" "this" {
  # mesh_name - (required) is a type of string
  mesh_name = var.mesh_name
  # mesh_owner - (optional) is a type of string
  mesh_owner = var.mesh_owner
  # name - (required) is a type of string
  name = var.name
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "spec" {
    for_each = var.spec
    content {

      dynamic "listener" {
        for_each = spec.value.listener
        content {

          dynamic "port_mapping" {
            for_each = listener.value.port_mapping
            content {
              # port - (required) is a type of number
              port = port_mapping.value["port"]
              # protocol - (required) is a type of string
              protocol = port_mapping.value["protocol"]
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
output "arn" {
  description = "returns a string"
  value       = aws_appmesh_virtual_router.this.arn
}

output "created_date" {
  description = "returns a string"
  value       = aws_appmesh_virtual_router.this.created_date
}

output "id" {
  description = "returns a string"
  value       = aws_appmesh_virtual_router.this.id
}

output "last_updated_date" {
  description = "returns a string"
  value       = aws_appmesh_virtual_router.this.last_updated_date
}

output "mesh_owner" {
  description = "returns a string"
  value       = aws_appmesh_virtual_router.this.mesh_owner
}

output "resource_owner" {
  description = "returns a string"
  value       = aws_appmesh_virtual_router.this.resource_owner
}

output "this" {
  value = aws_appmesh_virtual_router.this
}
```

[top](#index)