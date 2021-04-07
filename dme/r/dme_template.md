# dme_template

[back](../dme.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    dme = ">= 0.1.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "dme_template" {
  source = "./modules/dme/r/dme_template"

  # domain_ids - (optional) is a type of list of number
  domain_ids = []
  # name - (required) is a type of string
  name = null
  # public_template - (optional) is a type of string
  public_template = null
}
```

[top](#index)

### Variables

```terraform
variable "domain_ids" {
  description = "(optional)"
  type        = list(number)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "public_template" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "dme_template" "this" {
  # domain_ids - (optional) is a type of list of number
  domain_ids = var.domain_ids
  # name - (required) is a type of string
  name = var.name
  # public_template - (optional) is a type of string
  public_template = var.public_template
}
```

[top](#index)

### Outputs

```terraform
output "domain_ids" {
  description = "returns a list of number"
  value       = dme_template.this.domain_ids
}

output "id" {
  description = "returns a string"
  value       = dme_template.this.id
}

output "public_template" {
  description = "returns a string"
  value       = dme_template.this.public_template
}

output "this" {
  value = dme_template.this
}
```

[top](#index)