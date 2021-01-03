# azurestack_dns_a_record

[back](../azurestack.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    azurestack = ">= 0.9.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurestack_dns_a_record" {
  source = "./modules/azurestack/r/azurestack_dns_a_record"

  # name - (required) is a type of string
  name = null
  # records - (required) is a type of set of string
  records = []
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # ttl - (required) is a type of number
  ttl = null
  # zone_name - (required) is a type of string
  zone_name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "records" {
  description = "(required)"
  type        = set(string)
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "ttl" {
  description = "(required)"
  type        = number
}

variable "zone_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "azurestack_dns_a_record" "this" {
  name                = var.name
  records             = var.records
  resource_group_name = var.resource_group_name
  tags                = var.tags
  ttl                 = var.ttl
  zone_name           = var.zone_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azurestack_dns_a_record.this.id
}

output "tags" {
  description = "returns a map of string"
  value       = azurestack_dns_a_record.this.tags
}

output "this" {
  value = azurestack_dns_a_record.this
}
```

[top](#index)