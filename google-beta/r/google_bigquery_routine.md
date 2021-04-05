# google_bigquery_routine

[back](../google-beta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "google_bigquery_routine" {
  source = "./modules/google-beta/r/google_bigquery_routine"

  # dataset_id - (required) is a type of string
  dataset_id = null
  # definition_body - (required) is a type of string
  definition_body = null
  # description - (optional) is a type of string
  description = null
  # determinism_level - (optional) is a type of string
  determinism_level = null
  # imported_libraries - (optional) is a type of list of string
  imported_libraries = []
  # language - (optional) is a type of string
  language = null
  # project - (optional) is a type of string
  project = null
  # return_type - (optional) is a type of string
  return_type = null
  # routine_id - (required) is a type of string
  routine_id = null
  # routine_type - (optional) is a type of string
  routine_type = null

  arguments = [{
    argument_kind = null
    data_type     = null
    mode          = null
    name          = null
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "dataset_id" {
  description = "(required) - The ID of the dataset containing this routine"
  type        = string
}

variable "definition_body" {
  description = "(required) - The body of the routine. For functions, this is the expression in the AS clause.\nIf language=SQL, it is the substring inside (but excluding) the parentheses."
  type        = string
}

variable "description" {
  description = "(optional) - The description of the routine if defined."
  type        = string
  default     = null
}

variable "determinism_level" {
  description = "(optional) - The determinism level of the JavaScript UDF if defined. Possible values: [\"DETERMINISM_LEVEL_UNSPECIFIED\", \"DETERMINISTIC\", \"NOT_DETERMINISTIC\"]"
  type        = string
  default     = null
}

variable "imported_libraries" {
  description = "(optional) - Optional. If language = \"JAVASCRIPT\", this field stores the path of the\nimported JAVASCRIPT libraries."
  type        = list(string)
  default     = null
}

variable "language" {
  description = "(optional) - The language of the routine. Possible values: [\"SQL\", \"JAVASCRIPT\"]"
  type        = string
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "return_type" {
  description = "(optional) - A JSON schema for the return type. Optional if language = \"SQL\"; required otherwise.\nIf absent, the return type is inferred from definitionBody at query time in each query\nthat references this routine. If present, then the evaluated result will be cast to\nthe specified returned type at query time. ~>**NOTE**: Because this field expects a JSON\nstring, any changes to the string will create a diff, even if the JSON itself hasn't\nchanged. If the API returns a different value for the same schema, e.g. it switche\nd the order of values or replaced STRUCT field type with RECORD field type, we currently\ncannot suppress the recurring diff this causes. As a workaround, we recommend using\nthe schema as returned by the API."
  type        = string
  default     = null
}

variable "routine_id" {
  description = "(required) - The ID of the the routine. The ID must contain only letters (a-z, A-Z), numbers (0-9), or underscores (_). The maximum length is 256 characters."
  type        = string
}

variable "routine_type" {
  description = "(optional) - The type of routine. Possible values: [\"SCALAR_FUNCTION\", \"PROCEDURE\"]"
  type        = string
  default     = null
}

variable "arguments" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      argument_kind = string
      data_type     = string
      mode          = string
      name          = string
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "google_bigquery_routine" "this" {
  dataset_id         = var.dataset_id
  definition_body    = var.definition_body
  description        = var.description
  determinism_level  = var.determinism_level
  imported_libraries = var.imported_libraries
  language           = var.language
  project            = var.project
  return_type        = var.return_type
  routine_id         = var.routine_id
  routine_type       = var.routine_type

  dynamic "arguments" {
    for_each = var.arguments
    content {
      argument_kind = arguments.value["argument_kind"]
      data_type     = arguments.value["data_type"]
      mode          = arguments.value["mode"]
      name          = arguments.value["name"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "creation_time" {
  description = "returns a number"
  value       = google_bigquery_routine.this.creation_time
}

output "id" {
  description = "returns a string"
  value       = google_bigquery_routine.this.id
}

output "last_modified_time" {
  description = "returns a number"
  value       = google_bigquery_routine.this.last_modified_time
}

output "project" {
  description = "returns a string"
  value       = google_bigquery_routine.this.project
}

output "this" {
  value = google_bigquery_routine.this
}
```

[top](#index)