# google_monitoring_uptime_check_ips

[back](../google-beta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    google-beta = ">= 3.63.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_monitoring_uptime_check_ips" {
  source = "./modules/google-beta/d/google_monitoring_uptime_check_ips"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "google_monitoring_uptime_check_ips" "this" {
}
```

[top](#index)

### Outputs

```terraform
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