# tencentcloud_eip_association

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
module "tencentcloud_eip_association" {
  source = "./modules/tencentcloud/r/tencentcloud_eip_association"

  # eip_id - (required) is a type of string
  eip_id = null
  # instance_id - (optional) is a type of string
  instance_id = null
  # network_interface_id - (optional) is a type of string
  network_interface_id = null
  # private_ip - (optional) is a type of string
  private_ip = null
}
```

[top](#index)

### Variables

```terraform
variable "eip_id" {
  description = "(required) - The ID of EIP."
  type        = string
}

variable "instance_id" {
  description = "(optional) - The CVM or CLB instance id going to bind with the EIP. This field is conflict with `network_interface_id` and `private_ip fields`."
  type        = string
  default     = null
}

variable "network_interface_id" {
  description = "(optional) - Indicates the network interface id like `eni-xxxxxx`. This field is conflict with `instance_id`."
  type        = string
  default     = null
}

variable "private_ip" {
  description = "(optional) - Indicates an IP belongs to the `network_interface_id`. This field is conflict with `instance_id`."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_eip_association" "this" {
  # eip_id - (required) is a type of string
  eip_id = var.eip_id
  # instance_id - (optional) is a type of string
  instance_id = var.instance_id
  # network_interface_id - (optional) is a type of string
  network_interface_id = var.network_interface_id
  # private_ip - (optional) is a type of string
  private_ip = var.private_ip
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tencentcloud_eip_association.this.id
}

output "instance_id" {
  description = "returns a string"
  value       = tencentcloud_eip_association.this.instance_id
}

output "network_interface_id" {
  description = "returns a string"
  value       = tencentcloud_eip_association.this.network_interface_id
}

output "private_ip" {
  description = "returns a string"
  value       = tencentcloud_eip_association.this.private_ip
}

output "this" {
  value = tencentcloud_eip_association.this
}
```

[top](#index)