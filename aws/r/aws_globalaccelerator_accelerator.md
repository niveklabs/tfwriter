# aws_globalaccelerator_accelerator

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
module "aws_globalaccelerator_accelerator" {
  source = "./modules/aws/r/aws_globalaccelerator_accelerator"

  # enabled - (optional) is a type of bool
  enabled = null
  # ip_address_type - (optional) is a type of string
  ip_address_type = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}

  attributes = [{
    flow_logs_enabled   = null
    flow_logs_s3_bucket = null
    flow_logs_s3_prefix = null
  }]
}
```

[top](#index)

### Variables

```hcl
variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ip_address_type" {
  description = "(optional)"
  type        = string
  default     = null
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

variable "attributes" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      flow_logs_enabled   = bool
      flow_logs_s3_bucket = string
      flow_logs_s3_prefix = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```hcl
resource "aws_globalaccelerator_accelerator" "this" {
  enabled         = var.enabled
  ip_address_type = var.ip_address_type
  name            = var.name
  tags            = var.tags

  dynamic "attributes" {
    for_each = var.attributes
    content {
      flow_logs_enabled   = attributes.value["flow_logs_enabled"]
      flow_logs_s3_bucket = attributes.value["flow_logs_s3_bucket"]
      flow_logs_s3_prefix = attributes.value["flow_logs_s3_prefix"]
    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "dns_name" {
  description = "returns a string"
  value       = aws_globalaccelerator_accelerator.this.dns_name
}

output "hosted_zone_id" {
  description = "returns a string"
  value       = aws_globalaccelerator_accelerator.this.hosted_zone_id
}

output "id" {
  description = "returns a string"
  value       = aws_globalaccelerator_accelerator.this.id
}

output "ip_sets" {
  description = "returns a list of object"
  value       = aws_globalaccelerator_accelerator.this.ip_sets
}

output "this" {
  value = aws_globalaccelerator_accelerator.this
}
```

[top](#index)