# opc_compute_security_protocol

[back](../opc.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    opc = ">= 1.4.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "opc_compute_security_protocol" {
  source = "./modules/opc/r/opc_compute_security_protocol"

  # description - (optional) is a type of string
  description = null
  # dst_ports - (optional) is a type of list of string
  dst_ports = []
  # ip_protocol - (optional) is a type of string
  ip_protocol = null
  # name - (required) is a type of string
  name = null
  # src_ports - (optional) is a type of list of string
  src_ports = []
  # tags - (optional) is a type of list of string
  tags = []
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dst_ports" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "ip_protocol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "src_ports" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = list(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "opc_compute_security_protocol" "this" {
  # description - (optional) is a type of string
  description = var.description
  # dst_ports - (optional) is a type of list of string
  dst_ports = var.dst_ports
  # ip_protocol - (optional) is a type of string
  ip_protocol = var.ip_protocol
  # name - (required) is a type of string
  name = var.name
  # src_ports - (optional) is a type of list of string
  src_ports = var.src_ports
  # tags - (optional) is a type of list of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = opc_compute_security_protocol.this.id
}

output "uri" {
  description = "returns a string"
  value       = opc_compute_security_protocol.this.uri
}

output "this" {
  value = opc_compute_security_protocol.this
}
```

[top](#index)