# nutanix_karbon_clusters

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
    nutanix = ">= 1.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nutanix_karbon_clusters" {
  source = "./modules/nutanix/d/nutanix_karbon_clusters"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "nutanix_karbon_clusters" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "clusters" {
  description = "returns a list of object"
  value       = data.nutanix_karbon_clusters.this.clusters
}

output "id" {
  description = "returns a string"
  value       = data.nutanix_karbon_clusters.this.id
}

output "this" {
  value = nutanix_karbon_clusters.this
}
```

[top](#index)