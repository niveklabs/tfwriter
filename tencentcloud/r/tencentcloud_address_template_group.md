# tencentcloud_address_template_group

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
module "tencentcloud_address_template_group" {
  source = "./modules/tencentcloud/r/tencentcloud_address_template_group"

  # name - (required) is a type of string
  name = null
  # template_ids - (required) is a type of set of string
  template_ids = []
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - Name of the address template group."
  type        = string
}

variable "template_ids" {
  description = "(required) - Template ID list."
  type        = set(string)
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_address_template_group" "this" {
  name         = var.name
  template_ids = var.template_ids
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tencentcloud_address_template_group.this.id
}

output "this" {
  value = tencentcloud_address_template_group.this
}
```

[top](#index)