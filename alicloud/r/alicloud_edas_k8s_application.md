# alicloud_edas_k8s_application

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_edas_k8s_application" {
  source = "./modules/alicloud/r/alicloud_edas_k8s_application"

  # application_descriotion - (optional) is a type of string
  application_descriotion = null
  # application_name - (required) is a type of string
  application_name = null
  # cluster_id - (required) is a type of string
  cluster_id = null
  # command - (optional) is a type of string
  command = null
  # command_args - (optional) is a type of list of string
  command_args = []
  # edas_container_version - (optional) is a type of string
  edas_container_version = null
  # envs - (optional) is a type of map of string
  envs = {}
  # image_url - (optional) is a type of string
  image_url = null
  # internet_slb_id - (optional) is a type of string
  internet_slb_id = null
  # internet_slb_port - (optional) is a type of number
  internet_slb_port = null
  # internet_slb_protocol - (optional) is a type of string
  internet_slb_protocol = null
  # internet_target_port - (optional) is a type of number
  internet_target_port = null
  # jdk - (optional) is a type of string
  jdk = null
  # limit_m_cpu - (optional) is a type of number
  limit_m_cpu = null
  # limit_mem - (optional) is a type of number
  limit_mem = null
  # liveness - (optional) is a type of string
  liveness = null
  # local_volume - (optional) is a type of string
  local_volume = null
  # logical_region_id - (optional) is a type of string
  logical_region_id = null
  # mount_descs - (optional) is a type of string
  mount_descs = null
  # namespace - (optional) is a type of string
  namespace = null
  # nas_id - (optional) is a type of string
  nas_id = null
  # package_type - (optional) is a type of string
  package_type = null
  # package_url - (optional) is a type of string
  package_url = null
  # package_version - (optional) is a type of string
  package_version = null
  # post_start - (optional) is a type of string
  post_start = null
  # pre_stop - (optional) is a type of string
  pre_stop = null
  # readiness - (optional) is a type of string
  readiness = null
  # replicas - (optional) is a type of number
  replicas = null
  # requests_m_cpu - (optional) is a type of number
  requests_m_cpu = null
  # requests_mem - (optional) is a type of number
  requests_mem = null
  # web_container - (optional) is a type of string
  web_container = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "application_descriotion" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "application_name" {
  description = "(required)"
  type        = string
}

variable "cluster_id" {
  description = "(required)"
  type        = string
}

variable "command" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "command_args" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "edas_container_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "envs" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "image_url" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "internet_slb_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "internet_slb_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "internet_slb_protocol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "internet_target_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "jdk" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "limit_m_cpu" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "limit_mem" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "liveness" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "local_volume" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "logical_region_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mount_descs" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "namespace" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "nas_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "package_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "package_url" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "package_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "post_start" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pre_stop" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "readiness" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "replicas" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "requests_m_cpu" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "requests_mem" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "web_container" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_edas_k8s_application" "this" {
  application_descriotion = var.application_descriotion
  application_name        = var.application_name
  cluster_id              = var.cluster_id
  command                 = var.command
  command_args            = var.command_args
  edas_container_version  = var.edas_container_version
  envs                    = var.envs
  image_url               = var.image_url
  internet_slb_id         = var.internet_slb_id
  internet_slb_port       = var.internet_slb_port
  internet_slb_protocol   = var.internet_slb_protocol
  internet_target_port    = var.internet_target_port
  jdk                     = var.jdk
  limit_m_cpu             = var.limit_m_cpu
  limit_mem               = var.limit_mem
  liveness                = var.liveness
  local_volume            = var.local_volume
  logical_region_id       = var.logical_region_id
  mount_descs             = var.mount_descs
  namespace               = var.namespace
  nas_id                  = var.nas_id
  package_type            = var.package_type
  package_url             = var.package_url
  package_version         = var.package_version
  post_start              = var.post_start
  pre_stop                = var.pre_stop
  readiness               = var.readiness
  replicas                = var.replicas
  requests_m_cpu          = var.requests_m_cpu
  requests_mem            = var.requests_mem
  web_container           = var.web_container

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_edas_k8s_application.this.id
}

output "this" {
  value = alicloud_edas_k8s_application.this
}
```

[top](#index)