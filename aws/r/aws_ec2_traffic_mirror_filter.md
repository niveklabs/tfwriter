# aws_ec2_traffic_mirror_filter

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
module "aws_ec2_traffic_mirror_filter" {
  source = "./modules/aws/r/aws_ec2_traffic_mirror_filter"

  # description - (optional) is a type of string
  description = null
  # network_services - (optional) is a type of set of string
  network_services = []
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "network_services" {
  description = "(optional)"
  type        = set(string)
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
resource "aws_ec2_traffic_mirror_filter" "this" {
  description      = var.description
  network_services = var.network_services
  tags             = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_ec2_traffic_mirror_filter.this.id
}

output "this" {
  value = aws_ec2_traffic_mirror_filter.this
}
```

[top](#index)