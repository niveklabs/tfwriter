# aws_ssm_resource_data_sync

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
module "aws_ssm_resource_data_sync" {
  source = "./modules/aws/r/aws_ssm_resource_data_sync"

  # name - (required) is a type of string
  name = null

  s3_destination = [{
    bucket_name = null
    kms_key_arn = null
    prefix      = null
    region      = null
    sync_format = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "s3_destination" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      bucket_name = string
      kms_key_arn = string
      prefix      = string
      region      = string
      sync_format = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "aws_ssm_resource_data_sync" "this" {
  # name - (required) is a type of string
  name = var.name

  dynamic "s3_destination" {
    for_each = var.s3_destination
    content {
      # bucket_name - (required) is a type of string
      bucket_name = s3_destination.value["bucket_name"]
      # kms_key_arn - (optional) is a type of string
      kms_key_arn = s3_destination.value["kms_key_arn"]
      # prefix - (optional) is a type of string
      prefix = s3_destination.value["prefix"]
      # region - (required) is a type of string
      region = s3_destination.value["region"]
      # sync_format - (optional) is a type of string
      sync_format = s3_destination.value["sync_format"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_ssm_resource_data_sync.this.id
}

output "this" {
  value = aws_ssm_resource_data_sync.this
}
```

[top](#index)