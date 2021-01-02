# aws_media_package_channel

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
module "aws_media_package_channel" {
  source = "./modules/aws/r/aws_media_package_channel"

  # channel_id - (required) is a type of string
  channel_id = null
  # description - (optional) is a type of string
  description = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "channel_id" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_media_package_channel" "this" {
  channel_id  = var.channel_id
  description = var.description
  tags        = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_media_package_channel.this.arn
}

output "hls_ingest" {
  description = "returns a list of object"
  value       = aws_media_package_channel.this.hls_ingest
}

output "id" {
  description = "returns a string"
  value       = aws_media_package_channel.this.id
}

output "this" {
  value = aws_media_package_channel.this
}
```

[top](#index)