# lacework_api_token

[back](../lacework.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    lacework = ">= 0.2.7"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "lacework_api_token" {
  source = "./modules/lacework/d/lacework_api_token"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "lacework_api_token" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.lacework_api_token.this.id
}

output "token" {
  description = "returns a string"
  value       = data.lacework_api_token.this.token
  sensitive   = true
}

output "this" {
  value = lacework_api_token.this
}
```

[top](#index)