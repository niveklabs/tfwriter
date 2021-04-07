# tencentcloud_ha_vip_eip_attachment

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
module "tencentcloud_ha_vip_eip_attachment" {
  source = "./modules/tencentcloud/r/tencentcloud_ha_vip_eip_attachment"

  # address_ip - (required) is a type of string
  address_ip = null
  # havip_id - (required) is a type of string
  havip_id = null
}
```

[top](#index)

### Variables

```terraform
variable "address_ip" {
  description = "(required) - Public address of the EIP."
  type        = string
}

variable "havip_id" {
  description = "(required) - ID of the attached HA VIP."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_ha_vip_eip_attachment" "this" {
  address_ip = var.address_ip
  havip_id   = var.havip_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tencentcloud_ha_vip_eip_attachment.this.id
}

output "this" {
  value = tencentcloud_ha_vip_eip_attachment.this
}
```

[top](#index)