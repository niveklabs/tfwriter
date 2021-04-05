# rancher2_cloud_credential

[back](../rancher2.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    rancher2 = ">= 1.13.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "rancher2_cloud_credential" {
  source = "./modules/rancher2/d/rancher2_cloud_credential"

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
data "rancher2_cloud_credential" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "annotations" {
  description = "returns a map of string"
  value       = data.rancher2_cloud_credential.this.annotations
}

output "id" {
  description = "returns a string"
  value       = data.rancher2_cloud_credential.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = data.rancher2_cloud_credential.this.labels
}

output "this" {
  value = rancher2_cloud_credential.this
}
```

[top](#index)