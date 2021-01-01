# google_monitoring_uptime_check_ips

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    google = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "google_monitoring_uptime_check_ips" {
  source = "./modules/google/d/google_monitoring_uptime_check_ips"

}
```

[top](#index)

### Variables

```hcl
```

[top](#index)

### Datasource

```hcl
data "google_monitoring_uptime_check_ips" "this" {
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = data.google_monitoring_uptime_check_ips.this.id
}

output "uptime_check_ips" {
  description = "returns a list of object"
  value       = data.google_monitoring_uptime_check_ips.this.uptime_check_ips
}

output "this" {
  value = google_monitoring_uptime_check_ips.this
}
```

[top](#index)