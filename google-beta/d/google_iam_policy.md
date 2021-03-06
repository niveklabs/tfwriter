# google_iam_policy

[back](../google-beta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    google-beta = ">= 3.63.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_iam_policy" {
  source = "./modules/google-beta/d/google_iam_policy"


  audit_config = [{
    audit_log_configs = [{
      exempted_members = []
      log_type         = null
    }]
    service = null
  }]

  binding = [{
    condition = [{
      description = null
      expression  = null
      title       = null
    }]
    members = []
    role    = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "audit_config" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      audit_log_configs = set(object(
        {
          exempted_members = set(string)
          log_type         = string
        }
      ))
      service = string
    }
  ))
  default = []
}

variable "binding" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      condition = list(object(
        {
          description = string
          expression  = string
          title       = string
        }
      ))
      members = set(string)
      role    = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "google_iam_policy" "this" {

  dynamic "audit_config" {
    for_each = var.audit_config
    content {
      # service - (required) is a type of string
      service = audit_config.value["service"]

      dynamic "audit_log_configs" {
        for_each = audit_config.value.audit_log_configs
        content {
          # exempted_members - (optional) is a type of set of string
          exempted_members = audit_log_configs.value["exempted_members"]
          # log_type - (required) is a type of string
          log_type = audit_log_configs.value["log_type"]
        }
      }

    }
  }

  dynamic "binding" {
    for_each = var.binding
    content {
      # members - (required) is a type of set of string
      members = binding.value["members"]
      # role - (required) is a type of string
      role = binding.value["role"]

      dynamic "condition" {
        for_each = binding.value.condition
        content {
          # description - (optional) is a type of string
          description = condition.value["description"]
          # expression - (required) is a type of string
          expression = condition.value["expression"]
          # title - (required) is a type of string
          title = condition.value["title"]
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
  value       = data.google_iam_policy.this.id
}

output "policy_data" {
  description = "returns a string"
  value       = data.google_iam_policy.this.policy_data
}

output "this" {
  value = google_iam_policy.this
}
```

[top](#index)