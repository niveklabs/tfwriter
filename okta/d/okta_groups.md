# okta_groups

[back](../okta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    okta = ">= 3.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "okta_groups" {
  source = "./modules/okta/d/okta_groups"

  # q - (optional) is a type of string
  q = null
  # search - (optional) is a type of string
  search = null
  # type - (optional) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "q" {
  description = "(optional) - Searches the name property of groups for matching value"
  type        = string
  default     = null
}

variable "search" {
  description = "(optional) - Searches for groups with a supported filtering expression for all attributes except for '_embedded', '_links', and 'objectClass'"
  type        = string
  default     = null
}

variable "type" {
  description = "(optional) - Type of the group. When specified in the terraform resource, will act as a filter when searching for the groups"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "okta_groups" "this" {
  # q - (optional) is a type of string
  q = var.q
  # search - (optional) is a type of string
  search = var.search
  # type - (optional) is a type of string
  type = var.type
}
```

[top](#index)

### Outputs

```terraform
output "groups" {
  description = "returns a list of object"
  value       = data.okta_groups.this.groups
}

output "id" {
  description = "returns a string"
  value       = data.okta_groups.this.id
}

output "this" {
  value = okta_groups.this
}
```

[top](#index)