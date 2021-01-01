# aws_flow_log

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
module "aws_flow_log" {
  source = "./modules/aws/r/aws_flow_log"

  # eni_id - (optional) is a type of string
  eni_id = null
  # iam_role_arn - (optional) is a type of string
  iam_role_arn = null
  # log_destination - (optional) is a type of string
  log_destination = null
  # log_destination_type - (optional) is a type of string
  log_destination_type = null
  # log_format - (optional) is a type of string
  log_format = null
  # log_group_name - (optional) is a type of string
  log_group_name = null
  # max_aggregation_interval - (optional) is a type of number
  max_aggregation_interval = null
  # subnet_id - (optional) is a type of string
  subnet_id = null
  # tags - (optional) is a type of map of string
  tags = {}
  # traffic_type - (required) is a type of string
  traffic_type = null
  # vpc_id - (optional) is a type of string
  vpc_id = null
}
```

[top](#index)

### Variables

```hcl
variable "eni_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "iam_role_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "log_destination" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "log_destination_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "log_format" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "log_group_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "max_aggregation_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "subnet_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "traffic_type" {
  description = "(required)"
  type        = string
}

variable "vpc_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```hcl
resource "aws_flow_log" "this" {
  eni_id                   = var.eni_id
  iam_role_arn             = var.iam_role_arn
  log_destination          = var.log_destination
  log_destination_type     = var.log_destination_type
  log_format               = var.log_format
  log_group_name           = var.log_group_name
  max_aggregation_interval = var.max_aggregation_interval
  subnet_id                = var.subnet_id
  tags                     = var.tags
  traffic_type             = var.traffic_type
  vpc_id                   = var.vpc_id
}
```

[top](#index)

### Outputs

```hcl
output "arn" {
  description = "returns a string"
  value       = aws_flow_log.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_flow_log.this.id
}

output "log_destination" {
  description = "returns a string"
  value       = aws_flow_log.this.log_destination
}

output "log_format" {
  description = "returns a string"
  value       = aws_flow_log.this.log_format
}

output "log_group_name" {
  description = "returns a string"
  value       = aws_flow_log.this.log_group_name
}

output "this" {
  value = aws_flow_log.this
}
```

[top](#index)