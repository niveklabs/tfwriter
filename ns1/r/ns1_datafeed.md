# ns1_datafeed

[back](../ns1.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ns1 = ">= 1.9.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ns1_datafeed" {
  source = "./modules/ns1/r/ns1_datafeed"

  # config - (optional) is a type of map of string
  config = {}
  # name - (required) is a type of string
  name = null
  # source_id - (required) is a type of string
  source_id = null
}
```

[top](#index)

### Variables

```terraform
variable "config" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "source_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "ns1_datafeed" "this" {
  # config - (optional) is a type of map of string
  config = var.config
  # name - (required) is a type of string
  name = var.name
  # source_id - (required) is a type of string
  source_id = var.source_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = ns1_datafeed.this.id
}

output "this" {
  value = ns1_datafeed.this
}
```

[top](#index)