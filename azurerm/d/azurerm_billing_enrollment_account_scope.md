# azurerm_billing_enrollment_account_scope

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
module "azurerm_billing_enrollment_account_scope" {
  source = "./modules/azurerm/d/azurerm_billing_enrollment_account_scope"

  # billing_account_name - (required) is a type of string
  billing_account_name = null
  # enrollment_account_name - (required) is a type of string
  enrollment_account_name = null

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

variable "enrollment_account_name" {
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
data "azurerm_billing_enrollment_account_scope" "this" {
  billing_account_name    = var.billing_account_name
  enrollment_account_name = var.enrollment_account_name

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
  value       = data.azurerm_billing_enrollment_account_scope.this.id
}

output "this" {
  value = azurerm_billing_enrollment_account_scope.this
}
```

[top](#index)