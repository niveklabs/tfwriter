# aws_codebuild_webhook
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
module "aws_codebuild_webhook" {
  source = "./modules/aws/r/aws_codebuild_webhook"

  # branch_filter - (optional) is a type of string
  branch_filter = null
  # project_name - (required) is a type of string
  project_name = null

  filter_group = [{
    filter = [{
      exclude_matched_pattern = null
      pattern                 = null
      type                    = null
    }]
  }]
}
```
[top](#index)
### Variables
```hcl
variable "branch_filter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "project_name" {
  description = "(required)"
  type        = string
}

variable "filter_group" {
  description = "nested mode: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      filter = list(object(
        {
          exclude_matched_pattern = bool
          pattern                 = string
          type                    = string
        }
      ))
    }
  ))
  default = []
}
```
[top](#index)

### Resource
```hcl
resource "aws_codebuild_webhook" "this" {
  branch_filter = var.branch_filter
  project_name  = var.project_name

  dynamic "filter_group" {
    for_each = var.filter_group
    content {

      dynamic "filter" {
        for_each = filter_group.value.filter
        content {
          exclude_matched_pattern = filter.value["exclude_matched_pattern"]
          pattern                 = filter.value["pattern"]
          type                    = filter.value["type"]
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
  value       = aws_codebuild_webhook.this.id
}

output "payload_url" {
  description = "returns a string"
  value       = aws_codebuild_webhook.this.payload_url
}

output "secret" {
  description = "returns a string"
  value       = aws_codebuild_webhook.this.secret
  sensitive   = true
}

output "url" {
  description = "returns a string"
  value       = aws_codebuild_webhook.this.url
}

output "this" {
  value = aws_codebuild_webhook.this
}
```
[top](#index)
