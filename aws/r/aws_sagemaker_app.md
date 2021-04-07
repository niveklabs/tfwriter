# aws_sagemaker_app

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
module "aws_sagemaker_app" {
  source = "./modules/aws/r/aws_sagemaker_app"

  # app_name - (required) is a type of string
  app_name = null
  # app_type - (required) is a type of string
  app_type = null
  # domain_id - (required) is a type of string
  domain_id = null
  # tags - (optional) is a type of map of string
  tags = {}
  # user_profile_name - (required) is a type of string
  user_profile_name = null

  resource_spec = [{
    instance_type       = null
    sagemaker_image_arn = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "app_name" {
  description = "(required)"
  type        = string
}

variable "app_type" {
  description = "(required)"
  type        = string
}

variable "domain_id" {
  description = "(required)"
  type        = string
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

variable "resource_spec" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      instance_type       = string
      sagemaker_image_arn = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_sagemaker_app" "this" {
  # app_name - (required) is a type of string
  app_name = var.app_name
  # app_type - (required) is a type of string
  app_type = var.app_type
  # domain_id - (required) is a type of string
  domain_id = var.domain_id
  # tags - (optional) is a type of map of string
  tags = var.tags
  # user_profile_name - (required) is a type of string
  user_profile_name = var.user_profile_name

  dynamic "resource_spec" {
    for_each = var.resource_spec
    content {
      # instance_type - (optional) is a type of string
      instance_type = resource_spec.value["instance_type"]
      # sagemaker_image_arn - (optional) is a type of string
      sagemaker_image_arn = resource_spec.value["sagemaker_image_arn"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_sagemaker_app.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_sagemaker_app.this.id
}

output "this" {
  value = aws_sagemaker_app.this
}
```

[top](#index)