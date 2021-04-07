# tencentcloud_cbs_snapshots

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
module "tencentcloud_cbs_snapshots" {
  source = "./modules/tencentcloud/d/tencentcloud_cbs_snapshots"

  # availability_zone - (optional) is a type of string
  availability_zone = null
  # project_id - (optional) is a type of number
  project_id = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
  # snapshot_id - (optional) is a type of string
  snapshot_id = null
  # snapshot_name - (optional) is a type of string
  snapshot_name = null
  # storage_id - (optional) is a type of string
  storage_id = null
  # storage_usage - (optional) is a type of string
  storage_usage = null
}
```

[top](#index)

### Variables

```terraform
variable "availability_zone" {
  description = "(optional) - The available zone that the CBS instance locates at."
  type        = string
  default     = null
}

variable "project_id" {
  description = "(optional) - ID of the project within the snapshot."
  type        = number
  default     = null
}

variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}

variable "snapshot_id" {
  description = "(optional) - ID of the snapshot to be queried."
  type        = string
  default     = null
}

variable "snapshot_name" {
  description = "(optional) - Name of the snapshot to be queried."
  type        = string
  default     = null
}

variable "storage_id" {
  description = "(optional) - ID of the the CBS which this snapshot created from."
  type        = string
  default     = null
}

variable "storage_usage" {
  description = "(optional) - Types of CBS which this snapshot created from, and available values include SYSTEM_DISK and DATA_DISK."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_cbs_snapshots" "this" {
  availability_zone  = var.availability_zone
  project_id         = var.project_id
  result_output_file = var.result_output_file
  snapshot_id        = var.snapshot_id
  snapshot_name      = var.snapshot_name
  storage_id         = var.storage_id
  storage_usage      = var.storage_usage
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_cbs_snapshots.this.id
}

output "snapshot_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_cbs_snapshots.this.snapshot_list
}

output "this" {
  value = tencentcloud_cbs_snapshots.this
}
```

[top](#index)