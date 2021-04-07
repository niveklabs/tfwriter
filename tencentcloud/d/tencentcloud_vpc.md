# tencentcloud_vpc

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
module "tencentcloud_vpc" {
  source = "./modules/tencentcloud/d/tencentcloud_vpc"

  # name - (optional) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional) - The name of the specific VPC to retrieve."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_vpc" "this" {
  # name - (optional) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "cidr_block" {
  description = "returns a string"
  value       = data.tencentcloud_vpc.this.cidr_block
}

output "id" {
  description = "returns a string"
  value       = data.tencentcloud_vpc.this.id
}

output "is_default" {
  description = "returns a bool"
  value       = data.tencentcloud_vpc.this.is_default
}

output "is_multicast" {
  description = "returns a bool"
  value       = data.tencentcloud_vpc.this.is_multicast
}

output "name" {
  description = "returns a string"
  value       = data.tencentcloud_vpc.this.name
}

output "this" {
  value = tencentcloud_vpc.this
}
```

[top](#index)