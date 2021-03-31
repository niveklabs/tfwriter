# alicloud_slb_server_certificates

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
    alicloud = ">= 1.119.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_slb_server_certificates" {
  source = "./modules/alicloud/d/alicloud_slb_server_certificates"

  # ids - (optional) is a type of list of string
  ids = []
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # resource_group_id - (optional) is a type of string
  resource_group_id = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
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

variable "resource_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_slb_server_certificates" "this" {
  ids               = var.ids
  name_regex        = var.name_regex
  output_file       = var.output_file
  resource_group_id = var.resource_group_id
  tags              = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "certificates" {
  description = "returns a list of object"
  value       = data.alicloud_slb_server_certificates.this.certificates
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_slb_server_certificates.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_slb_server_certificates.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_slb_server_certificates.this.names
}

output "this" {
  value = alicloud_slb_server_certificates.this
}
```

[top](#index)