# fortios_systemlldp_networkpolicy

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
module "fortios_systemlldp_networkpolicy" {
  source = "./modules/fortios/d/fortios_systemlldp_networkpolicy"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "fortios_systemlldp_networkpolicy" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "comment" {
  description = "returns a string"
  value       = data.fortios_systemlldp_networkpolicy.this.comment
}

output "guest" {
  description = "returns a list of object"
  value       = data.fortios_systemlldp_networkpolicy.this.guest
}

output "guest_voice_signaling" {
  description = "returns a list of object"
  value       = data.fortios_systemlldp_networkpolicy.this.guest_voice_signaling
}

output "id" {
  description = "returns a string"
  value       = data.fortios_systemlldp_networkpolicy.this.id
}

output "softphone" {
  description = "returns a list of object"
  value       = data.fortios_systemlldp_networkpolicy.this.softphone
}

output "streaming_video" {
  description = "returns a list of object"
  value       = data.fortios_systemlldp_networkpolicy.this.streaming_video
}

output "video_conferencing" {
  description = "returns a list of object"
  value       = data.fortios_systemlldp_networkpolicy.this.video_conferencing
}

output "video_signaling" {
  description = "returns a list of object"
  value       = data.fortios_systemlldp_networkpolicy.this.video_signaling
}

output "voice" {
  description = "returns a list of object"
  value       = data.fortios_systemlldp_networkpolicy.this.voice
}

output "voice_signaling" {
  description = "returns a list of object"
  value       = data.fortios_systemlldp_networkpolicy.this.voice_signaling
}

output "this" {
  value = fortios_systemlldp_networkpolicy.this
}
```

[top](#index)