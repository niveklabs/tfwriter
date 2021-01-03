# alicloud_subnet

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
    alicloud = ">= 1.111.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_subnet" {
  source = "./modules/alicloud/r/alicloud_subnet"

  # availability_zone - (required) is a type of string
  availability_zone = null
  # cidr_block - (required) is a type of string
  cidr_block = null
  # description - (optional) is a type of string
  description = null
  # name - (optional) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # vpc_id - (required) is a type of string
  vpc_id = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "availability_zone" {
  description = "(required)"
  type        = string
}

variable "cidr_block" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "vpc_id" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_subnet" "this" {
  availability_zone = var.availability_zone
  cidr_block        = var.cidr_block
  description       = var.description
  name              = var.name
  tags              = var.tags
  vpc_id            = var.vpc_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_subnet.this.id
}

output "this" {
  value = alicloud_subnet.this
}
```

[top](#index)