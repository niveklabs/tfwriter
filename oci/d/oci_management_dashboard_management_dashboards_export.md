# oci_management_dashboard_management_dashboards_export

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_management_dashboard_management_dashboards_export" {
  source = "./modules/oci/d/oci_management_dashboard_management_dashboards_export"

  # export_dashboard_id - (required) is a type of string
  export_dashboard_id = null
}
```

[top](#index)

### Variables

```terraform
variable "export_dashboard_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_management_dashboard_management_dashboards_export" "this" {
  # export_dashboard_id - (required) is a type of string
  export_dashboard_id = var.export_dashboard_id
}
```

[top](#index)

### Outputs

```terraform
output "export_details" {
  description = "returns a string"
  value       = data.oci_management_dashboard_management_dashboards_export.this.export_details
}

output "id" {
  description = "returns a string"
  value       = data.oci_management_dashboard_management_dashboards_export.this.id
}

output "this" {
  value = oci_management_dashboard_management_dashboards_export.this
}
```

[top](#index)