# azurerm_billing_mca_account_scope

[back](../azurerm.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    azurerm = ">= 2.54.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_billing_mca_account_scope" {
  source = "./modules/azurerm/d/azurerm_billing_mca_account_scope"

  # billing_account_name - (required) is a type of string
  billing_account_name = null
  # billing_profile_name - (required) is a type of string
  billing_profile_name = null
  # invoice_section_name - (required) is a type of string
  invoice_section_name = null

  timeouts = [{
    read = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "billing_account_name" {
  description = "(required)"
  type        = string
}

variable "billing_profile_name" {
  description = "(required)"
  type        = string
}

variable "invoice_section_name" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      read = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "azurerm_billing_mca_account_scope" "this" {
  billing_account_name = var.billing_account_name
  billing_profile_name = var.billing_profile_name
  invoice_section_name = var.invoice_section_name

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      read = timeouts.value["read"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.azurerm_billing_mca_account_scope.this.id
}

output "this" {
  value = azurerm_billing_mca_account_scope.this
}
```

[top](#index)