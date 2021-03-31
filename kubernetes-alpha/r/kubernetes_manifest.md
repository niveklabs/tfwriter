# kubernetes_manifest

[back](../kubernetes-alpha.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    kubernetes-alpha = ">= 0.3.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "kubernetes_manifest" {
  source = "./modules/kubernetes-alpha/r/kubernetes_manifest"

  # manifest - (required) is a type of dynamic
  manifest = null
  # object - (optional) is a type of dynamic
  object = null
  # wait_for - (optional) is a type of object
  wait_for = {
    fields = {}
  }
}
```

[top](#index)

### Variables

```terraform
variable "manifest" {
  description = "(required) - A Kubernetes manifest describing the desired state of the resource in HCL format."
  type        = any
}

variable "object" {
  description = "(optional) - The resulting resource state, as returned by the API server after applying the desired state from `manifest`."
  type        = any
  default     = null
}

variable "wait_for" {
  description = "(optional) - A map of attribute paths and desired patterns to be matched. After each apply the provider will wait for all attributes listed here to reach a value that matches the desired pattern."
  type = object(
    {
      fields = map(string)
    }
  )
  default = null
}
```

[top](#index)

### Resource

```terraform
resource "kubernetes_manifest" "this" {
  manifest = var.manifest
  object   = var.object
  wait_for = var.wait_for
}
```

[top](#index)

### Outputs

```terraform
output "object" {
  description = "returns a dynamic"
  value       = kubernetes_manifest.this.object
}

output "this" {
  value = kubernetes_manifest.this
}
```

[top](#index)