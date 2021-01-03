# alicloud_mse_clusters

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
    alicloud = ">= 1.111.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_mse_clusters" {
  source = "./modules/alicloud/d/alicloud_mse_clusters"

  # cluster_alias_name - (optional) is a type of string
  cluster_alias_name = null
  # enable_details - (optional) is a type of bool
  enable_details = null
  # ids - (optional) is a type of list of string
  ids = []
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # request_pars - (optional) is a type of string
  request_pars = null
  # status - (optional) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
variable "cluster_alias_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enable_details" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "name_regex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "request_pars" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_mse_clusters" "this" {
  cluster_alias_name = var.cluster_alias_name
  enable_details     = var.enable_details
  ids                = var.ids
  name_regex         = var.name_regex
  output_file        = var.output_file
  request_pars       = var.request_pars
  status             = var.status
}
```

[top](#index)

### Outputs

```terraform
output "clusters" {
  description = "returns a list of object"
  value       = data.alicloud_mse_clusters.this.clusters
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_mse_clusters.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_mse_clusters.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_mse_clusters.this.names
}

output "this" {
  value = alicloud_mse_clusters.this
}
```

[top](#index)