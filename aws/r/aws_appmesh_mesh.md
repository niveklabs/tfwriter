# aws_appmesh_mesh

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "aws_appmesh_mesh" {
  source = "./modules/aws/r/aws_appmesh_mesh"

  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}

  spec = [{
    egress_filter = [{
      type = null
    }]
  }]
}
```

[top](#index)

### Variables

```hcl
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
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      egress_filter = list(object(
        {
          type = string
        }
      ))
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```hcl
resource "aws_appmesh_mesh" "this" {
  name = var.name
  tags = var.tags

  dynamic "spec" {
    for_each = var.spec
    content {

      dynamic "egress_filter" {
        for_each = spec.value.egress_filter
        content {
          type = egress_filter.value["type"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "arn" {
  description = "returns a string"
  value       = aws_appmesh_mesh.this.arn
}

output "created_date" {
  description = "returns a string"
  value       = aws_appmesh_mesh.this.created_date
}

output "id" {
  description = "returns a string"
  value       = aws_appmesh_mesh.this.id
}

output "last_updated_date" {
  description = "returns a string"
  value       = aws_appmesh_mesh.this.last_updated_date
}

output "mesh_owner" {
  description = "returns a string"
  value       = aws_appmesh_mesh.this.mesh_owner
}

output "resource_owner" {
  description = "returns a string"
  value       = aws_appmesh_mesh.this.resource_owner
}

output "this" {
  value = aws_appmesh_mesh.this
}
```

[top](#index)