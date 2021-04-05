# ovh_vracks

[back](../ovh.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ovh = ">= 0.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ovh_vracks" {
  source = "./modules/ovh/d/ovh_vracks"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "ovh_vracks" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.ovh_vracks.this.id
}

output "result" {
  description = "returns a list of string"
  value       = data.ovh_vracks.this.result
}

output "this" {
  value = ovh_vracks.this
}
```

[top](#index)