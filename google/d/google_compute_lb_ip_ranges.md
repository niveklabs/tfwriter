# google_compute_lb_ip_ranges

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
module "google_compute_lb_ip_ranges" {
  source = "./modules/google/d/google_compute_lb_ip_ranges"

}
```

[top](#index)

### Variables

```hcl
```

[top](#index)

### Datasource

```hcl
data "google_compute_lb_ip_ranges" "this" {
}
```

[top](#index)

### Outputs

```hcl
output "http_ssl_tcp_internal" {
  description = "returns a list of string"
  value       = data.google_compute_lb_ip_ranges.this.http_ssl_tcp_internal
}

output "id" {
  description = "returns a string"
  value       = data.google_compute_lb_ip_ranges.this.id
}

output "network" {
  description = "returns a list of string"
  value       = data.google_compute_lb_ip_ranges.this.network
}

output "this" {
  value = google_compute_lb_ip_ranges.this
}
```

[top](#index)