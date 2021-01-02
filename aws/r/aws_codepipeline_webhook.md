# aws_codepipeline_webhook

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
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_codepipeline_webhook" {
  source = "./modules/aws/r/aws_codepipeline_webhook"

  # authentication - (required) is a type of string
  authentication = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # target_action - (required) is a type of string
  target_action = null
  # target_pipeline - (required) is a type of string
  target_pipeline = null

  authentication_configuration = [{
    allowed_ip_range = null
    secret_token     = null
  }]

  filter = [{
    json_path    = null
    match_equals = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "authentication" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "target_action" {
  description = "(required)"
  type        = string
}

variable "target_pipeline" {
  description = "(required)"
  type        = string
}

variable "authentication_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      allowed_ip_range = string
      secret_token     = string
    }
  ))
  default = []
}

variable "filter" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      json_path    = string
      match_equals = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "aws_codepipeline_webhook" "this" {
  authentication  = var.authentication
  name            = var.name
  tags            = var.tags
  target_action   = var.target_action
  target_pipeline = var.target_pipeline

  dynamic "authentication_configuration" {
    for_each = var.authentication_configuration
    content {
      allowed_ip_range = authentication_configuration.value["allowed_ip_range"]
      secret_token     = authentication_configuration.value["secret_token"]
    }
  }

  dynamic "filter" {
    for_each = var.filter
    content {
      json_path    = filter.value["json_path"]
      match_equals = filter.value["match_equals"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_codepipeline_webhook.this.id
}

output "url" {
  description = "returns a string"
  value       = aws_codepipeline_webhook.this.url
}

output "this" {
  value = aws_codepipeline_webhook.this
}
```

[top](#index)