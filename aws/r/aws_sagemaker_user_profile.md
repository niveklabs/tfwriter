# aws_sagemaker_user_profile

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
    aws = ">= 3.34.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_sagemaker_user_profile" {
  source = "./modules/aws/r/aws_sagemaker_user_profile"

  # domain_id - (required) is a type of string
  domain_id = null
  # single_sign_on_user_identifier - (optional) is a type of string
  single_sign_on_user_identifier = null
  # single_sign_on_user_value - (optional) is a type of string
  single_sign_on_user_value = null
  # tags - (optional) is a type of map of string
  tags = {}
  # user_profile_name - (required) is a type of string
  user_profile_name = null

  user_settings = [{
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
variable "domain_id" {
  description = "(required)"
  type        = string
}

variable "single_sign_on_user_identifier" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "single_sign_on_user_value" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "user_profile_name" {
  description = "(required)"
  type        = string
}

variable "user_settings" {
  description = "nested block: NestingList, min items: 0, max items: 1"
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
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_sagemaker_user_profile" "this" {
  domain_id                      = var.domain_id
  single_sign_on_user_identifier = var.single_sign_on_user_identifier
  single_sign_on_user_value      = var.single_sign_on_user_value
  tags                           = var.tags
  user_profile_name              = var.user_profile_name

  dynamic "user_settings" {
    for_each = var.user_settings
    content {
      execution_role  = user_settings.value["execution_role"]
      security_groups = user_settings.value["security_groups"]

      dynamic "jupyter_server_app_settings" {
        for_each = user_settings.value.jupyter_server_app_settings
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
        for_each = user_settings.value.kernel_gateway_app_settings
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
        for_each = user_settings.value.sharing_settings
        content {
          notebook_output_option = sharing_settings.value["notebook_output_option"]
          s3_kms_key_id          = sharing_settings.value["s3_kms_key_id"]
          s3_output_path         = sharing_settings.value["s3_output_path"]
        }
      }

      dynamic "tensor_board_app_settings" {
        for_each = user_settings.value.tensor_board_app_settings
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
  value       = aws_sagemaker_user_profile.this.arn
}

output "home_efs_file_system_uid" {
  description = "returns a string"
  value       = aws_sagemaker_user_profile.this.home_efs_file_system_uid
}

output "id" {
  description = "returns a string"
  value       = aws_sagemaker_user_profile.this.id
}

output "this" {
  value = aws_sagemaker_user_profile.this
}
```

[top](#index)