# aws_imagebuilder_image_recipe

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
  # working_directory - (optional) is a type of string
  working_directory = null

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

```terraform
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

variable "working_directory" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "block_device_mapping" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
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
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      component_arn = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "aws_imagebuilder_image_recipe" "this" {
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # parent_image - (required) is a type of string
  parent_image = var.parent_image
  # tags - (optional) is a type of map of string
  tags = var.tags
  # version - (required) is a type of string
  version = var.version
  # working_directory - (optional) is a type of string
  working_directory = var.working_directory

  dynamic "block_device_mapping" {
    for_each = var.block_device_mapping
    content {
      # device_name - (optional) is a type of string
      device_name = block_device_mapping.value["device_name"]
      # no_device - (optional) is a type of bool
      no_device = block_device_mapping.value["no_device"]
      # virtual_name - (optional) is a type of string
      virtual_name = block_device_mapping.value["virtual_name"]

      dynamic "ebs" {
        for_each = block_device_mapping.value.ebs
        content {
          # delete_on_termination - (optional) is a type of string
          delete_on_termination = ebs.value["delete_on_termination"]
          # encrypted - (optional) is a type of string
          encrypted = ebs.value["encrypted"]
          # iops - (optional) is a type of number
          iops = ebs.value["iops"]
          # kms_key_id - (optional) is a type of string
          kms_key_id = ebs.value["kms_key_id"]
          # snapshot_id - (optional) is a type of string
          snapshot_id = ebs.value["snapshot_id"]
          # volume_size - (optional) is a type of number
          volume_size = ebs.value["volume_size"]
          # volume_type - (optional) is a type of string
          volume_type = ebs.value["volume_type"]
        }
      }

    }
  }

  dynamic "component" {
    for_each = var.component
    content {
      # component_arn - (required) is a type of string
      component_arn = component.value["component_arn"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
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