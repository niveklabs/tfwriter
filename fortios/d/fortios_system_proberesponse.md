# fortios_system_proberesponse

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
module "fortios_system_proberesponse" {
  source = "./modules/fortios/d/fortios_system_proberesponse"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "fortios_system_proberesponse" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "http_probe_value" {
  description = "returns a string"
  value       = data.fortios_system_proberesponse.this.http_probe_value
}

output "id" {
  description = "returns a string"
  value       = data.fortios_system_proberesponse.this.id
}

output "mode" {
  description = "returns a string"
  value       = data.fortios_system_proberesponse.this.mode
}

output "password" {
  description = "returns a string"
  value       = data.fortios_system_proberesponse.this.password
  sensitive   = true
}

output "port" {
  description = "returns a number"
  value       = data.fortios_system_proberesponse.this.port
}

output "security_mode" {
  description = "returns a string"
  value       = data.fortios_system_proberesponse.this.security_mode
}

output "timeout" {
  description = "returns a number"
  value       = data.fortios_system_proberesponse.this.timeout
}

output "ttl_mode" {
  description = "returns a string"
  value       = data.fortios_system_proberesponse.this.ttl_mode
}

output "this" {
  value = fortios_system_proberesponse.this
}
```

[top](#index)