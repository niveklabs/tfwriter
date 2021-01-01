# kubernetes_storage_class

[back](../kubernetes.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    kubernetes = ">= 1.13.3"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "kubernetes_storage_class" {
  source = "./modules/kubernetes/r/kubernetes_storage_class"

  # allow_volume_expansion - (optional) is a type of bool
  allow_volume_expansion = null
  # mount_options - (optional) is a type of set of string
  mount_options = []
  # parameters - (optional) is a type of map of string
  parameters = {}
  # reclaim_policy - (optional) is a type of string
  reclaim_policy = null
  # storage_provisioner - (required) is a type of string
  storage_provisioner = null
  # volume_binding_mode - (optional) is a type of string
  volume_binding_mode = null

  metadata = [{
    annotations      = {}
    generate_name    = null
    generation       = null
    labels           = {}
    name             = null
    resource_version = null
    self_link        = null
    uid              = null
  }]
}
```

[top](#index)

### Variables

```hcl
variable "allow_volume_expansion" {
  description = "(optional) - Indicates whether the storage class allow volume expand"
  type        = bool
  default     = null
}

variable "mount_options" {
  description = "(optional) - Persistent Volumes that are dynamically created by a storage class will have the mount options specified"
  type        = set(string)
  default     = null
}

variable "parameters" {
  description = "(optional) - The parameters for the provisioner that should create volumes of this storage class"
  type        = map(string)
  default     = null
}

variable "reclaim_policy" {
  description = "(optional) - Indicates the type of the reclaim policy"
  type        = string
  default     = null
}

variable "storage_provisioner" {
  description = "(required) - Indicates the type of the provisioner"
  type        = string
}

variable "volume_binding_mode" {
  description = "(optional) - Indicates when volume binding and dynamic provisioning should occur"
  type        = string
  default     = null
}

variable "metadata" {
  description = "nested mode: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      annotations      = map(string)
      generate_name    = string
      generation       = number
      labels           = map(string)
      name             = string
      resource_version = string
      self_link        = string
      uid              = string
    }
  ))
}
```

[top](#index)

### Resource

```hcl
resource "kubernetes_storage_class" "this" {
  allow_volume_expansion = var.allow_volume_expansion
  mount_options          = var.mount_options
  parameters             = var.parameters
  reclaim_policy         = var.reclaim_policy
  storage_provisioner    = var.storage_provisioner
  volume_binding_mode    = var.volume_binding_mode

  dynamic "metadata" {
    for_each = var.metadata
    content {
      annotations   = metadata.value["annotations"]
      generate_name = metadata.value["generate_name"]
      labels        = metadata.value["labels"]
      name          = metadata.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = kubernetes_storage_class.this.id
}

output "this" {
  value = kubernetes_storage_class.this
}
```

[top](#index)