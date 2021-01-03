# nutanix_clusters

[back](../nutanix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    nutanix = ">= 1.1.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nutanix_clusters" {
  source = "./modules/nutanix/d/nutanix_clusters"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "nutanix_clusters" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "api_version" {
  description = "returns a string"
  value       = data.nutanix_clusters.this.api_version
}

output "entities" {
  description = "returns a list of object"
  value       = data.nutanix_clusters.this.entities
}

output "id" {
  description = "returns a string"
  value       = data.nutanix_clusters.this.id
}

output "this" {
  value = nutanix_clusters.this
}
```

[top](#index)