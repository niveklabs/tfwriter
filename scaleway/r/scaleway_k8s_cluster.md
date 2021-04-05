# scaleway_k8s_cluster

[back](../scaleway.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    scaleway = ">= 2.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "scaleway_k8s_cluster" {
  source = "./modules/scaleway/r/scaleway_k8s_cluster"

  # admission_plugins - (optional) is a type of list of string
  admission_plugins = []
  # apiserver_cert_sans - (optional) is a type of list of string
  apiserver_cert_sans = []
  # cni - (required) is a type of string
  cni = null
  # delete_additional_resources - (optional) is a type of bool
  delete_additional_resources = null
  # description - (optional) is a type of string
  description = null
  # feature_gates - (optional) is a type of list of string
  feature_gates = []
  # name - (required) is a type of string
  name = null
  # project_id - (optional) is a type of string
  project_id = null
  # region - (optional) is a type of string
  region = null
  # tags - (optional) is a type of list of string
  tags = []
  # version - (required) is a type of string
  version = null

  auto_upgrade = [{
    enable                        = null
    maintenance_window_day        = null
    maintenance_window_start_hour = null
  }]

  autoscaler_config = [{
    balance_similar_node_groups      = null
    disable_scale_down               = null
    estimator                        = null
    expander                         = null
    expendable_pods_priority_cutoff  = null
    ignore_daemonsets_utilization    = null
    max_graceful_termination_sec     = null
    scale_down_delay_after_add       = null
    scale_down_unneeded_time         = null
    scale_down_utilization_threshold = null
  }]

  open_id_connect_config = [{
    client_id       = null
    groups_claim    = []
    groups_prefix   = null
    issuer_url      = null
    required_claim  = []
    username_claim  = null
    username_prefix = null
  }]

  timeouts = [{
    default = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "admission_plugins" {
  description = "(optional) - The list of admission plugins to enable on the cluster"
  type        = list(string)
  default     = null
}

variable "apiserver_cert_sans" {
  description = "(optional) - Additional Subject Alternative Names for the Kubernetes API server certificate"
  type        = list(string)
  default     = null
}

variable "cni" {
  description = "(required) - The CNI plugin of the cluster"
  type        = string
}

variable "delete_additional_resources" {
  description = "(optional) - Delete additional resources like block volumes and loadbalancers on cluster deletion"
  type        = bool
  default     = null
}

variable "description" {
  description = "(optional) - The description of the cluster"
  type        = string
  default     = null
}

variable "feature_gates" {
  description = "(optional) - The list of feature gates to enable on the cluster"
  type        = list(string)
  default     = null
}

variable "name" {
  description = "(required) - The name of the cluster"
  type        = string
}

variable "project_id" {
  description = "(optional) - The project_id you want to attach the resource to"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional) - The region you want to attach the resource to"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional) - The tags associated with the cluster"
  type        = list(string)
  default     = null
}

variable "version" {
  description = "(required) - The version of the cluster"
  type        = string
}

variable "auto_upgrade" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      enable                        = bool
      maintenance_window_day        = string
      maintenance_window_start_hour = number
    }
  ))
  default = []
}

variable "autoscaler_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      balance_similar_node_groups      = bool
      disable_scale_down               = bool
      estimator                        = string
      expander                         = string
      expendable_pods_priority_cutoff  = number
      ignore_daemonsets_utilization    = bool
      max_graceful_termination_sec     = number
      scale_down_delay_after_add       = string
      scale_down_unneeded_time         = string
      scale_down_utilization_threshold = number
    }
  ))
  default = []
}

variable "open_id_connect_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      client_id       = string
      groups_claim    = list(string)
      groups_prefix   = string
      issuer_url      = string
      required_claim  = list(string)
      username_claim  = string
      username_prefix = string
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      default = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "scaleway_k8s_cluster" "this" {
  admission_plugins           = var.admission_plugins
  apiserver_cert_sans         = var.apiserver_cert_sans
  cni                         = var.cni
  delete_additional_resources = var.delete_additional_resources
  description                 = var.description
  feature_gates               = var.feature_gates
  name                        = var.name
  project_id                  = var.project_id
  region                      = var.region
  tags                        = var.tags
  version                     = var.version

  dynamic "auto_upgrade" {
    for_each = var.auto_upgrade
    content {
      enable                        = auto_upgrade.value["enable"]
      maintenance_window_day        = auto_upgrade.value["maintenance_window_day"]
      maintenance_window_start_hour = auto_upgrade.value["maintenance_window_start_hour"]
    }
  }

  dynamic "autoscaler_config" {
    for_each = var.autoscaler_config
    content {
      balance_similar_node_groups      = autoscaler_config.value["balance_similar_node_groups"]
      disable_scale_down               = autoscaler_config.value["disable_scale_down"]
      estimator                        = autoscaler_config.value["estimator"]
      expander                         = autoscaler_config.value["expander"]
      expendable_pods_priority_cutoff  = autoscaler_config.value["expendable_pods_priority_cutoff"]
      ignore_daemonsets_utilization    = autoscaler_config.value["ignore_daemonsets_utilization"]
      max_graceful_termination_sec     = autoscaler_config.value["max_graceful_termination_sec"]
      scale_down_delay_after_add       = autoscaler_config.value["scale_down_delay_after_add"]
      scale_down_unneeded_time         = autoscaler_config.value["scale_down_unneeded_time"]
      scale_down_utilization_threshold = autoscaler_config.value["scale_down_utilization_threshold"]
    }
  }

  dynamic "open_id_connect_config" {
    for_each = var.open_id_connect_config
    content {
      client_id       = open_id_connect_config.value["client_id"]
      groups_claim    = open_id_connect_config.value["groups_claim"]
      groups_prefix   = open_id_connect_config.value["groups_prefix"]
      issuer_url      = open_id_connect_config.value["issuer_url"]
      required_claim  = open_id_connect_config.value["required_claim"]
      username_claim  = open_id_connect_config.value["username_claim"]
      username_prefix = open_id_connect_config.value["username_prefix"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      default = timeouts.value["default"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "apiserver_url" {
  description = "returns a string"
  value       = scaleway_k8s_cluster.this.apiserver_url
}

output "created_at" {
  description = "returns a string"
  value       = scaleway_k8s_cluster.this.created_at
}

output "id" {
  description = "returns a string"
  value       = scaleway_k8s_cluster.this.id
}

output "kubeconfig" {
  description = "returns a list of object"
  value       = scaleway_k8s_cluster.this.kubeconfig
}

output "organization_id" {
  description = "returns a string"
  value       = scaleway_k8s_cluster.this.organization_id
}

output "project_id" {
  description = "returns a string"
  value       = scaleway_k8s_cluster.this.project_id
}

output "region" {
  description = "returns a string"
  value       = scaleway_k8s_cluster.this.region
}

output "status" {
  description = "returns a string"
  value       = scaleway_k8s_cluster.this.status
}

output "updated_at" {
  description = "returns a string"
  value       = scaleway_k8s_cluster.this.updated_at
}

output "upgrade_available" {
  description = "returns a bool"
  value       = scaleway_k8s_cluster.this.upgrade_available
}

output "wildcard_dns" {
  description = "returns a string"
  value       = scaleway_k8s_cluster.this.wildcard_dns
}

output "this" {
  value = scaleway_k8s_cluster.this
}
```

[top](#index)