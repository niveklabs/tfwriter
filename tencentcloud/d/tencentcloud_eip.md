# tencentcloud_eip

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
module "tencentcloud_eip" {
  source = "./modules/tencentcloud/d/tencentcloud_eip"

  # include_arrears - (optional) is a type of bool
  include_arrears = null
  # include_blocked - (optional) is a type of bool
  include_blocked = null

  filter = [{
    name   = null
    values = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "include_arrears" {
  description = "(optional) - Whether the IP is arrears."
  type        = bool
  default     = null
}

variable "include_blocked" {
  description = "(optional) - Whether the IP is blocked."
  type        = bool
  default     = null
}

variable "filter" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name   = string
      values = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_eip" "this" {
  # include_arrears - (optional) is a type of bool
  include_arrears = var.include_arrears
  # include_blocked - (optional) is a type of bool
  include_blocked = var.include_blocked

  dynamic "filter" {
    for_each = var.filter
    content {
      # name - (required) is a type of string
      name = filter.value["name"]
      # values - (required) is a type of list of string
      values = filter.value["values"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_eip.this.id
}

output "public_ip" {
  description = "returns a string"
  value       = data.tencentcloud_eip.this.public_ip
}

output "status" {
  description = "returns a string"
  value       = data.tencentcloud_eip.this.status
}

output "this" {
  value = tencentcloud_eip.this
}
```

[top](#index)