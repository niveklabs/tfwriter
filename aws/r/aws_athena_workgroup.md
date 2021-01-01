# aws_athena_workgroup
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
module "aws_athena_workgroup" {
  source = "./modules/aws/r/aws_athena_workgroup"

  # description - (optional) is a type of string
  description = null
  # force_destroy - (optional) is a type of bool
  force_destroy = null
  # name - (required) is a type of string
  name = null
  # state - (optional) is a type of string
  state = null
  # tags - (optional) is a type of map of string
  tags = {}

  configuration = [{
    bytes_scanned_cutoff_per_query     = null
    enforce_workgroup_configuration    = null
    publish_cloudwatch_metrics_enabled = null
    result_configuration = [{
      encryption_configuration = [{
        encryption_option = null
        kms_key_arn       = null
      }]
      output_location = null
    }]
  }]
}
```
[top](#index)
### Variables
```hcl
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "force_destroy" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "configuration" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      bytes_scanned_cutoff_per_query     = number
      enforce_workgroup_configuration    = bool
      publish_cloudwatch_metrics_enabled = bool
      result_configuration = list(object(
        {
          encryption_configuration = list(object(
            {
              encryption_option = string
              kms_key_arn       = string
            }
          ))
          output_location = string
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
resource "aws_athena_workgroup" "this" {
  description   = var.description
  force_destroy = var.force_destroy
  name          = var.name
  state         = var.state
  tags          = var.tags

  dynamic "configuration" {
    for_each = var.configuration
    content {
      bytes_scanned_cutoff_per_query     = configuration.value["bytes_scanned_cutoff_per_query"]
      enforce_workgroup_configuration    = configuration.value["enforce_workgroup_configuration"]
      publish_cloudwatch_metrics_enabled = configuration.value["publish_cloudwatch_metrics_enabled"]

      dynamic "result_configuration" {
        for_each = configuration.value.result_configuration
        content {
          output_location = result_configuration.value["output_location"]

          dynamic "encryption_configuration" {
            for_each = result_configuration.value.encryption_configuration
            content {
              encryption_option = encryption_configuration.value["encryption_option"]
              kms_key_arn       = encryption_configuration.value["kms_key_arn"]
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
```hcl
output "arn" {
  description = "returns a string"
  value       = aws_athena_workgroup.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_athena_workgroup.this.id
}

output "this" {
  value = aws_athena_workgroup.this
}
```
[top](#index)
