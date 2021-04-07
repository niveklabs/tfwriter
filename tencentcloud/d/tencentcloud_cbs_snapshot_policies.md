# tencentcloud_cbs_snapshot_policies

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "tencentcloud_cbs_snapshot_policies" {
  source = "./modules/tencentcloud/d/tencentcloud_cbs_snapshot_policies"

  # result_output_file - (optional) is a type of string
  result_output_file = null
  # snapshot_policy_id - (optional) is a type of string
  snapshot_policy_id = null
  # snapshot_policy_name - (optional) is a type of string
  snapshot_policy_name = null
}
```

[top](#index)

### Variables

```terraform
variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}

variable "snapshot_policy_id" {
  description = "(optional) - ID of the snapshot policy to be queried."
  type        = string
  default     = null
}

variable "snapshot_policy_name" {
  description = "(optional) - Name of the snapshot policy to be queried."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_cbs_snapshot_policies" "this" {
  result_output_file   = var.result_output_file
  snapshot_policy_id   = var.snapshot_policy_id
  snapshot_policy_name = var.snapshot_policy_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_cbs_snapshot_policies.this.id
}

output "snapshot_policy_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_cbs_snapshot_policies.this.snapshot_policy_list
}

output "this" {
  value = tencentcloud_cbs_snapshot_policies.this
}
```

[top](#index)