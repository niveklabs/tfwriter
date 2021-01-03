# nsxt_management_cluster

[back](../nsxt.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    nsxt = ">= 3.1.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nsxt_management_cluster" {
  source = "./modules/nsxt/d/nsxt_management_cluster"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "nsxt_management_cluster" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.nsxt_management_cluster.this.id
}

output "node_sha256_thumbprint" {
  description = "returns a string"
  value       = data.nsxt_management_cluster.this.node_sha256_thumbprint
}

output "this" {
  value = nsxt_management_cluster.this
}
```

[top](#index)