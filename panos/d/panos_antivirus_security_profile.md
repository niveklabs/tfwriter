# panos_antivirus_security_profile

[back](../panos.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    panos = ">= 1.8.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_antivirus_security_profile" {
  source = "./modules/panos/d/panos_antivirus_security_profile"

  # device_group - (optional) is a type of string
  device_group = null
  # name - (required) is a type of string
  name = null
  # vsys - (optional) is a type of string
  vsys = null
}
```

[top](#index)

### Variables

```terraform
variable "device_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Security profile name"
  type        = string
}

variable "vsys" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "panos_antivirus_security_profile" "this" {
  # device_group - (optional) is a type of string
  device_group = var.device_group
  # name - (required) is a type of string
  name = var.name
  # vsys - (optional) is a type of string
  vsys = var.vsys
}
```

[top](#index)

### Outputs

```terraform
output "application_exception" {
  description = "returns a list of object"
  value       = data.panos_antivirus_security_profile.this.application_exception
}

output "decoder" {
  description = "returns a list of object"
  value       = data.panos_antivirus_security_profile.this.decoder
}

output "description" {
  description = "returns a string"
  value       = data.panos_antivirus_security_profile.this.description
}

output "id" {
  description = "returns a string"
  value       = data.panos_antivirus_security_profile.this.id
}

output "machine_learning_exception" {
  description = "returns a list of object"
  value       = data.panos_antivirus_security_profile.this.machine_learning_exception
}

output "machine_learning_model" {
  description = "returns a list of object"
  value       = data.panos_antivirus_security_profile.this.machine_learning_model
}

output "packet_capture" {
  description = "returns a bool"
  value       = data.panos_antivirus_security_profile.this.packet_capture
}

output "threat_exceptions" {
  description = "returns a list of string"
  value       = data.panos_antivirus_security_profile.this.threat_exceptions
}

output "this" {
  value = panos_antivirus_security_profile.this
}
```

[top](#index)