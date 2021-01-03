# sumologic_caller_identity

[back](../sumologic.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    sumologic = ">= 2.6.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "sumologic_caller_identity" {
  source = "./modules/sumologic/d/sumologic_caller_identity"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "sumologic_caller_identity" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "access_id" {
  description = "returns a string"
  value       = data.sumologic_caller_identity.this.access_id
}

output "environment" {
  description = "returns a string"
  value       = data.sumologic_caller_identity.this.environment
}

output "id" {
  description = "returns a string"
  value       = data.sumologic_caller_identity.this.id
}

output "this" {
  value = sumologic_caller_identity.this
}
```

[top](#index)