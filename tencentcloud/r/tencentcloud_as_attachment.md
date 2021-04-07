# tencentcloud_as_attachment

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    tencentcloud = ">= 1.56.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "tencentcloud_as_attachment" {
  source = "./modules/tencentcloud/r/tencentcloud_as_attachment"

  # instance_ids - (required) is a type of set of string
  instance_ids = []
  # scaling_group_id - (required) is a type of string
  scaling_group_id = null
}
```

[top](#index)

### Variables

```terraform
variable "instance_ids" {
  description = "(required) - ID list of CVM instances to be attached to the scaling group."
  type        = set(string)
}

variable "scaling_group_id" {
  description = "(required) - ID of a scaling group."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_as_attachment" "this" {
  # instance_ids - (required) is a type of set of string
  instance_ids = var.instance_ids
  # scaling_group_id - (required) is a type of string
  scaling_group_id = var.scaling_group_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tencentcloud_as_attachment.this.id
}

output "this" {
  value = tencentcloud_as_attachment.this
}
```

[top](#index)