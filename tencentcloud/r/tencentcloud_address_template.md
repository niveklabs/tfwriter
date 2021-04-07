# tencentcloud_address_template

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
module "tencentcloud_address_template" {
  source = "./modules/tencentcloud/r/tencentcloud_address_template"

  # addresses - (required) is a type of set of string
  addresses = []
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "addresses" {
  description = "(required) - Address list. IP(`10.0.0.1`), CIDR(`10.0.1.0/24`), IP range(`10.0.0.1-10.0.0.100`) format are supported."
  type        = set(string)
}

variable "name" {
  description = "(required) - Name of the address template."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_address_template" "this" {
  # addresses - (required) is a type of set of string
  addresses = var.addresses
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tencentcloud_address_template.this.id
}

output "this" {
  value = tencentcloud_address_template.this
}
```

[top](#index)