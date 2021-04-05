# nutanix_projects

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
module "nutanix_projects" {
  source = "./modules/nutanix/d/nutanix_projects"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "nutanix_projects" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "api_version" {
  description = "returns a string"
  value       = data.nutanix_projects.this.api_version
}

output "entities" {
  description = "returns a list of object"
  value       = data.nutanix_projects.this.entities
}

output "id" {
  description = "returns a string"
  value       = data.nutanix_projects.this.id
}

output "this" {
  value = nutanix_projects.this
}
```

[top](#index)