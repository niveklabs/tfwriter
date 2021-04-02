# aws_sagemaker_domain

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
module "aws_sagemaker_domain" {
  source = "./modules/aws/r/aws_sagemaker_domain"

  # app_network_access_type - (optional) is a type of string
  app_network_access_type = null
  # auth_mode - (required) is a type of string
  auth_mode = null
  # domain_name - (required) is a type of string
  domain_name = null
  # kms_key_id - (optional) is a type of string
  kms_key_id = null
  # subnet_ids - (required) is a type of set of string
  subnet_ids = []
  # tags - (optional) is a type of map of string
  tags = {}
  # vpc_id - (required) is a type of string
  vpc_id = null

  default_user_settings = [{
    execution_role = null
    jupyter_server_app_settings = [{
      default_resource_spec = [{
        instance_type       = null
        sagemaker_image_arn = null
      }]
    }]
    kernel_gateway_app_settings = [{
      custom_image = [{
        app_image_config_name = null
        image_name            = null
        image_version_number  = null
      }]
      default_resource_spec = [{
        instance_type       = null
        sagemaker_image_arn = null
      }]
    }]
    security_groups = []
    sharing_settings = [{
      notebook_output_option = null
      s3_kms_key_id          = null
      s3_output_path         = null
    }]
    tensor_board_app_settings = [{
      default_resource_spec = [{
        instance_type       = null
        sagemaker_image_arn = null
      }]
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "app_network_access_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auth_mode" {
  description = "(required)"
  type        = string
}

variable "domain_name" {
  description = "(required)"
  type        = string
}

variable "kms_key_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "subnet_ids" {
  description = "(required)"
  type        = set(string)
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "vpc_id" {
  description = "(required)"
  type        = string
}

variable "default_user_settings" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      execution_role = string
      jupyter_server_app_settings = list(object(
        {
          default_resource_spec = list(object(
            {
              instance_type       = string
              sagemaker_image_arn = string
            }
          ))
        }
      ))
      kernel_gateway_app_settings = list(object(
        {
          custom_image = list(object(
            {
              app_image_config_name = string
              image_name            = string
              image_version_number  = number
            }
          ))
          default_resource_spec = list(object(
            {
              instance_type       = string
              sagemaker_image_arn = string
            }
          ))
        }
      ))
      security_groups = set(string)
      sharing_settings = list(object(
        {
          notebook_output_option = string
          s3_kms_key_id          = string
          s3_output_path         = string
        }
      ))
      tensor_board_app_settings = list(object(
        {
          default_resource_spec = list(object(
            {
              instance_type       = string
              sagemaker_image_arn = string
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
resource "aws_sagemaker_domain" "this" {
  app_network_access_type = var.app_network_access_type
  auth_mode               = var.auth_mode
  domain_name             = var.domain_name
  kms_key_id              = var.kms_key_id
  subnet_ids              = var.subnet_ids
  tags                    = var.tags
  vpc_id                  = var.vpc_id

  dynamic "default_user_settings" {
    for_each = var.default_user_settings
    content {
      execution_role  = default_user_settings.value["execution_role"]
      security_groups = default_user_settings.value["security_groups"]

      dynamic "jupyter_server_app_settings" {
        for_each = default_user_settings.value.jupyter_server_app_settings
        content {

          dynamic "default_resource_spec" {
            for_each = jupyter_server_app_settings.value.default_resource_spec
            content {
              instance_type       = default_resource_spec.value["instance_type"]
              sagemaker_image_arn = default_resource_spec.value["sagemaker_image_arn"]
            }
          }

        }
      }

      dynamic "kernel_gateway_app_settings" {
        for_each = default_user_settings.value.kernel_gateway_app_settings
        content {

          dynamic "custom_image" {
            for_each = kernel_gateway_app_settings.value.custom_image
            content {
              app_image_config_name = custom_image.value["app_image_config_name"]
              image_name            = custom_image.value["image_name"]
              image_version_number  = custom_image.value["image_version_number"]
            }
          }

          dynamic "default_resource_spec" {
            for_each = kernel_gateway_app_settings.value.default_resource_spec
            content {
              instance_type       = default_resource_spec.value["instance_type"]
              sagemaker_image_arn = default_resource_spec.value["sagemaker_image_arn"]
            }
          }

        }
      }

      dynamic "sharing_settings" {
        for_each = default_user_settings.value.sharing_settings
        content {
          notebook_output_option = sharing_settings.value["notebook_output_option"]
          s3_kms_key_id          = sharing_settings.value["s3_kms_key_id"]
          s3_output_path         = sharing_settings.value["s3_output_path"]
        }
      }

      dynamic "tensor_board_app_settings" {
        for_each = default_user_settings.value.tensor_board_app_settings
        content {

          dynamic "default_resource_spec" {
            for_each = tensor_board_app_settings.value.default_resource_spec
            content {
              instance_type       = default_resource_spec.value["instance_type"]
              sagemaker_image_arn = default_resource_spec.value["sagemaker_image_arn"]
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
  value       = aws_sagemaker_domain.this.arn
}

output "home_efs_file_system_id" {
  description = "returns a string"
  value       = aws_sagemaker_domain.this.home_efs_file_system_id
}

output "id" {
  description = "returns a string"
  value       = aws_sagemaker_domain.this.id
}

output "single_sign_on_managed_application_instance_id" {
  description = "returns a string"
  value       = aws_sagemaker_domain.this.single_sign_on_managed_application_instance_id
}

output "url" {
  description = "returns a string"
  value       = aws_sagemaker_domain.this.url
}

output "this" {
  value = aws_sagemaker_domain.this
}
```

[top](#index)