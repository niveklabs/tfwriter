# helm_release

[back](../helm.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    helm = ">= 2.1.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "helm_release" {
  source = "./modules/helm/r/helm_release"

  # atomic - (optional) is a type of bool
  atomic = null
  # chart - (required) is a type of string
  chart = null
  # cleanup_on_fail - (optional) is a type of bool
  cleanup_on_fail = null
  # create_namespace - (optional) is a type of bool
  create_namespace = null
  # dependency_update - (optional) is a type of bool
  dependency_update = null
  # description - (optional) is a type of string
  description = null
  # devel - (optional) is a type of bool
  devel = null
  # disable_crd_hooks - (optional) is a type of bool
  disable_crd_hooks = null
  # disable_openapi_validation - (optional) is a type of bool
  disable_openapi_validation = null
  # disable_webhooks - (optional) is a type of bool
  disable_webhooks = null
  # force_update - (optional) is a type of bool
  force_update = null
  # keyring - (optional) is a type of string
  keyring = null
  # lint - (optional) is a type of bool
  lint = null
  # max_history - (optional) is a type of number
  max_history = null
  # name - (required) is a type of string
  name = null
  # namespace - (optional) is a type of string
  namespace = null
  # recreate_pods - (optional) is a type of bool
  recreate_pods = null
  # render_subchart_notes - (optional) is a type of bool
  render_subchart_notes = null
  # replace - (optional) is a type of bool
  replace = null
  # repository - (optional) is a type of string
  repository = null
  # repository_ca_file - (optional) is a type of string
  repository_ca_file = null
  # repository_cert_file - (optional) is a type of string
  repository_cert_file = null
  # repository_key_file - (optional) is a type of string
  repository_key_file = null
  # repository_password - (optional) is a type of string
  repository_password = null
  # repository_username - (optional) is a type of string
  repository_username = null
  # reset_values - (optional) is a type of bool
  reset_values = null
  # reuse_values - (optional) is a type of bool
  reuse_values = null
  # skip_crds - (optional) is a type of bool
  skip_crds = null
  # timeout - (optional) is a type of number
  timeout = null
  # values - (optional) is a type of list of string
  values = []
  # verify - (optional) is a type of bool
  verify = null
  # version - (optional) is a type of string
  version = null
  # wait - (optional) is a type of bool
  wait = null

  postrender = [{
    binary_path = null
  }]

  set = [{
    name  = null
    type  = null
    value = null
  }]

  set_sensitive = [{
    name  = null
    type  = null
    value = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "atomic" {
  description = "(optional) - If set, installation process purges chart on fail. The wait flag will be set automatically if atomic is used"
  type        = bool
  default     = null
}

variable "chart" {
  description = "(required) - Chart name to be installed. A path may be used."
  type        = string
}

variable "cleanup_on_fail" {
  description = "(optional) - Allow deletion of new resources created in this upgrade when upgrade fails"
  type        = bool
  default     = null
}

variable "create_namespace" {
  description = "(optional) - Create the namespace if it does not exist"
  type        = bool
  default     = null
}

variable "dependency_update" {
  description = "(optional) - Run helm dependency update before installing the chart"
  type        = bool
  default     = null
}

variable "description" {
  description = "(optional) - Add a custom description"
  type        = string
  default     = null
}

variable "devel" {
  description = "(optional) - Use chart development versions, too. Equivalent to version '>0.0.0-0'. If `version` is set, this is ignored"
  type        = bool
  default     = null
}

variable "disable_crd_hooks" {
  description = "(optional) - Prevent CRD hooks from, running, but run other hooks.  See helm install --no-crd-hook"
  type        = bool
  default     = null
}

variable "disable_openapi_validation" {
  description = "(optional) - If set, the installation process will not validate rendered templates against the Kubernetes OpenAPI Schema"
  type        = bool
  default     = null
}

variable "disable_webhooks" {
  description = "(optional) - Prevent hooks from running."
  type        = bool
  default     = null
}

variable "force_update" {
  description = "(optional) - Force resource update through delete/recreate if needed."
  type        = bool
  default     = null
}

variable "keyring" {
  description = "(optional) - Location of public keys used for verification. Used only if `verify` is true"
  type        = string
  default     = null
}

variable "lint" {
  description = "(optional) - Run helm lint when planning"
  type        = bool
  default     = null
}

variable "max_history" {
  description = "(optional) - Limit the maximum number of revisions saved per release. Use 0 for no limit"
  type        = number
  default     = null
}

variable "name" {
  description = "(required) - Release name."
  type        = string
}

variable "namespace" {
  description = "(optional) - Namespace to install the release into."
  type        = string
  default     = null
}

variable "recreate_pods" {
  description = "(optional) - Perform pods restart during upgrade/rollback"
  type        = bool
  default     = null
}

variable "render_subchart_notes" {
  description = "(optional) - If set, render subchart notes along with the parent"
  type        = bool
  default     = null
}

variable "replace" {
  description = "(optional) - Re-use the given name, even if that name is already used. This is unsafe in production"
  type        = bool
  default     = null
}

variable "repository" {
  description = "(optional) - Repository where to locate the requested chart. If is a URL the chart is installed without installing the repository."
  type        = string
  default     = null
}

variable "repository_ca_file" {
  description = "(optional) - The Repositories CA File"
  type        = string
  default     = null
}

variable "repository_cert_file" {
  description = "(optional) - The repositories cert file"
  type        = string
  default     = null
}

variable "repository_key_file" {
  description = "(optional) - The repositories cert key file"
  type        = string
  default     = null
}

variable "repository_password" {
  description = "(optional) - Password for HTTP basic authentication"
  type        = string
  default     = null
}

variable "repository_username" {
  description = "(optional) - Username for HTTP basic authentication"
  type        = string
  default     = null
}

variable "reset_values" {
  description = "(optional) - When upgrading, reset the values to the ones built into the chart"
  type        = bool
  default     = null
}

variable "reuse_values" {
  description = "(optional) - When upgrading, reuse the last release's values and merge in any overrides. If 'reset_values' is specified, this is ignored"
  type        = bool
  default     = null
}

variable "skip_crds" {
  description = "(optional) - If set, no CRDs will be installed. By default, CRDs are installed if not already present"
  type        = bool
  default     = null
}

variable "timeout" {
  description = "(optional) - Time in seconds to wait for any individual kubernetes operation."
  type        = number
  default     = null
}

variable "values" {
  description = "(optional) - List of values in raw yaml format to pass to helm."
  type        = list(string)
  default     = null
}

variable "verify" {
  description = "(optional) - Verify the package before installing it."
  type        = bool
  default     = null
}

variable "version" {
  description = "(optional) - Specify the exact chart version to install. If this is not specified, the latest version is installed."
  type        = string
  default     = null
}

variable "wait" {
  description = "(optional) - Will wait until all resources are in a ready state before marking the release as successful."
  type        = bool
  default     = null
}

variable "postrender" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      binary_path = string
    }
  ))
  default = []
}

variable "set" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name  = string
      type  = string
      value = string
    }
  ))
  default = []
}

variable "set_sensitive" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name  = string
      type  = string
      value = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "helm_release" "this" {
  atomic                     = var.atomic
  chart                      = var.chart
  cleanup_on_fail            = var.cleanup_on_fail
  create_namespace           = var.create_namespace
  dependency_update          = var.dependency_update
  description                = var.description
  devel                      = var.devel
  disable_crd_hooks          = var.disable_crd_hooks
  disable_openapi_validation = var.disable_openapi_validation
  disable_webhooks           = var.disable_webhooks
  force_update               = var.force_update
  keyring                    = var.keyring
  lint                       = var.lint
  max_history                = var.max_history
  name                       = var.name
  namespace                  = var.namespace
  recreate_pods              = var.recreate_pods
  render_subchart_notes      = var.render_subchart_notes
  replace                    = var.replace
  repository                 = var.repository
  repository_ca_file         = var.repository_ca_file
  repository_cert_file       = var.repository_cert_file
  repository_key_file        = var.repository_key_file
  repository_password        = var.repository_password
  repository_username        = var.repository_username
  reset_values               = var.reset_values
  reuse_values               = var.reuse_values
  skip_crds                  = var.skip_crds
  timeout                    = var.timeout
  values                     = var.values
  verify                     = var.verify
  version                    = var.version
  wait                       = var.wait

  dynamic "postrender" {
    for_each = var.postrender
    content {
      binary_path = postrender.value["binary_path"]
    }
  }

  dynamic "set" {
    for_each = var.set
    content {
      name  = set.value["name"]
      type  = set.value["type"]
      value = set.value["value"]
    }
  }

  dynamic "set_sensitive" {
    for_each = var.set_sensitive
    content {
      name  = set_sensitive.value["name"]
      type  = set_sensitive.value["type"]
      value = set_sensitive.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = helm_release.this.id
}

output "manifest" {
  description = "returns a string"
  value       = helm_release.this.manifest
}

output "metadata" {
  description = "returns a list of object"
  value       = helm_release.this.metadata
}

output "status" {
  description = "returns a string"
  value       = helm_release.this.status
}

output "version" {
  description = "returns a string"
  value       = helm_release.this.version
}

output "this" {
  value = helm_release.this
}
```

[top](#index)