# tencentcloud_vpn_customer_gateway

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
module "tencentcloud_vpn_customer_gateway" {
  source = "./modules/tencentcloud/r/tencentcloud_vpn_customer_gateway"

  # name - (required) is a type of string
  name = null
  # public_ip_address - (required) is a type of string
  public_ip_address = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - Name of the customer gateway. The length of character is limited to 1-60."
  type        = string
}

variable "public_ip_address" {
  description = "(required) - Public IP of the customer gateway."
  type        = string
}

variable "tags" {
  description = "(optional) - A list of tags used to associate different resources."
  type        = map(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_vpn_customer_gateway" "this" {
  name              = var.name
  public_ip_address = var.public_ip_address
  tags              = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "create_time" {
  description = "returns a string"
  value       = tencentcloud_vpn_customer_gateway.this.create_time
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_vpn_customer_gateway.this.id
}

output "this" {
  value = tencentcloud_vpn_customer_gateway.this
}
```

[top](#index)