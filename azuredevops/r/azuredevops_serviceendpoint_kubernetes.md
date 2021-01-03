# azuredevops_serviceendpoint_kubernetes

[back](../azuredevops.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    azuredevops = ">= 0.1.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azuredevops_serviceendpoint_kubernetes" {
  source = "./modules/azuredevops/r/azuredevops_serviceendpoint_kubernetes"

  # apiserver_url - (required) is a type of string
  apiserver_url = null
  # authorization - (optional) is a type of map of string
  authorization = {}
  # authorization_type - (required) is a type of string
  authorization_type = null
  # description - (optional) is a type of string
  description = null
  # project_id - (required) is a type of string
  project_id = null
  # service_endpoint_name - (required) is a type of string
  service_endpoint_name = null

  azure_subscription = [{
    azure_environment = null
    cluster_name      = null
    namespace         = null
    resourcegroup_id  = null
    subscription_id   = null
    subscription_name = null
    tenant_id         = null
  }]

  kubeconfig = [{
    accept_untrusted_certs = null
    cluster_context        = null
    kube_config            = null
    kube_config_hash       = null
  }]

  service_account = [{
    ca_cert      = null
    ca_cert_hash = null
    token        = null
    token_hash   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "apiserver_url" {
  description = "(required) - URL to Kubernete's API-Server"
  type        = string
}

variable "authorization" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "authorization_type" {
  description = "(required) - Type of credentials to use"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "project_id" {
  description = "(required)"
  type        = string
}

variable "service_endpoint_name" {
  description = "(required)"
  type        = string
}

variable "azure_subscription" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      azure_environment = string
      cluster_name      = string
      namespace         = string
      resourcegroup_id  = string
      subscription_id   = string
      subscription_name = string
      tenant_id         = string
    }
  ))
  default = []
}

variable "kubeconfig" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      accept_untrusted_certs = bool
      cluster_context        = string
      kube_config            = string
      kube_config_hash       = string
    }
  ))
  default = []
}

variable "service_account" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      ca_cert      = string
      ca_cert_hash = string
      token        = string
      token_hash   = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azuredevops_serviceendpoint_kubernetes" "this" {
  apiserver_url         = var.apiserver_url
  authorization         = var.authorization
  authorization_type    = var.authorization_type
  description           = var.description
  project_id            = var.project_id
  service_endpoint_name = var.service_endpoint_name

  dynamic "azure_subscription" {
    for_each = var.azure_subscription
    content {
      azure_environment = azure_subscription.value["azure_environment"]
      cluster_name      = azure_subscription.value["cluster_name"]
      namespace         = azure_subscription.value["namespace"]
      resourcegroup_id  = azure_subscription.value["resourcegroup_id"]
      subscription_id   = azure_subscription.value["subscription_id"]
      subscription_name = azure_subscription.value["subscription_name"]
      tenant_id         = azure_subscription.value["tenant_id"]
    }
  }

  dynamic "kubeconfig" {
    for_each = var.kubeconfig
    content {
      accept_untrusted_certs = kubeconfig.value["accept_untrusted_certs"]
      cluster_context        = kubeconfig.value["cluster_context"]
      kube_config            = kubeconfig.value["kube_config"]
    }
  }

  dynamic "service_account" {
    for_each = var.service_account
    content {
      ca_cert = service_account.value["ca_cert"]
      token   = service_account.value["token"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "authorization" {
  description = "returns a map of string"
  value       = azuredevops_serviceendpoint_kubernetes.this.authorization
}

output "id" {
  description = "returns a string"
  value       = azuredevops_serviceendpoint_kubernetes.this.id
}

output "this" {
  value = azuredevops_serviceendpoint_kubernetes.this
}
```

[top](#index)