# rancher2_cloud_credential

[back](../rancher2.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    rancher2 = ">= 1.13.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "rancher2_cloud_credential" {
  source = "./modules/rancher2/r/rancher2_cloud_credential"

  # annotations - (optional) is a type of map of string
  annotations = {}
  # description - (optional) is a type of string
  description = null
  # labels - (optional) is a type of map of string
  labels = {}
  # name - (required) is a type of string
  name = null

  amazonec2_credential_config = [{
    access_key = null
    secret_key = null
  }]

  azure_credential_config = [{
    client_id       = null
    client_secret   = null
    subscription_id = null
  }]

  digitalocean_credential_config = [{
    access_token = null
  }]

  linode_credential_config = [{
    token = null
  }]

  openstack_credential_config = [{
    password = null
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]

  vsphere_credential_config = [{
    password     = null
    username     = null
    vcenter      = null
    vcenter_port = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "annotations" {
  description = "(optional) - Annotations of the resource"
  type        = map(string)
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "labels" {
  description = "(optional) - Labels of the resource"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "amazonec2_credential_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      access_key = string
      secret_key = string
    }
  ))
  default = []
}

variable "azure_credential_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      client_id       = string
      client_secret   = string
      subscription_id = string
    }
  ))
  default = []
}

variable "digitalocean_credential_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      access_token = string
    }
  ))
  default = []
}

variable "linode_credential_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      token = string
    }
  ))
  default = []
}

variable "openstack_credential_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      password = string
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}

variable "vsphere_credential_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      password     = string
      username     = string
      vcenter      = string
      vcenter_port = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "rancher2_cloud_credential" "this" {
  # annotations - (optional) is a type of map of string
  annotations = var.annotations
  # description - (optional) is a type of string
  description = var.description
  # labels - (optional) is a type of map of string
  labels = var.labels
  # name - (required) is a type of string
  name = var.name

  dynamic "amazonec2_credential_config" {
    for_each = var.amazonec2_credential_config
    content {
      # access_key - (required) is a type of string
      access_key = amazonec2_credential_config.value["access_key"]
      # secret_key - (required) is a type of string
      secret_key = amazonec2_credential_config.value["secret_key"]
    }
  }

  dynamic "azure_credential_config" {
    for_each = var.azure_credential_config
    content {
      # client_id - (required) is a type of string
      client_id = azure_credential_config.value["client_id"]
      # client_secret - (required) is a type of string
      client_secret = azure_credential_config.value["client_secret"]
      # subscription_id - (required) is a type of string
      subscription_id = azure_credential_config.value["subscription_id"]
    }
  }

  dynamic "digitalocean_credential_config" {
    for_each = var.digitalocean_credential_config
    content {
      # access_token - (required) is a type of string
      access_token = digitalocean_credential_config.value["access_token"]
    }
  }

  dynamic "linode_credential_config" {
    for_each = var.linode_credential_config
    content {
      # token - (required) is a type of string
      token = linode_credential_config.value["token"]
    }
  }

  dynamic "openstack_credential_config" {
    for_each = var.openstack_credential_config
    content {
      # password - (required) is a type of string
      password = openstack_credential_config.value["password"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

  dynamic "vsphere_credential_config" {
    for_each = var.vsphere_credential_config
    content {
      # password - (required) is a type of string
      password = vsphere_credential_config.value["password"]
      # username - (required) is a type of string
      username = vsphere_credential_config.value["username"]
      # vcenter - (required) is a type of string
      vcenter = vsphere_credential_config.value["vcenter"]
      # vcenter_port - (optional) is a type of string
      vcenter_port = vsphere_credential_config.value["vcenter_port"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "annotations" {
  description = "returns a map of string"
  value       = rancher2_cloud_credential.this.annotations
}

output "driver" {
  description = "returns a string"
  value       = rancher2_cloud_credential.this.driver
}

output "id" {
  description = "returns a string"
  value       = rancher2_cloud_credential.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = rancher2_cloud_credential.this.labels
}

output "this" {
  value = rancher2_cloud_credential.this
}
```

[top](#index)