# ecl_network_qos_options_v2

[back](../ecl.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ecl = ">= 2.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ecl_network_qos_options_v2" {
  source = "./modules/ecl/d/ecl_network_qos_options_v2"

  # aws_service_id - (optional) is a type of string
  aws_service_id = null
  # azure_service_id - (optional) is a type of string
  azure_service_id = null
  # bandwidth - (optional) is a type of string
  bandwidth = null
  # description - (optional) is a type of string
  description = null
  # fic_service_id - (optional) is a type of string
  fic_service_id = null
  # gcp_service_id - (optional) is a type of string
  gcp_service_id = null
  # interdc_service_id - (optional) is a type of string
  interdc_service_id = null
  # internet_service_id - (optional) is a type of string
  internet_service_id = null
  # name - (optional) is a type of string
  name = null
  # qos_option_id - (optional) is a type of string
  qos_option_id = null
  # qos_type - (optional) is a type of string
  qos_type = null
  # service_type - (optional) is a type of string
  service_type = null
  # status - (optional) is a type of string
  status = null
  # vpn_service_id - (optional) is a type of string
  vpn_service_id = null
}
```

[top](#index)

### Variables

```terraform
variable "aws_service_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "azure_service_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "bandwidth" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fic_service_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gcp_service_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "interdc_service_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "internet_service_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "qos_option_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "qos_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vpn_service_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "ecl_network_qos_options_v2" "this" {
  aws_service_id      = var.aws_service_id
  azure_service_id    = var.azure_service_id
  bandwidth           = var.bandwidth
  description         = var.description
  fic_service_id      = var.fic_service_id
  gcp_service_id      = var.gcp_service_id
  interdc_service_id  = var.interdc_service_id
  internet_service_id = var.internet_service_id
  name                = var.name
  qos_option_id       = var.qos_option_id
  qos_type            = var.qos_type
  service_type        = var.service_type
  status              = var.status
  vpn_service_id      = var.vpn_service_id
}
```

[top](#index)

### Outputs

```terraform
output "aws_service_id" {
  description = "returns a string"
  value       = data.ecl_network_qos_options_v2.this.aws_service_id
}

output "azure_service_id" {
  description = "returns a string"
  value       = data.ecl_network_qos_options_v2.this.azure_service_id
}

output "bandwidth" {
  description = "returns a string"
  value       = data.ecl_network_qos_options_v2.this.bandwidth
}

output "description" {
  description = "returns a string"
  value       = data.ecl_network_qos_options_v2.this.description
}

output "fic_service_id" {
  description = "returns a string"
  value       = data.ecl_network_qos_options_v2.this.fic_service_id
}

output "gcp_service_id" {
  description = "returns a string"
  value       = data.ecl_network_qos_options_v2.this.gcp_service_id
}

output "id" {
  description = "returns a string"
  value       = data.ecl_network_qos_options_v2.this.id
}

output "interdc_service_id" {
  description = "returns a string"
  value       = data.ecl_network_qos_options_v2.this.interdc_service_id
}

output "internet_service_id" {
  description = "returns a string"
  value       = data.ecl_network_qos_options_v2.this.internet_service_id
}

output "name" {
  description = "returns a string"
  value       = data.ecl_network_qos_options_v2.this.name
}

output "qos_option_id" {
  description = "returns a string"
  value       = data.ecl_network_qos_options_v2.this.qos_option_id
}

output "qos_type" {
  description = "returns a string"
  value       = data.ecl_network_qos_options_v2.this.qos_type
}

output "service_type" {
  description = "returns a string"
  value       = data.ecl_network_qos_options_v2.this.service_type
}

output "status" {
  description = "returns a string"
  value       = data.ecl_network_qos_options_v2.this.status
}

output "vpn_service_id" {
  description = "returns a string"
  value       = data.ecl_network_qos_options_v2.this.vpn_service_id
}

output "this" {
  value = ecl_network_qos_options_v2.this
}
```

[top](#index)