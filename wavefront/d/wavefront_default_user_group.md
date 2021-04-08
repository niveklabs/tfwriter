# wavefront_default_user_group

[back](../wavefront.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    wavefront = ">= 2.8.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "wavefront_default_user_group" {
  source = "./modules/wavefront/d/wavefront_default_user_group"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "wavefront_default_user_group" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "group_id" {
  description = "returns a string"
  value       = data.wavefront_default_user_group.this.group_id
}

output "id" {
  description = "returns a string"
  value       = data.wavefront_default_user_group.this.id
}

output "this" {
  value = wavefront_default_user_group.this
}
```

[top](#index)