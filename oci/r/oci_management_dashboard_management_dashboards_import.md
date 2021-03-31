# oci_management_dashboard_management_dashboards_import

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_management_dashboard_management_dashboards_import" {
  source = "./modules/oci/r/oci_management_dashboard_management_dashboards_import"

  # import_details - (optional) is a type of string
  import_details = null
  # import_details_file - (optional) is a type of string
  import_details_file = null

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "import_details" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "import_details_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "oci_management_dashboard_management_dashboards_import" "this" {
  import_details      = var.import_details
  import_details_file = var.import_details_file

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = oci_management_dashboard_management_dashboards_import.this.id
}

output "this" {
  value = oci_management_dashboard_management_dashboards_import.this
}
```

[top](#index)