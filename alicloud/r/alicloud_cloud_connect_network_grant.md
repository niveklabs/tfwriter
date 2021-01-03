# alicloud_cloud_connect_network_grant

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "alicloud_cloud_connect_network_grant" {
  source = "./modules/alicloud/r/alicloud_cloud_connect_network_grant"

  # ccn_id - (required) is a type of string
  ccn_id = null
  # cen_id - (required) is a type of string
  cen_id = null
  # cen_uid - (required) is a type of string
  cen_uid = null
}
```

[top](#index)

### Variables

```terraform
variable "ccn_id" {
  description = "(required)"
  type        = string
}

variable "cen_id" {
  description = "(required)"
  type        = string
}

variable "cen_uid" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_cloud_connect_network_grant" "this" {
  ccn_id  = var.ccn_id
  cen_id  = var.cen_id
  cen_uid = var.cen_uid
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_cloud_connect_network_grant.this.id
}

output "this" {
  value = alicloud_cloud_connect_network_grant.this
}
```

[top](#index)