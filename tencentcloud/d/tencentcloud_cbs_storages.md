# tencentcloud_cbs_storages

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
module "tencentcloud_cbs_storages" {
  source = "./modules/tencentcloud/d/tencentcloud_cbs_storages"

  # availability_zone - (optional) is a type of string
  availability_zone = null
  # project_id - (optional) is a type of number
  project_id = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
  # storage_id - (optional) is a type of string
  storage_id = null
  # storage_name - (optional) is a type of string
  storage_name = null
  # storage_type - (optional) is a type of string
  storage_type = null
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
  description = "(optional) - ID of the project with which the CBS is associated."
  type        = number
  default     = null
}

variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}

variable "storage_id" {
  description = "(optional) - ID of the CBS to be queried."
  type        = string
  default     = null
}

variable "storage_name" {
  description = "(optional) - Name of the CBS to be queried."
  type        = string
  default     = null
}

variable "storage_type" {
  description = "(optional) - Filter by cloud disk media type (`CLOUD_BASIC`: HDD cloud disk | `CLOUD_PREMIUM`: Premium Cloud Storage | `CLOUD_SSD`: SSD cloud disk)."
  type        = string
  default     = null
}

variable "storage_usage" {
  description = "(optional) - Filter by cloud disk type (`SYSTEM_DISK`: system disk | `DATA_DISK`: data disk)."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_cbs_storages" "this" {
  availability_zone  = var.availability_zone
  project_id         = var.project_id
  result_output_file = var.result_output_file
  storage_id         = var.storage_id
  storage_name       = var.storage_name
  storage_type       = var.storage_type
  storage_usage      = var.storage_usage
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_cbs_storages.this.id
}

output "storage_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_cbs_storages.this.storage_list
}

output "this" {
  value = tencentcloud_cbs_storages.this
}
```

[top](#index)