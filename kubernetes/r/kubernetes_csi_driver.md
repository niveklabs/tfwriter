# kubernetes_csi_driver

[back](../kubernetes.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    kubernetes = ">= 1.13.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "kubernetes_csi_driver" {
  source = "./modules/kubernetes/r/kubernetes_csi_driver"


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

  spec = [{
    attach_required        = null
    pod_info_on_mount      = null
    volume_lifecycle_modes = []
  }]
}
```

[top](#index)

### Variables

```terraform
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

variable "spec" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      attach_required        = bool
      pod_info_on_mount      = bool
      volume_lifecycle_modes = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "kubernetes_csi_driver" "this" {

  dynamic "metadata" {
    for_each = var.metadata
    content {
      annotations   = metadata.value["annotations"]
      generate_name = metadata.value["generate_name"]
      labels        = metadata.value["labels"]
      name          = metadata.value["name"]
    }
  }

  dynamic "spec" {
    for_each = var.spec
    content {
      attach_required        = spec.value["attach_required"]
      pod_info_on_mount      = spec.value["pod_info_on_mount"]
      volume_lifecycle_modes = spec.value["volume_lifecycle_modes"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = kubernetes_csi_driver.this.id
}

output "this" {
  value = kubernetes_csi_driver.this
}
```

[top](#index)