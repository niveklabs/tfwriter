# vsphere_host

[back](../vsphere.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vsphere = ">= 1.25.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vsphere_host" {
  source = "./modules/vsphere/r/vsphere_host"

  # cluster - (optional) is a type of string
  cluster = null
  # cluster_managed - (optional) is a type of bool
  cluster_managed = null
  # connected - (optional) is a type of bool
  connected = null
  # datacenter - (optional) is a type of string
  datacenter = null
  # force - (optional) is a type of bool
  force = null
  # hostname - (required) is a type of string
  hostname = null
  # license - (optional) is a type of string
  license = null
  # lockdown - (optional) is a type of string
  lockdown = null
  # maintenance - (optional) is a type of bool
  maintenance = null
  # password - (required) is a type of string
  password = null
  # thumbprint - (optional) is a type of string
  thumbprint = null
  # username - (required) is a type of string
  username = null
}
```

[top](#index)

### Variables

```terraform
variable "cluster" {
  description = "(optional) - ID of the vSphere cluster the host will belong to."
  type        = string
  default     = null
}

variable "cluster_managed" {
  description = "(optional) - Must be set if host is a member of a managed compute_cluster resource."
  type        = bool
  default     = null
}

variable "connected" {
  description = "(optional) - Set the state of the host. If set to false then the host will be asked to disconnect."
  type        = bool
  default     = null
}

variable "datacenter" {
  description = "(optional) - ID of the vSphere datacenter the host will belong to."
  type        = string
  default     = null
}

variable "force" {
  description = "(optional) - Force add the host to vsphere, even if it's already managed by a different vSphere instance."
  type        = bool
  default     = null
}

variable "hostname" {
  description = "(required) - FQDN or IP address of the host."
  type        = string
}

variable "license" {
  description = "(optional) - License key that will be applied to this host."
  type        = string
  default     = null
}

variable "lockdown" {
  description = "(optional) - Set the host's lockdown status. Default is disabled. Valid options are 'disabled', 'normal', 'strict'"
  type        = string
  default     = null
}

variable "maintenance" {
  description = "(optional) - Set the host's maintenance mode. Default is false"
  type        = bool
  default     = null
}

variable "password" {
  description = "(required) - Password of the administration account of the host."
  type        = string
}

variable "thumbprint" {
  description = "(optional) - Host's certificate SHA-1 thumbprint. If not set then the CA that signed the host's certificate must be trusted."
  type        = string
  default     = null
}

variable "username" {
  description = "(required) - Username of the administration account of the host."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "vsphere_host" "this" {
  # cluster - (optional) is a type of string
  cluster = var.cluster
  # cluster_managed - (optional) is a type of bool
  cluster_managed = var.cluster_managed
  # connected - (optional) is a type of bool
  connected = var.connected
  # datacenter - (optional) is a type of string
  datacenter = var.datacenter
  # force - (optional) is a type of bool
  force = var.force
  # hostname - (required) is a type of string
  hostname = var.hostname
  # license - (optional) is a type of string
  license = var.license
  # lockdown - (optional) is a type of string
  lockdown = var.lockdown
  # maintenance - (optional) is a type of bool
  maintenance = var.maintenance
  # password - (required) is a type of string
  password = var.password
  # thumbprint - (optional) is a type of string
  thumbprint = var.thumbprint
  # username - (required) is a type of string
  username = var.username
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vsphere_host.this.id
}

output "this" {
  value = vsphere_host.this
}
```

[top](#index)