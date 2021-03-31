# fortios_systemautoupdate_pushupdate

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_systemautoupdate_pushupdate" {
  source = "./modules/fortios/d/fortios_systemautoupdate_pushupdate"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "fortios_systemautoupdate_pushupdate" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "address" {
  description = "returns a string"
  value       = data.fortios_systemautoupdate_pushupdate.this.address
}

output "id" {
  description = "returns a string"
  value       = data.fortios_systemautoupdate_pushupdate.this.id
}

output "override" {
  description = "returns a string"
  value       = data.fortios_systemautoupdate_pushupdate.this.override
}

output "port" {
  description = "returns a number"
  value       = data.fortios_systemautoupdate_pushupdate.this.port
}

output "status" {
  description = "returns a string"
  value       = data.fortios_systemautoupdate_pushupdate.this.status
}

output "this" {
  value = fortios_systemautoupdate_pushupdate.this
}
```

[top](#index)