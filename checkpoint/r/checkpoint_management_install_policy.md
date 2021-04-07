# checkpoint_management_install_policy

[back](../checkpoint.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    checkpoint = ">= 1.4.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "checkpoint_management_install_policy" {
  source = "./modules/checkpoint/r/checkpoint_management_install_policy"

  # access - (optional) is a type of bool
  access = null
  # desktop_security - (optional) is a type of bool
  desktop_security = null
  # install_on_all_cluster_members_or_fail - (optional) is a type of bool
  install_on_all_cluster_members_or_fail = null
  # policy_package - (required) is a type of string
  policy_package = null
  # prepare_only - (optional) is a type of bool
  prepare_only = null
  # qos - (optional) is a type of bool
  qos = null
  # revision - (optional) is a type of string
  revision = null
  # targets - (required) is a type of set of string
  targets = []
  # threat_prevention - (optional) is a type of bool
  threat_prevention = null
  # triggers - (optional) is a type of set of string
  triggers = []
}
```

[top](#index)

### Variables

```terraform
variable "access" {
  description = "(optional) - Set to be true in order to install the Access Control policy. By default, the value is true if Access Control policy is enabled on the input policy package, otherwise false."
  type        = bool
  default     = null
}

variable "desktop_security" {
  description = "(optional) - Set to be true in order to install the Desktop Security policy. By default, the value is true if desktop security policy is enabled on the input policy package, otherwise false."
  type        = bool
  default     = null
}

variable "install_on_all_cluster_members_or_fail" {
  description = "(optional) - Relevant for the gateway clusters. If true, the policy is installed on all the cluster members. If the installation on a cluster member fails, don't install on that cluster."
  type        = bool
  default     = null
}

variable "policy_package" {
  description = "(required) - The name of the Policy Package to be installed."
  type        = string
}

variable "prepare_only" {
  description = "(optional) - If true, prepares the policy for the installation, but doesn't install it on an installation target."
  type        = bool
  default     = null
}

variable "qos" {
  description = "(optional) - Set to be true in order to install the QoS policy. By default, the value is true if Quality-of-Service policy is enabled on the input policy package, otherwise false."
  type        = bool
  default     = null
}

variable "revision" {
  description = "(optional) - The UID of the revision of the policy to install."
  type        = string
  default     = null
}

variable "targets" {
  description = "(required) - On what targets to execute this command. Targets may be identified by their name, or object unique identifier."
  type        = set(string)
}

variable "threat_prevention" {
  description = "(optional) - Set to be true in order to install the Threat Prevention policy. By default, the value is true if Threat Prevention policy is enabled on the input policy package, otherwise false."
  type        = bool
  default     = null
}

variable "triggers" {
  description = "(optional) - Triggers a install-policy if there are any changes to objects in this list."
  type        = set(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "checkpoint_management_install_policy" "this" {
  # access - (optional) is a type of bool
  access = var.access
  # desktop_security - (optional) is a type of bool
  desktop_security = var.desktop_security
  # install_on_all_cluster_members_or_fail - (optional) is a type of bool
  install_on_all_cluster_members_or_fail = var.install_on_all_cluster_members_or_fail
  # policy_package - (required) is a type of string
  policy_package = var.policy_package
  # prepare_only - (optional) is a type of bool
  prepare_only = var.prepare_only
  # qos - (optional) is a type of bool
  qos = var.qos
  # revision - (optional) is a type of string
  revision = var.revision
  # targets - (required) is a type of set of string
  targets = var.targets
  # threat_prevention - (optional) is a type of bool
  threat_prevention = var.threat_prevention
  # triggers - (optional) is a type of set of string
  triggers = var.triggers
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_install_policy.this.id
}

output "task_id" {
  description = "returns a string"
  value       = checkpoint_management_install_policy.this.task_id
}

output "this" {
  value = checkpoint_management_install_policy.this
}
```

[top](#index)