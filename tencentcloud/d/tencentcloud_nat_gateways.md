# tencentcloud_nat_gateways

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
module "tencentcloud_nat_gateways" {
  source = "./modules/tencentcloud/d/tencentcloud_nat_gateways"

  # name - (optional) is a type of string
  name = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
  # vpc_id - (optional) is a type of string
  vpc_id = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional) - Name of the NAT gateway."
  type        = string
  default     = null
}

variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}

variable "vpc_id" {
  description = "(optional) - ID of the VPC."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_nat_gateways" "this" {
  name               = var.name
  result_output_file = var.result_output_file
  vpc_id             = var.vpc_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_nat_gateways.this.id
}

output "nats" {
  description = "returns a list of object"
  value       = data.tencentcloud_nat_gateways.this.nats
}

output "this" {
  value = tencentcloud_nat_gateways.this
}
```

[top](#index)