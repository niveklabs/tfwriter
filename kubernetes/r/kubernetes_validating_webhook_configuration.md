# kubernetes_validating_webhook_configuration

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
module "kubernetes_validating_webhook_configuration" {
  source = "./modules/kubernetes/r/kubernetes_validating_webhook_configuration"


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

  webhook = [{
    admission_review_versions = []
    client_config = [{
      ca_bundle = null
      service = [{
        name      = null
        namespace = null
        path      = null
        port      = null
      }]
      url = null
    }]
    failure_policy = null
    match_policy   = null
    name           = null
    namespace_selector = [{
      match_expressions = [{
        key      = null
        operator = null
        values   = []
      }]
      match_labels = {}
    }]
    object_selector = [{
      match_expressions = [{
        key      = null
        operator = null
        values   = []
      }]
      match_labels = {}
    }]
    rule = [{
      api_groups   = []
      api_versions = []
      operations   = []
      resources    = []
      scope        = null
    }]
    side_effects    = null
    timeout_seconds = null
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

variable "webhook" {
  description = "nested mode: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      admission_review_versions = list(string)
      client_config = list(object(
        {
          ca_bundle = string
          service = list(object(
            {
              name      = string
              namespace = string
              path      = string
              port      = number
            }
          ))
          url = string
        }
      ))
      failure_policy = string
      match_policy   = string
      name           = string
      namespace_selector = list(object(
        {
          match_expressions = list(object(
            {
              key      = string
              operator = string
              values   = set(string)
            }
          ))
          match_labels = map(string)
        }
      ))
      object_selector = list(object(
        {
          match_expressions = list(object(
            {
              key      = string
              operator = string
              values   = set(string)
            }
          ))
          match_labels = map(string)
        }
      ))
      rule = list(object(
        {
          api_groups   = list(string)
          api_versions = list(string)
          operations   = list(string)
          resources    = list(string)
          scope        = string
        }
      ))
      side_effects    = string
      timeout_seconds = number
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "kubernetes_validating_webhook_configuration" "this" {

  dynamic "metadata" {
    for_each = var.metadata
    content {
      annotations   = metadata.value["annotations"]
      generate_name = metadata.value["generate_name"]
      labels        = metadata.value["labels"]
      name          = metadata.value["name"]
    }
  }

  dynamic "webhook" {
    for_each = var.webhook
    content {
      admission_review_versions = webhook.value["admission_review_versions"]
      failure_policy            = webhook.value["failure_policy"]
      match_policy              = webhook.value["match_policy"]
      name                      = webhook.value["name"]
      side_effects              = webhook.value["side_effects"]
      timeout_seconds           = webhook.value["timeout_seconds"]

      dynamic "client_config" {
        for_each = webhook.value.client_config
        content {
          ca_bundle = client_config.value["ca_bundle"]
          url       = client_config.value["url"]

          dynamic "service" {
            for_each = client_config.value.service
            content {
              name      = service.value["name"]
              namespace = service.value["namespace"]
              path      = service.value["path"]
              port      = service.value["port"]
            }
          }

        }
      }

      dynamic "namespace_selector" {
        for_each = webhook.value.namespace_selector
        content {
          match_labels = namespace_selector.value["match_labels"]

          dynamic "match_expressions" {
            for_each = namespace_selector.value.match_expressions
            content {
              key      = match_expressions.value["key"]
              operator = match_expressions.value["operator"]
              values   = match_expressions.value["values"]
            }
          }

        }
      }

      dynamic "object_selector" {
        for_each = webhook.value.object_selector
        content {
          match_labels = object_selector.value["match_labels"]

          dynamic "match_expressions" {
            for_each = object_selector.value.match_expressions
            content {
              key      = match_expressions.value["key"]
              operator = match_expressions.value["operator"]
              values   = match_expressions.value["values"]
            }
          }

        }
      }

      dynamic "rule" {
        for_each = webhook.value.rule
        content {
          api_groups   = rule.value["api_groups"]
          api_versions = rule.value["api_versions"]
          operations   = rule.value["operations"]
          resources    = rule.value["resources"]
          scope        = rule.value["scope"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = kubernetes_validating_webhook_configuration.this.id
}

output "this" {
  value = kubernetes_validating_webhook_configuration.this
}
```

[top](#index)