# akamai_appsec_security_policy_rename

[back](../akamai.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    akamai = ">= 1.5.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "akamai_appsec_security_policy_rename" {
  source = "./modules/akamai/r/akamai_appsec_security_policy_rename"

  # config_id - (required) is a type of number
  config_id = null
  # security_policy_id - (required) is a type of string
  security_policy_id = null
  # security_policy_name - (required) is a type of string
  security_policy_name = null
  # version - (required) is a type of number
  version = null
}
```

[top](#index)

### Variables

```terraform
variable "config_id" {
  description = "(required)"
  type        = number
}

variable "security_policy_id" {
  description = "(required)"
  type        = string
}

variable "security_policy_name" {
  description = "(required)"
  type        = string
}

variable "version" {
  description = "(required)"
  type        = number
}
```

[top](#index)

### Resource

```terraform
resource "akamai_appsec_security_policy_rename" "this" {
  config_id            = var.config_id
  security_policy_id   = var.security_policy_id
  security_policy_name = var.security_policy_name
  version              = var.version
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = akamai_appsec_security_policy_rename.this.id
}

output "this" {
  value = akamai_appsec_security_policy_rename.this
}
```

[top](#index)