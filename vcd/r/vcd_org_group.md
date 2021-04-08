# vcd_org_group

[back](../vcd.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vcd = ">= 3.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vcd_org_group" {
  source = "./modules/vcd/r/vcd_org_group"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # org - (optional) is a type of string
  org = null
  # provider_type - (required) is a type of string
  provider_type = null
  # role - (required) is a type of string
  role = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Description"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Group name"
  type        = string
}

variable "org" {
  description = "(optional) - The name of organization to use, optional if defined at provider level. Useful when connected as sysadmin working across different organizations"
  type        = string
  default     = null
}

variable "provider_type" {
  description = "(required) - Identity provider type - 'SAML' or 'INTEGRATED' for LDAP"
  type        = string
}

variable "role" {
  description = "(required) - Existing role name to assign"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "vcd_org_group" "this" {
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # org - (optional) is a type of string
  org = var.org
  # provider_type - (required) is a type of string
  provider_type = var.provider_type
  # role - (required) is a type of string
  role = var.role
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vcd_org_group.this.id
}

output "this" {
  value = vcd_org_group.this
}
```

[top](#index)