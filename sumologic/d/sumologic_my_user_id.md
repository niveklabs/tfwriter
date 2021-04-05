# sumologic_my_user_id

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
    sumologic = ">= 2.9.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "sumologic_my_user_id" {
  source = "./modules/sumologic/d/sumologic_my_user_id"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "sumologic_my_user_id" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.sumologic_my_user_id.this.id
}

output "this" {
  value = sumologic_my_user_id.this
}
```

[top](#index)