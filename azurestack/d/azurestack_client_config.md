# azurestack_client_config

[back](../azurestack.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    azurestack = ">= 0.9.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurestack_client_config" {
  source = "./modules/azurestack/d/azurestack_client_config"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "azurestack_client_config" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "client_id" {
  description = "returns a string"
  value       = data.azurestack_client_config.this.client_id
}

output "id" {
  description = "returns a string"
  value       = data.azurestack_client_config.this.id
}

output "service_principal_application_id" {
  description = "returns a string"
  value       = data.azurestack_client_config.this.service_principal_application_id
}

output "service_principal_object_id" {
  description = "returns a string"
  value       = data.azurestack_client_config.this.service_principal_object_id
}

output "subscription_id" {
  description = "returns a string"
  value       = data.azurestack_client_config.this.subscription_id
}

output "tenant_id" {
  description = "returns a string"
  value       = data.azurestack_client_config.this.tenant_id
}

output "this" {
  value = azurestack_client_config.this
}
```

[top](#index)