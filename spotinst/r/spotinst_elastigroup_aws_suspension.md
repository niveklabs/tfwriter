# spotinst_elastigroup_aws_suspension

[back](../spotinst.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    spotinst = ">= 1.27.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "spotinst_elastigroup_aws_suspension" {
  source = "./modules/spotinst/r/spotinst_elastigroup_aws_suspension"

  # group_id - (required) is a type of string
  group_id = null

  suspension = [{
    name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "group_id" {
  description = "(required)"
  type        = string
}

variable "suspension" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "spotinst_elastigroup_aws_suspension" "this" {
  group_id = var.group_id

  dynamic "suspension" {
    for_each = var.suspension
    content {
      name = suspension.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = spotinst_elastigroup_aws_suspension.this.id
}

output "this" {
  value = spotinst_elastigroup_aws_suspension.this
}
```

[top](#index)