# azuredevops_client_config

[back](../azuredevops.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    azuredevops = ">= 0.1.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azuredevops_client_config" {
  source = "./modules/azuredevops/d/azuredevops_client_config"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "azuredevops_client_config" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.azuredevops_client_config.this.id
}

output "organization_url" {
  description = "returns a string"
  value       = data.azuredevops_client_config.this.organization_url
}

output "this" {
  value = azuredevops_client_config.this
}
```

[top](#index)