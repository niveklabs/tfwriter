# aws_appmesh_virtual_service

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
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_appmesh_virtual_service" {
  source = "./modules/aws/r/aws_appmesh_virtual_service"

  # mesh_name - (required) is a type of string
  mesh_name = null
  # mesh_owner - (optional) is a type of string
  mesh_owner = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}

  spec = [{
    provider = [{
      virtual_node = [{
        virtual_node_name = null
      }]
      virtual_router = [{
        virtual_router_name = null
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
  description = "nested mode: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      provider = list(object(
        {
          virtual_node = list(object(
            {
              virtual_node_name = string
            }
          ))
          virtual_router = list(object(
            {
              virtual_router_name = string
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
resource "aws_appmesh_virtual_service" "this" {
  mesh_name  = var.mesh_name
  mesh_owner = var.mesh_owner
  name       = var.name
  tags       = var.tags

  dynamic "spec" {
    for_each = var.spec
    content {

      dynamic "provider" {
        for_each = spec.value.provider
        content {

          dynamic "virtual_node" {
            for_each = provider.value.virtual_node
            content {
              virtual_node_name = virtual_node.value["virtual_node_name"]
            }
          }

          dynamic "virtual_router" {
            for_each = provider.value.virtual_router
            content {
              virtual_router_name = virtual_router.value["virtual_router_name"]
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
  value       = aws_appmesh_virtual_service.this.arn
}

output "created_date" {
  description = "returns a string"
  value       = aws_appmesh_virtual_service.this.created_date
}

output "id" {
  description = "returns a string"
  value       = aws_appmesh_virtual_service.this.id
}

output "last_updated_date" {
  description = "returns a string"
  value       = aws_appmesh_virtual_service.this.last_updated_date
}

output "mesh_owner" {
  description = "returns a string"
  value       = aws_appmesh_virtual_service.this.mesh_owner
}

output "resource_owner" {
  description = "returns a string"
  value       = aws_appmesh_virtual_service.this.resource_owner
}

output "this" {
  value = aws_appmesh_virtual_service.this
}
```

[top](#index)