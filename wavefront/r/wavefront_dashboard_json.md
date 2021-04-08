# wavefront_dashboard_json

[back](../wavefront.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    wavefront = ">= 2.8.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "wavefront_dashboard_json" {
  source = "./modules/wavefront/r/wavefront_dashboard_json"

  # dashboard_json - (required) is a type of string
  dashboard_json = null
}
```

[top](#index)

### Variables

```terraform
variable "dashboard_json" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "wavefront_dashboard_json" "this" {
  # dashboard_json - (required) is a type of string
  dashboard_json = var.dashboard_json
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = wavefront_dashboard_json.this.id
}

output "this" {
  value = wavefront_dashboard_json.this
}
```

[top](#index)