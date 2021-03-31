# kubernetes_cluster_role

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
    kubernetes = ">= 2.0.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "kubernetes_cluster_role" {
  source = "./modules/kubernetes/r/kubernetes_cluster_role"


  aggregation_rule = [{
    cluster_role_selectors = [{
      match_expressions = [{
        key      = null
        operator = null
        values   = []
      }]
      match_labels = {}
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

  rule = [{
    api_groups        = []
    non_resource_urls = []
    resource_names    = []
    resources         = []
    verbs             = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "aggregation_rule" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      cluster_role_selectors = list(object(
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

variable "rule" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      api_groups        = list(string)
      non_resource_urls = list(string)
      resource_names    = list(string)
      resources         = list(string)
      verbs             = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "kubernetes_cluster_role" "this" {

  dynamic "aggregation_rule" {
    for_each = var.aggregation_rule
    content {

      dynamic "cluster_role_selectors" {
        for_each = aggregation_rule.value.cluster_role_selectors
        content {
          match_labels = cluster_role_selectors.value["match_labels"]

          dynamic "match_expressions" {
            for_each = cluster_role_selectors.value.match_expressions
            content {
              key      = match_expressions.value["key"]
              operator = match_expressions.value["operator"]
              values   = match_expressions.value["values"]
            }
          }

        }
      }

    }
  }

  dynamic "metadata" {
    for_each = var.metadata
    content {
      annotations = metadata.value["annotations"]
      labels      = metadata.value["labels"]
      name        = metadata.value["name"]
    }
  }

  dynamic "rule" {
    for_each = var.rule
    content {
      api_groups        = rule.value["api_groups"]
      non_resource_urls = rule.value["non_resource_urls"]
      resource_names    = rule.value["resource_names"]
      resources         = rule.value["resources"]
      verbs             = rule.value["verbs"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = kubernetes_cluster_role.this.id
}

output "this" {
  value = kubernetes_cluster_role.this
}
```

[top](#index)