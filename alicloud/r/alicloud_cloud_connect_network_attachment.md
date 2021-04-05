# alicloud_cloud_connect_network_attachment

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
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_cloud_connect_network_attachment" {
  source = "./modules/alicloud/r/alicloud_cloud_connect_network_attachment"

  # ccn_id - (required) is a type of string
  ccn_id = null
  # sag_id - (required) is a type of string
  sag_id = null
}
```

[top](#index)

### Variables

```terraform
variable "ccn_id" {
  description = "(required)"
  type        = string
}

variable "sag_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_cloud_connect_network_attachment" "this" {
  ccn_id = var.ccn_id
  sag_id = var.sag_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_cloud_connect_network_attachment.this.id
}

output "this" {
  value = alicloud_cloud_connect_network_attachment.this
}
```

[top](#index)