# vault_policy_document

[back](../vault.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vault = ">= 2.17.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vault_policy_document" {
  source = "./modules/vault/d/vault_policy_document"


  rule = [{
    allowed_parameter = [{
      key   = null
      value = []
    }]
    capabilities = []
    denied_parameter = [{
      key   = null
      value = []
    }]
    description         = null
    max_wrapping_ttl    = null
    min_wrapping_ttl    = null
    path                = null
    required_parameters = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "rule" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      allowed_parameter = list(object(
        {
          key   = string
          value = list(string)
        }
      ))
      capabilities = list(string)
      denied_parameter = list(object(
        {
          key   = string
          value = list(string)
        }
      ))
      description         = string
      max_wrapping_ttl    = string
      min_wrapping_ttl    = string
      path                = string
      required_parameters = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "vault_policy_document" "this" {

  dynamic "rule" {
    for_each = var.rule
    content {
      capabilities        = rule.value["capabilities"]
      description         = rule.value["description"]
      max_wrapping_ttl    = rule.value["max_wrapping_ttl"]
      min_wrapping_ttl    = rule.value["min_wrapping_ttl"]
      path                = rule.value["path"]
      required_parameters = rule.value["required_parameters"]

      dynamic "allowed_parameter" {
        for_each = rule.value.allowed_parameter
        content {
          key   = allowed_parameter.value["key"]
          value = allowed_parameter.value["value"]
        }
      }

      dynamic "denied_parameter" {
        for_each = rule.value.denied_parameter
        content {
          key   = denied_parameter.value["key"]
          value = denied_parameter.value["value"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "hcl" {
  description = "returns a string"
  value       = data.vault_policy_document.this.hcl
}

output "id" {
  description = "returns a string"
  value       = data.vault_policy_document.this.id
}

output "this" {
  value = vault_policy_document.this
}
```

[top](#index)