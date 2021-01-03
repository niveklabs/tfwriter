# okta_default_policies

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
    okta = ">= 3.7.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "okta_default_policies" {
  source = "./modules/okta/d/okta_default_policies"

  # type - (required) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "type" {
  description = "(required) - Policy type: OKTA_SIGN_ON, PASSWORD, MFA_ENROLL, OAUTH_AUTHORIZATION_POLICY, or IDP_DISCOVERY"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "okta_default_policies" "this" {
  type = var.type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.okta_default_policies.this.id
}

output "this" {
  value = okta_default_policies.this
}
```

[top](#index)