# aws_ec2_instance_type_offering

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "aws_ec2_instance_type_offering" {
  source = "./modules/aws/d/aws_ec2_instance_type_offering"

  # location_type - (optional) is a type of string
  location_type = null
  # preferred_instance_types - (optional) is a type of list of string
  preferred_instance_types = []

  filter = [{
    name   = null
    values = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "location_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "preferred_instance_types" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "filter" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name   = string
      values = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "aws_ec2_instance_type_offering" "this" {
  # location_type - (optional) is a type of string
  location_type = var.location_type
  # preferred_instance_types - (optional) is a type of list of string
  preferred_instance_types = var.preferred_instance_types

  dynamic "filter" {
    for_each = var.filter
    content {
      # name - (required) is a type of string
      name = filter.value["name"]
      # values - (required) is a type of list of string
      values = filter.value["values"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.aws_ec2_instance_type_offering.this.id
}

output "instance_type" {
  description = "returns a string"
  value       = data.aws_ec2_instance_type_offering.this.instance_type
}

output "this" {
  value = aws_ec2_instance_type_offering.this
}
```

[top](#index)