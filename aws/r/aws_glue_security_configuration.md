# aws_glue_security_configuration

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
module "aws_glue_security_configuration" {
  source = "./modules/aws/r/aws_glue_security_configuration"

  # name - (required) is a type of string
  name = null

  encryption_configuration = [{
    cloudwatch_encryption = [{
      cloudwatch_encryption_mode = null
      kms_key_arn                = null
    }]
    job_bookmarks_encryption = [{
      job_bookmarks_encryption_mode = null
      kms_key_arn                   = null
    }]
    s3_encryption = [{
      kms_key_arn        = null
      s3_encryption_mode = null
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

variable "encryption_configuration" {
  description = "nested mode: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      cloudwatch_encryption = list(object(
        {
          cloudwatch_encryption_mode = string
          kms_key_arn                = string
        }
      ))
      job_bookmarks_encryption = list(object(
        {
          job_bookmarks_encryption_mode = string
          kms_key_arn                   = string
        }
      ))
      s3_encryption = list(object(
        {
          kms_key_arn        = string
          s3_encryption_mode = string
        }
      ))
    }
  ))
}
```

[top](#index)

### Resource

```hcl
resource "aws_glue_security_configuration" "this" {
  name = var.name

  dynamic "encryption_configuration" {
    for_each = var.encryption_configuration
    content {

      dynamic "cloudwatch_encryption" {
        for_each = encryption_configuration.value.cloudwatch_encryption
        content {
          cloudwatch_encryption_mode = cloudwatch_encryption.value["cloudwatch_encryption_mode"]
          kms_key_arn                = cloudwatch_encryption.value["kms_key_arn"]
        }
      }

      dynamic "job_bookmarks_encryption" {
        for_each = encryption_configuration.value.job_bookmarks_encryption
        content {
          job_bookmarks_encryption_mode = job_bookmarks_encryption.value["job_bookmarks_encryption_mode"]
          kms_key_arn                   = job_bookmarks_encryption.value["kms_key_arn"]
        }
      }

      dynamic "s3_encryption" {
        for_each = encryption_configuration.value.s3_encryption
        content {
          kms_key_arn        = s3_encryption.value["kms_key_arn"]
          s3_encryption_mode = s3_encryption.value["s3_encryption_mode"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = aws_glue_security_configuration.this.id
}

output "this" {
  value = aws_glue_security_configuration.this
}
```

[top](#index)