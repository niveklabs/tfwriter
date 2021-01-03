# dome9_cloudaccount_kubernetes

[back](../dome9.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    dome9 = ">= 1.20.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "dome9_cloudaccount_kubernetes" {
  source = "./modules/dome9/d/dome9_cloudaccount_kubernetes"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "dome9_cloudaccount_kubernetes" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "cluster_version" {
  description = "returns a string"
  value       = data.dome9_cloudaccount_kubernetes.this.cluster_version
}

output "creation_date" {
  description = "returns a string"
  value       = data.dome9_cloudaccount_kubernetes.this.creation_date
}

output "id" {
  description = "returns a string"
  value       = data.dome9_cloudaccount_kubernetes.this.id
}

output "name" {
  description = "returns a string"
  value       = data.dome9_cloudaccount_kubernetes.this.name
}

output "organizational_unit_id" {
  description = "returns a string"
  value       = data.dome9_cloudaccount_kubernetes.this.organizational_unit_id
}

output "organizational_unit_name" {
  description = "returns a string"
  value       = data.dome9_cloudaccount_kubernetes.this.organizational_unit_name
}

output "organizational_unit_path" {
  description = "returns a string"
  value       = data.dome9_cloudaccount_kubernetes.this.organizational_unit_path
}

output "vendor" {
  description = "returns a string"
  value       = data.dome9_cloudaccount_kubernetes.this.vendor
}

output "this" {
  value = dome9_cloudaccount_kubernetes.this
}
```

[top](#index)