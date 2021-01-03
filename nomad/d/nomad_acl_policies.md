# nomad_acl_policies

[back](../nomad.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    nomad = ">= 1.4.11"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nomad_acl_policies" {
  source = "./modules/nomad/d/nomad_acl_policies"

  # prefix - (optional) is a type of string
  prefix = null
}
```

[top](#index)

### Variables

```terraform
variable "prefix" {
  description = "(optional) - ACL Policy Name Prefix"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "nomad_acl_policies" "this" {
  prefix = var.prefix
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.nomad_acl_policies.this.id
}

output "policies" {
  description = "returns a list of object"
  value       = data.nomad_acl_policies.this.policies
}

output "this" {
  value = nomad_acl_policies.this
}
```

[top](#index)