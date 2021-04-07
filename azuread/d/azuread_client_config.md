# azuread_client_config

[back](../azuread.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    azuread = ">= 1.4.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azuread_client_config" {
  source = "./modules/azuread/d/azuread_client_config"


  timeouts = [{
    read = null
  }]
}
```

[top](#index)

### Variables

```terraform
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
data "azuread_client_config" "this" {

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # read - (optional) is a type of string
      read = timeouts.value["read"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "client_id" {
  description = "returns a string"
  value       = data.azuread_client_config.this.client_id
}

output "id" {
  description = "returns a string"
  value       = data.azuread_client_config.this.id
}

output "object_id" {
  description = "returns a string"
  value       = data.azuread_client_config.this.object_id
}

output "tenant_id" {
  description = "returns a string"
  value       = data.azuread_client_config.this.tenant_id
}

output "this" {
  value = azuread_client_config.this
}
```

[top](#index)