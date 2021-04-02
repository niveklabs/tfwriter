# aws_sagemaker_app_image_config

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
module "aws_sagemaker_app_image_config" {
  source = "./modules/aws/r/aws_sagemaker_app_image_config"

  # app_image_config_name - (required) is a type of string
  app_image_config_name = null

  kernel_gateway_image_config = [{
    file_system_config = [{
      default_gid = null
      default_uid = null
      mount_path  = null
    }]
    kernel_spec = [{
      display_name = null
      name         = null
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "app_image_config_name" {
  description = "(required)"
  type        = string
}

variable "kernel_gateway_image_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      file_system_config = list(object(
        {
          default_gid = number
          default_uid = number
          mount_path  = string
        }
      ))
      kernel_spec = list(object(
        {
          display_name = string
          name         = string
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
resource "aws_sagemaker_app_image_config" "this" {
  app_image_config_name = var.app_image_config_name

  dynamic "kernel_gateway_image_config" {
    for_each = var.kernel_gateway_image_config
    content {

      dynamic "file_system_config" {
        for_each = kernel_gateway_image_config.value.file_system_config
        content {
          default_gid = file_system_config.value["default_gid"]
          default_uid = file_system_config.value["default_uid"]
          mount_path  = file_system_config.value["mount_path"]
        }
      }

      dynamic "kernel_spec" {
        for_each = kernel_gateway_image_config.value.kernel_spec
        content {
          display_name = kernel_spec.value["display_name"]
          name         = kernel_spec.value["name"]
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
  value       = aws_sagemaker_app_image_config.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_sagemaker_app_image_config.this.id
}

output "this" {
  value = aws_sagemaker_app_image_config.this
}
```

[top](#index)