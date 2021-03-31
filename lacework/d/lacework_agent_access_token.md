# lacework_agent_access_token

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
    lacework = ">= 0.3.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "lacework_agent_access_token" {
  source = "./modules/lacework/d/lacework_agent_access_token"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "lacework_agent_access_token" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.lacework_agent_access_token.this.id
}

output "token" {
  description = "returns a string"
  value       = data.lacework_agent_access_token.this.token
  sensitive   = true
}

output "this" {
  value = lacework_agent_access_token.this
}
```

[top](#index)