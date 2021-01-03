# aviatrix_firenet_vendor_integration

[back](../aviatrix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aviatrix = ">= 2.17.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aviatrix_firenet_vendor_integration" {
  source = "./modules/aviatrix/d/aviatrix_firenet_vendor_integration"

  # firewall_name - (optional) is a type of string
  firewall_name = null
  # instance_id - (required) is a type of string
  instance_id = null
  # number_of_retries - (optional) is a type of number
  number_of_retries = null
  # password - (required) is a type of string
  password = null
  # public_ip - (required) is a type of string
  public_ip = null
  # retry_interval - (optional) is a type of number
  retry_interval = null
  # route_table - (optional) is a type of string
  route_table = null
  # save - (optional) is a type of bool
  save = null
  # synchronize - (optional) is a type of bool
  synchronize = null
  # username - (required) is a type of string
  username = null
  # vendor_type - (required) is a type of string
  vendor_type = null
  # vpc_id - (required) is a type of string
  vpc_id = null
}
```

[top](#index)

### Variables

```terraform
variable "firewall_name" {
  description = "(optional) - Name of firewall instance."
  type        = string
  default     = null
}

variable "instance_id" {
  description = "(required) - ID of Firewall instance."
  type        = string
}

variable "number_of_retries" {
  description = "(optional) - Number of retries for 'save' or 'synchronize'."
  type        = number
  default     = null
}

variable "password" {
  description = "(required) - Firewall login password for API calls."
  type        = string
}

variable "public_ip" {
  description = "(required) - The public IP address of the firewall management interface for API calls from the Aviatrix Controller."
  type        = string
}

variable "retry_interval" {
  description = "(optional) - Retry interval in seconds for `save` or `synchronize`."
  type        = number
  default     = null
}

variable "route_table" {
  description = "(optional) - Specify the firewall virtual Router name you wish the Controller to program. If left unspecified, the Controller programs the firewall’s default router."
  type        = string
  default     = null
}

variable "save" {
  description = "(optional) - Switch to save or not."
  type        = bool
  default     = null
}

variable "synchronize" {
  description = "(optional) - Switch to sync or not."
  type        = bool
  default     = null
}

variable "username" {
  description = "(required) - Firewall login name for API calls from the Controller. For example, admin-api, as shown in the screen shot."
  type        = string
}

variable "vendor_type" {
  description = "(required) - Select PAN. Valid values: 'Generic', 'Palo Alto Networks VM-Series' and 'Aviatrix FQDN Gateway'."
  type        = string
}

variable "vpc_id" {
  description = "(required) - VPC ID."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "aviatrix_firenet_vendor_integration" "this" {
  firewall_name     = var.firewall_name
  instance_id       = var.instance_id
  number_of_retries = var.number_of_retries
  password          = var.password
  public_ip         = var.public_ip
  retry_interval    = var.retry_interval
  route_table       = var.route_table
  save              = var.save
  synchronize       = var.synchronize
  username          = var.username
  vendor_type       = var.vendor_type
  vpc_id            = var.vpc_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.aviatrix_firenet_vendor_integration.this.id
}

output "this" {
  value = aviatrix_firenet_vendor_integration.this
}
```

[top](#index)