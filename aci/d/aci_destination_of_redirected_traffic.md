# aci_destination_of_redirected_traffic

[back](../aci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aci = ">= 0.5.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aci_destination_of_redirected_traffic" {
  source = "./modules/aci/d/aci_destination_of_redirected_traffic"

  # annotation - (optional) is a type of string
  annotation = null
  # description - (optional) is a type of string
  description = null
  # dest_name - (optional) is a type of string
  dest_name = null
  # ip - (required) is a type of string
  ip = null
  # ip2 - (optional) is a type of string
  ip2 = null
  # mac - (optional) is a type of string
  mac = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # pod_id - (optional) is a type of string
  pod_id = null
  # service_redirect_policy_dn - (required) is a type of string
  service_redirect_policy_dn = null
}
```

[top](#index)

### Variables

```terraform
variable "annotation" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dest_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip" {
  description = "(required)"
  type        = string
}

variable "ip2" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mac" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name_alias" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pod_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_redirect_policy_dn" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "aci_destination_of_redirected_traffic" "this" {
  annotation                 = var.annotation
  description                = var.description
  dest_name                  = var.dest_name
  ip                         = var.ip
  ip2                        = var.ip2
  mac                        = var.mac
  name_alias                 = var.name_alias
  pod_id                     = var.pod_id
  service_redirect_policy_dn = var.service_redirect_policy_dn
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.aci_destination_of_redirected_traffic.this.description
}

output "dest_name" {
  description = "returns a string"
  value       = data.aci_destination_of_redirected_traffic.this.dest_name
}

output "id" {
  description = "returns a string"
  value       = data.aci_destination_of_redirected_traffic.this.id
}

output "ip2" {
  description = "returns a string"
  value       = data.aci_destination_of_redirected_traffic.this.ip2
}

output "mac" {
  description = "returns a string"
  value       = data.aci_destination_of_redirected_traffic.this.mac
}

output "name_alias" {
  description = "returns a string"
  value       = data.aci_destination_of_redirected_traffic.this.name_alias
}

output "pod_id" {
  description = "returns a string"
  value       = data.aci_destination_of_redirected_traffic.this.pod_id
}

output "this" {
  value = aci_destination_of_redirected_traffic.this
}
```

[top](#index)