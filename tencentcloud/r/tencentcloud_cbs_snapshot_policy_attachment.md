# tencentcloud_cbs_snapshot_policy_attachment

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
module "tencentcloud_cbs_snapshot_policy_attachment" {
  source = "./modules/tencentcloud/r/tencentcloud_cbs_snapshot_policy_attachment"

  # snapshot_policy_id - (required) is a type of string
  snapshot_policy_id = null
  # storage_id - (required) is a type of string
  storage_id = null
}
```

[top](#index)

### Variables

```terraform
variable "snapshot_policy_id" {
  description = "(required) - ID of CBS snapshot policy."
  type        = string
}

variable "storage_id" {
  description = "(required) - ID of CBS."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_cbs_snapshot_policy_attachment" "this" {
  # snapshot_policy_id - (required) is a type of string
  snapshot_policy_id = var.snapshot_policy_id
  # storage_id - (required) is a type of string
  storage_id = var.storage_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tencentcloud_cbs_snapshot_policy_attachment.this.id
}

output "this" {
  value = tencentcloud_cbs_snapshot_policy_attachment.this
}
```

[top](#index)