# google_compute_lb_ip_ranges

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
module "google_compute_lb_ip_ranges" {
  source = "./modules/google-beta/d/google_compute_lb_ip_ranges"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "google_compute_lb_ip_ranges" "this" {
}
```

[top](#index)

### Outputs

```terraform
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