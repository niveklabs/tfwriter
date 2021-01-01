# aws_imagebuilder_image_recipe

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "aws_imagebuilder_image_recipe" {
  source = "./modules/aws/r/aws_imagebuilder_image_recipe"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # parent_image - (required) is a type of string
  parent_image = null
  # tags - (optional) is a type of map of string
  tags = {}
  # version - (required) is a type of string
  version = null

  block_device_mapping = [{
    device_name = null
    ebs = [{
      delete_on_termination = null
      encrypted             = null
      iops                  = null
      kms_key_id            = null
      snapshot_id           = null
      volume_size           = null
      volume_type           = null
    }]
    no_device    = null
    virtual_name = null
  }]

  component = [{
    component_arn = null
  }]
}
```

[top](#index)

### Variables

```hcl
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "parent_image" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "version" {
  description = "(required)"
  type        = string
}

variable "block_device_mapping" {
  description = "nested mode: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      device_name = string
      ebs = list(object(
        {
          delete_on_termination = string
          encrypted             = string
          iops                  = number
          kms_key_id            = string
          snapshot_id           = string
          volume_size           = number
          volume_type           = string
        }
      ))
      no_device    = bool
      virtual_name = string
    }
  ))
  default = []
}

variable "component" {
  description = "nested mode: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      component_arn = string
    }
  ))
}
```

[top](#index)

### Resource

```hcl
resource "aws_imagebuilder_image_recipe" "this" {
  description  = var.description
  name         = var.name
  parent_image = var.parent_image
  tags         = var.tags
  version      = var.version

  dynamic "block_device_mapping" {
    for_each = var.block_device_mapping
    content {
      device_name  = block_device_mapping.value["device_name"]
      no_device    = block_device_mapping.value["no_device"]
      virtual_name = block_device_mapping.value["virtual_name"]

      dynamic "ebs" {
        for_each = block_device_mapping.value.ebs
        content {
          delete_on_termination = ebs.value["delete_on_termination"]
          encrypted             = ebs.value["encrypted"]
          iops                  = ebs.value["iops"]
          kms_key_id            = ebs.value["kms_key_id"]
          snapshot_id           = ebs.value["snapshot_id"]
          volume_size           = ebs.value["volume_size"]
          volume_type           = ebs.value["volume_type"]
        }
      }

    }
  }

  dynamic "component" {
    for_each = var.component
    content {
      component_arn = component.value["component_arn"]
    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "arn" {
  description = "returns a string"
  value       = aws_imagebuilder_image_recipe.this.arn
}

output "date_created" {
  description = "returns a string"
  value       = aws_imagebuilder_image_recipe.this.date_created
}

output "id" {
  description = "returns a string"
  value       = aws_imagebuilder_image_recipe.this.id
}

output "owner" {
  description = "returns a string"
  value       = aws_imagebuilder_image_recipe.this.owner
}

output "platform" {
  description = "returns a string"
  value       = aws_imagebuilder_image_recipe.this.platform
}

output "this" {
  value = aws_imagebuilder_image_recipe.this
}
```

[top](#index)