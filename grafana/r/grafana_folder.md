# grafana_folder

[back](../grafana.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    grafana = ">= 1.9.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "grafana_folder" {
  source = "./modules/grafana/r/grafana_folder"

  # title - (required) is a type of string
  title = null
}
```

[top](#index)

### Variables

```terraform
variable "title" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "grafana_folder" "this" {
  title = var.title
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = grafana_folder.this.id
}

output "uid" {
  description = "returns a string"
  value       = grafana_folder.this.uid
}

output "this" {
  value = grafana_folder.this
}
```

[top](#index)