# okta_policy_signon

[back](../okta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "okta_policy_signon" {
  source = "./modules/okta/r/okta_policy_signon"

  # description - (optional) is a type of string
  description = null
  # groups_included - (optional) is a type of set of string
  groups_included = []
  # name - (required) is a type of string
  name = null
  # priority - (optional) is a type of number
  priority = null
  # status - (optional) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Policy Description"
  type        = string
  default     = null
}

variable "groups_included" {
  description = "(optional) - List of Group IDs to Include"
  type        = set(string)
  default     = null
}

variable "name" {
  description = "(required) - Policy Name"
  type        = string
}

variable "priority" {
  description = "(optional) - Policy Priority, this attribute can be set to a valid priority. To avoid endless diff situation we error if an invalid priority is provided. API defaults it to the last (lowest) if not there."
  type        = number
  default     = null
}

variable "status" {
  description = "(optional) - Policy Status: ACTIVE or INACTIVE."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "okta_policy_signon" "this" {
  description     = var.description
  groups_included = var.groups_included
  name            = var.name
  priority        = var.priority
  status          = var.status
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = okta_policy_signon.this.id
}

output "this" {
  value = okta_policy_signon.this
}
```

[top](#index)