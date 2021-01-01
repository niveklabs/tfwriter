# aws_glue_data_catalog_encryption_settings
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
module "aws_glue_data_catalog_encryption_settings" {
  source = "./modules/aws/r/aws_glue_data_catalog_encryption_settings"

  # catalog_id - (optional) is a type of string
  catalog_id = null

  data_catalog_encryption_settings = [{
    connection_password_encryption = [{
      aws_kms_key_id                       = null
      return_connection_password_encrypted = null
    }]
    encryption_at_rest = [{
      catalog_encryption_mode = null
      sse_aws_kms_key_id      = null
    }]
  }]
}
```
[top](#index)
### Variables
```hcl
variable "catalog_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "data_catalog_encryption_settings" {
  description = "nested mode: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      connection_password_encryption = list(object(
        {
          aws_kms_key_id                       = string
          return_connection_password_encrypted = bool
        }
      ))
      encryption_at_rest = list(object(
        {
          catalog_encryption_mode = string
          sse_aws_kms_key_id      = string
        }
      ))
    }
  ))
}
```
[top](#index)

### Resource
```hcl
resource "aws_glue_data_catalog_encryption_settings" "this" {
  catalog_id = var.catalog_id

  dynamic "data_catalog_encryption_settings" {
    for_each = var.data_catalog_encryption_settings
    content {

      dynamic "connection_password_encryption" {
        for_each = data_catalog_encryption_settings.value.connection_password_encryption
        content {
          aws_kms_key_id                       = connection_password_encryption.value["aws_kms_key_id"]
          return_connection_password_encrypted = connection_password_encryption.value["return_connection_password_encrypted"]
        }
      }

      dynamic "encryption_at_rest" {
        for_each = data_catalog_encryption_settings.value.encryption_at_rest
        content {
          catalog_encryption_mode = encryption_at_rest.value["catalog_encryption_mode"]
          sse_aws_kms_key_id      = encryption_at_rest.value["sse_aws_kms_key_id"]
        }
      }

    }
  }

}
```
[top](#index)
### Outputs
```hcl
output "catalog_id" {
  description = "returns a string"
  value       = aws_glue_data_catalog_encryption_settings.this.catalog_id
}

output "id" {
  description = "returns a string"
  value       = aws_glue_data_catalog_encryption_settings.this.id
}

output "this" {
  value = aws_glue_data_catalog_encryption_settings.this
}
```
[top](#index)
