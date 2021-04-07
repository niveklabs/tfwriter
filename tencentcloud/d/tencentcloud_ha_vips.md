# tencentcloud_ha_vips

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
module "tencentcloud_ha_vips" {
  source = "./modules/tencentcloud/d/tencentcloud_ha_vips"

  # address_ip - (optional) is a type of string
  address_ip = null
  # name - (optional) is a type of string
  name = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
  # subnet_id - (optional) is a type of string
  subnet_id = null
  # vpc_id - (optional) is a type of string
  vpc_id = null
}
```

[top](#index)

### Variables

```terraform
variable "address_ip" {
  description = "(optional) - EIP of the HA VIP to be queried."
  type        = string
  default     = null
}

variable "name" {
  description = "(optional) - Name of the HA VIP. The length of character is limited to 1-60."
  type        = string
  default     = null
}

variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}

variable "subnet_id" {
  description = "(optional) - Subnet id of the HA VIP to be queried."
  type        = string
  default     = null
}

variable "vpc_id" {
  description = "(optional) - VPC id of the HA VIP to be queried."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_ha_vips" "this" {
  # address_ip - (optional) is a type of string
  address_ip = var.address_ip
  # name - (optional) is a type of string
  name = var.name
  # result_output_file - (optional) is a type of string
  result_output_file = var.result_output_file
  # subnet_id - (optional) is a type of string
  subnet_id = var.subnet_id
  # vpc_id - (optional) is a type of string
  vpc_id = var.vpc_id
}
```

[top](#index)

### Outputs

```terraform
output "ha_vip_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_ha_vips.this.ha_vip_list
}

output "id" {
  description = "returns a string"
  value       = data.tencentcloud_ha_vips.this.id
}

output "this" {
  value = tencentcloud_ha_vips.this
}
```

[top](#index)