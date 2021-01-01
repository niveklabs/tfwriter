# vsphere_host

[back](../vsphere.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    vsphere = ">= 1.24.3"
  }
}
```

[top](#index)

### Example Usage

```hcl
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

```hcl
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

```hcl
resource "vsphere_host" "this" {
  cluster         = var.cluster
  cluster_managed = var.cluster_managed
  connected       = var.connected
  datacenter      = var.datacenter
  force           = var.force
  hostname        = var.hostname
  license         = var.license
  lockdown        = var.lockdown
  maintenance     = var.maintenance
  password        = var.password
  thumbprint      = var.thumbprint
  username        = var.username
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = vsphere_host.this.id
}

output "this" {
  value = vsphere_host.this
}
```

[top](#index)