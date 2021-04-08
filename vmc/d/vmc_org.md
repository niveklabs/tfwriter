# vmc_org

[back](../vmc.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vmc = ">= 1.5.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vmc_org" {
  source = "./modules/vmc/d/vmc_org"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "vmc_org" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "display_name" {
  description = "returns a string"
  value       = data.vmc_org.this.display_name
}

output "id" {
  description = "returns a string"
  value       = data.vmc_org.this.id
}

output "name" {
  description = "returns a string"
  value       = data.vmc_org.this.name
}

output "this" {
  value = vmc_org.this
}
```

[top](#index)