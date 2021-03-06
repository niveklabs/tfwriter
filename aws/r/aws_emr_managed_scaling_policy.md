# aws_emr_managed_scaling_policy

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
    aws = ">= 3.35.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_emr_managed_scaling_policy" {
  source = "./modules/aws/r/aws_emr_managed_scaling_policy"

  # cluster_id - (required) is a type of string
  cluster_id = null

  compute_limits = [{
    maximum_capacity_units          = null
    maximum_core_capacity_units     = null
    maximum_ondemand_capacity_units = null
    minimum_capacity_units          = null
    unit_type                       = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "cluster_id" {
  description = "(required)"
  type        = string
}

variable "compute_limits" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      maximum_capacity_units          = number
      maximum_core_capacity_units     = number
      maximum_ondemand_capacity_units = number
      minimum_capacity_units          = number
      unit_type                       = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "aws_emr_managed_scaling_policy" "this" {
  # cluster_id - (required) is a type of string
  cluster_id = var.cluster_id

  dynamic "compute_limits" {
    for_each = var.compute_limits
    content {
      # maximum_capacity_units - (required) is a type of number
      maximum_capacity_units = compute_limits.value["maximum_capacity_units"]
      # maximum_core_capacity_units - (optional) is a type of number
      maximum_core_capacity_units = compute_limits.value["maximum_core_capacity_units"]
      # maximum_ondemand_capacity_units - (optional) is a type of number
      maximum_ondemand_capacity_units = compute_limits.value["maximum_ondemand_capacity_units"]
      # minimum_capacity_units - (required) is a type of number
      minimum_capacity_units = compute_limits.value["minimum_capacity_units"]
      # unit_type - (required) is a type of string
      unit_type = compute_limits.value["unit_type"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_emr_managed_scaling_policy.this.id
}

output "this" {
  value = aws_emr_managed_scaling_policy.this
}
```

[top](#index)