# tfe_ip_ranges

[back](../tfe.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    tfe = ">= 0.24.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "tfe_ip_ranges" {
  source = "./modules/tfe/d/tfe_ip_ranges"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "tfe_ip_ranges" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "api" {
  description = "returns a list of string"
  value       = data.tfe_ip_ranges.this.api
}

output "id" {
  description = "returns a string"
  value       = data.tfe_ip_ranges.this.id
}

output "notifications" {
  description = "returns a list of string"
  value       = data.tfe_ip_ranges.this.notifications
}

output "sentinel" {
  description = "returns a list of string"
  value       = data.tfe_ip_ranges.this.sentinel
}

output "vcs" {
  description = "returns a list of string"
  value       = data.tfe_ip_ranges.this.vcs
}

output "this" {
  value = tfe_ip_ranges.this
}
```

[top](#index)