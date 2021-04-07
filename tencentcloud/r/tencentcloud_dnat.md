# tencentcloud_dnat

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
module "tencentcloud_dnat" {
  source = "./modules/tencentcloud/r/tencentcloud_dnat"

  # description - (optional) is a type of string
  description = null
  # elastic_ip - (required) is a type of string
  elastic_ip = null
  # elastic_port - (required) is a type of string
  elastic_port = null
  # nat_id - (required) is a type of string
  nat_id = null
  # private_ip - (required) is a type of string
  private_ip = null
  # private_port - (required) is a type of string
  private_port = null
  # protocol - (required) is a type of string
  protocol = null
  # vpc_id - (required) is a type of string
  vpc_id = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Description of the NAT forward."
  type        = string
  default     = null
}

variable "elastic_ip" {
  description = "(required) - Network address of the EIP."
  type        = string
}

variable "elastic_port" {
  description = "(required) - Port of the EIP."
  type        = string
}

variable "nat_id" {
  description = "(required) - ID of the NAT gateway."
  type        = string
}

variable "private_ip" {
  description = "(required) - Network address of the backend service."
  type        = string
}

variable "private_port" {
  description = "(required) - Port of intranet."
  type        = string
}

variable "protocol" {
  description = "(required) - Type of the network protocol. Valid value: `TCP` and `UDP`."
  type        = string
}

variable "vpc_id" {
  description = "(required) - ID of the VPC."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_dnat" "this" {
  description  = var.description
  elastic_ip   = var.elastic_ip
  elastic_port = var.elastic_port
  nat_id       = var.nat_id
  private_ip   = var.private_ip
  private_port = var.private_port
  protocol     = var.protocol
  vpc_id       = var.vpc_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tencentcloud_dnat.this.id
}

output "this" {
  value = tencentcloud_dnat.this
}
```

[top](#index)