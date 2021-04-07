# tencentcloud_cbs_snapshot

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
module "tencentcloud_cbs_snapshot" {
  source = "./modules/tencentcloud/r/tencentcloud_cbs_snapshot"

  # snapshot_name - (required) is a type of string
  snapshot_name = null
  # storage_id - (required) is a type of string
  storage_id = null
}
```

[top](#index)

### Variables

```terraform
variable "snapshot_name" {
  description = "(required) - Name of the snapshot."
  type        = string
}

variable "storage_id" {
  description = "(required) - ID of the the CBS which this snapshot created from."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_cbs_snapshot" "this" {
  # snapshot_name - (required) is a type of string
  snapshot_name = var.snapshot_name
  # storage_id - (required) is a type of string
  storage_id = var.storage_id
}
```

[top](#index)

### Outputs

```terraform
output "create_time" {
  description = "returns a string"
  value       = tencentcloud_cbs_snapshot.this.create_time
}

output "disk_type" {
  description = "returns a string"
  value       = tencentcloud_cbs_snapshot.this.disk_type
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_cbs_snapshot.this.id
}

output "percent" {
  description = "returns a number"
  value       = tencentcloud_cbs_snapshot.this.percent
}

output "snapshot_status" {
  description = "returns a string"
  value       = tencentcloud_cbs_snapshot.this.snapshot_status
}

output "storage_size" {
  description = "returns a number"
  value       = tencentcloud_cbs_snapshot.this.storage_size
}

output "this" {
  value = tencentcloud_cbs_snapshot.this
}
```

[top](#index)