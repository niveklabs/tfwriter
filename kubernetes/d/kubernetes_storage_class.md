# kubernetes_storage_class

[back](../kubernetes.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    kubernetes = ">= 2.0.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "kubernetes_storage_class" {
  source = "./modules/kubernetes/d/kubernetes_storage_class"

  # allow_volume_expansion - (optional) is a type of bool
  allow_volume_expansion = null
  # mount_options - (optional) is a type of set of string
  mount_options = []
  # parameters - (optional) is a type of map of string
  parameters = {}
  # reclaim_policy - (optional) is a type of string
  reclaim_policy = null
  # volume_binding_mode - (optional) is a type of string
  volume_binding_mode = null

  allowed_topologies = [{
    match_label_expressions = [{
      key    = null
      values = []
    }]
  }]

  metadata = [{
    annotations      = {}
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

```terraform
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

variable "volume_binding_mode" {
  description = "(optional) - Indicates when volume binding and dynamic provisioning should occur"
  type        = string
  default     = null
}

variable "allowed_topologies" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      match_label_expressions = list(object(
        {
          key    = string
          values = set(string)
        }
      ))
    }
  ))
  default = []
}

variable "metadata" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      annotations      = map(string)
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

### Datasource

```terraform
data "kubernetes_storage_class" "this" {
  # allow_volume_expansion - (optional) is a type of bool
  allow_volume_expansion = var.allow_volume_expansion
  # mount_options - (optional) is a type of set of string
  mount_options = var.mount_options
  # parameters - (optional) is a type of map of string
  parameters = var.parameters
  # reclaim_policy - (optional) is a type of string
  reclaim_policy = var.reclaim_policy
  # volume_binding_mode - (optional) is a type of string
  volume_binding_mode = var.volume_binding_mode

  dynamic "allowed_topologies" {
    for_each = var.allowed_topologies
    content {

      dynamic "match_label_expressions" {
        for_each = allowed_topologies.value.match_label_expressions
        content {
          # key - (optional) is a type of string
          key = match_label_expressions.value["key"]
          # values - (optional) is a type of set of string
          values = match_label_expressions.value["values"]
        }
      }

    }
  }

  dynamic "metadata" {
    for_each = var.metadata
    content {
      # annotations - (optional) is a type of map of string
      annotations = metadata.value["annotations"]
      # labels - (optional) is a type of map of string
      labels = metadata.value["labels"]
      # name - (optional) is a type of string
      name = metadata.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "allow_volume_expansion" {
  description = "returns a bool"
  value       = data.kubernetes_storage_class.this.allow_volume_expansion
}

output "id" {
  description = "returns a string"
  value       = data.kubernetes_storage_class.this.id
}

output "mount_options" {
  description = "returns a set of string"
  value       = data.kubernetes_storage_class.this.mount_options
}

output "parameters" {
  description = "returns a map of string"
  value       = data.kubernetes_storage_class.this.parameters
}

output "reclaim_policy" {
  description = "returns a string"
  value       = data.kubernetes_storage_class.this.reclaim_policy
}

output "storage_provisioner" {
  description = "returns a string"
  value       = data.kubernetes_storage_class.this.storage_provisioner
}

output "volume_binding_mode" {
  description = "returns a string"
  value       = data.kubernetes_storage_class.this.volume_binding_mode
}

output "this" {
  value = kubernetes_storage_class.this
}
```

[top](#index)