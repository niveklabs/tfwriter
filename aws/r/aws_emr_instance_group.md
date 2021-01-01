# aws_emr_instance_group

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
module "aws_emr_instance_group" {
  source = "./modules/aws/r/aws_emr_instance_group"

  # autoscaling_policy - (optional) is a type of string
  autoscaling_policy = null
  # bid_price - (optional) is a type of string
  bid_price = null
  # cluster_id - (required) is a type of string
  cluster_id = null
  # configurations_json - (optional) is a type of string
  configurations_json = null
  # ebs_optimized - (optional) is a type of bool
  ebs_optimized = null
  # instance_count - (optional) is a type of number
  instance_count = null
  # instance_type - (required) is a type of string
  instance_type = null
  # name - (optional) is a type of string
  name = null

  ebs_config = [{
    iops                 = null
    size                 = null
    type                 = null
    volumes_per_instance = null
  }]
}
```

[top](#index)

### Variables

```hcl
variable "autoscaling_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "bid_price" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cluster_id" {
  description = "(required)"
  type        = string
}

variable "configurations_json" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ebs_optimized" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "instance_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "instance_type" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ebs_config" {
  description = "nested mode: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      iops                 = number
      size                 = number
      type                 = string
      volumes_per_instance = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```hcl
resource "aws_emr_instance_group" "this" {
  autoscaling_policy  = var.autoscaling_policy
  bid_price           = var.bid_price
  cluster_id          = var.cluster_id
  configurations_json = var.configurations_json
  ebs_optimized       = var.ebs_optimized
  instance_count      = var.instance_count
  instance_type       = var.instance_type
  name                = var.name

  dynamic "ebs_config" {
    for_each = var.ebs_config
    content {
      iops                 = ebs_config.value["iops"]
      size                 = ebs_config.value["size"]
      type                 = ebs_config.value["type"]
      volumes_per_instance = ebs_config.value["volumes_per_instance"]
    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = aws_emr_instance_group.this.id
}

output "running_instance_count" {
  description = "returns a number"
  value       = aws_emr_instance_group.this.running_instance_count
}

output "status" {
  description = "returns a string"
  value       = aws_emr_instance_group.this.status
}

output "this" {
  value = aws_emr_instance_group.this
}
```

[top](#index)