# alicloud_emr_main_versions

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_emr_main_versions" {
  source = "./modules/alicloud/d/alicloud_emr_main_versions"

  # cluster_type - (optional) is a type of list of string
  cluster_type = []
  # emr_version - (optional) is a type of string
  emr_version = null
  # output_file - (optional) is a type of string
  output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "cluster_type" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "emr_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_emr_main_versions" "this" {
  cluster_type = var.cluster_type
  emr_version  = var.emr_version
  output_file  = var.output_file
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_emr_main_versions.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_emr_main_versions.this.ids
}

output "main_versions" {
  description = "returns a list of object"
  value       = data.alicloud_emr_main_versions.this.main_versions
}

output "this" {
  value = alicloud_emr_main_versions.this
}
```

[top](#index)