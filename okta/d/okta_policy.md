# okta_policy

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
module "okta_policy" {
  source = "./modules/okta/d/okta_policy"

  # name - (required) is a type of string
  name = null
  # type - (required) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - Name of policy"
  type        = string
}

variable "type" {
  description = "(required) - Policy type: OKTA_SIGN_ON, PASSWORD, MFA_ENROLL, or IDP_DISCOVERY"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "okta_policy" "this" {
  # name - (required) is a type of string
  name = var.name
  # type - (required) is a type of string
  type = var.type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.okta_policy.this.id
}

output "this" {
  value = okta_policy.this
}
```

[top](#index)