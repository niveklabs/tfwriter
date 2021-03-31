# datadog_synthetics_locations

[back](../datadog.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    datadog = ">= 2.24.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "datadog_synthetics_locations" {
  source = "./modules/datadog/d/datadog_synthetics_locations"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "datadog_synthetics_locations" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.datadog_synthetics_locations.this.id
}

output "locations" {
  description = "returns a map of string"
  value       = data.datadog_synthetics_locations.this.locations
}

output "this" {
  value = datadog_synthetics_locations.this
}
```

[top](#index)