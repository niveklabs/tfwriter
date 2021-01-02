# kubernetes_all_namespaces

[back](../kubernetes.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    kubernetes = ">= 1.13.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "kubernetes_all_namespaces" {
  source = "./modules/kubernetes/d/kubernetes_all_namespaces"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "kubernetes_all_namespaces" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.kubernetes_all_namespaces.this.id
}

output "namespaces" {
  description = "returns a list of string"
  value       = data.kubernetes_all_namespaces.this.namespaces
}

output "this" {
  value = kubernetes_all_namespaces.this
}
```

[top](#index)