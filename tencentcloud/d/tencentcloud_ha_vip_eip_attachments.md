# tencentcloud_ha_vip_eip_attachments

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
module "tencentcloud_ha_vip_eip_attachments" {
  source = "./modules/tencentcloud/d/tencentcloud_ha_vip_eip_attachments"

  # address_ip - (optional) is a type of string
  address_ip = null
  # havip_id - (required) is a type of string
  havip_id = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "address_ip" {
  description = "(optional) - Public IP address of EIP to be queried."
  type        = string
  default     = null
}

variable "havip_id" {
  description = "(required) - ID of the attached HA VIP to be queried."
  type        = string
}

variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_ha_vip_eip_attachments" "this" {
  # address_ip - (optional) is a type of string
  address_ip = var.address_ip
  # havip_id - (required) is a type of string
  havip_id = var.havip_id
  # result_output_file - (optional) is a type of string
  result_output_file = var.result_output_file
}
```

[top](#index)

### Outputs

```terraform
output "ha_vip_eip_attachment_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_ha_vip_eip_attachments.this.ha_vip_eip_attachment_list
}

output "id" {
  description = "returns a string"
  value       = data.tencentcloud_ha_vip_eip_attachments.this.id
}

output "this" {
  value = tencentcloud_ha_vip_eip_attachments.this
}
```

[top](#index)