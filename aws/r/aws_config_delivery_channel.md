# aws_config_delivery_channel
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
module "aws_config_delivery_channel" {
  source = "./modules/aws/r/aws_config_delivery_channel"

  # name - (optional) is a type of string
  name = null
  # s3_bucket_name - (required) is a type of string
  s3_bucket_name = null
  # s3_key_prefix - (optional) is a type of string
  s3_key_prefix = null
  # sns_topic_arn - (optional) is a type of string
  sns_topic_arn = null

  snapshot_delivery_properties = [{
    delivery_frequency = null
  }]
}
```
[top](#index)
### Variables
```hcl
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "s3_bucket_name" {
  description = "(required)"
  type        = string
}

variable "s3_key_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sns_topic_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "snapshot_delivery_properties" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      delivery_frequency = string
    }
  ))
  default = []
}
```
[top](#index)

### Resource
```hcl
resource "aws_config_delivery_channel" "this" {
  name           = var.name
  s3_bucket_name = var.s3_bucket_name
  s3_key_prefix  = var.s3_key_prefix
  sns_topic_arn  = var.sns_topic_arn

  dynamic "snapshot_delivery_properties" {
    for_each = var.snapshot_delivery_properties
    content {
      delivery_frequency = snapshot_delivery_properties.value["delivery_frequency"]
    }
  }

}
```
[top](#index)
### Outputs
```hcl
output "id" {
  description = "returns a string"
  value       = aws_config_delivery_channel.this.id
}

output "this" {
  value = aws_config_delivery_channel.this
}
```
[top](#index)
