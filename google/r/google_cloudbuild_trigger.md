# google_cloudbuild_trigger

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    google = ">= 3.63.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_cloudbuild_trigger" {
  source = "./modules/google/r/google_cloudbuild_trigger"

  # description - (optional) is a type of string
  description = null
  # disabled - (optional) is a type of bool
  disabled = null
  # filename - (optional) is a type of string
  filename = null
  # ignored_files - (optional) is a type of list of string
  ignored_files = []
  # included_files - (optional) is a type of list of string
  included_files = []
  # name - (optional) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
  # substitutions - (optional) is a type of map of string
  substitutions = {}
  # tags - (optional) is a type of list of string
  tags = []

  build = [{
    artifacts = [{
      images = []
      objects = [{
        location = null
        paths    = []
        timing = [{
          end_time   = null
          start_time = null
        }]
      }]
    }]
    images      = []
    logs_bucket = null
    options = [{
      disk_size_gb            = null
      dynamic_substitutions   = null
      env                     = []
      log_streaming_option    = null
      logging                 = null
      machine_type            = null
      requested_verify_option = null
      secret_env              = []
      source_provenance_hash  = []
      substitution_option     = null
      volumes = [{
        name = null
        path = null
      }]
      worker_pool = null
    }]
    queue_ttl = null
    secret = [{
      kms_key_name = null
      secret_env   = {}
    }]
    source = [{
      repo_source = [{
        branch_name   = null
        commit_sha    = null
        dir           = null
        invert_regex  = null
        project_id    = null
        repo_name     = null
        substitutions = {}
        tag_name      = null
      }]
      storage_source = [{
        bucket     = null
        generation = null
        object     = null
      }]
    }]
    step = [{
      args       = []
      dir        = null
      entrypoint = null
      env        = []
      id         = null
      name       = null
      secret_env = []
      timeout    = null
      timing     = null
      volumes = [{
        name = null
        path = null
      }]
      wait_for = []
    }]
    substitutions = {}
    tags          = []
    timeout       = null
  }]

  github = [{
    name  = null
    owner = null
    pull_request = [{
      branch          = null
      comment_control = null
      invert_regex    = null
    }]
    push = [{
      branch       = null
      invert_regex = null
      tag          = null
    }]
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]

  trigger_template = [{
    branch_name  = null
    commit_sha   = null
    dir          = null
    invert_regex = null
    project_id   = null
    repo_name    = null
    tag_name     = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Human-readable description of the trigger."
  type        = string
  default     = null
}

variable "disabled" {
  description = "(optional) - Whether the trigger is disabled or not. If true, the trigger will never result in a build."
  type        = bool
  default     = null
}

variable "filename" {
  description = "(optional) - Path, from the source root, to a file whose contents is used for the template. Either a filename or build template must be provided."
  type        = string
  default     = null
}

variable "ignored_files" {
  description = "(optional) - ignoredFiles and includedFiles are file glob matches using https://golang.org/pkg/path/filepath/#Match\nextended with support for '**'.\n\nIf ignoredFiles and changed files are both empty, then they are not\nused to determine whether or not to trigger a build.\n\nIf ignoredFiles is not empty, then we ignore any files that match any\nof the ignored_file globs. If the change has no files that are outside\nof the ignoredFiles globs, then we do not trigger a build."
  type        = list(string)
  default     = null
}

variable "included_files" {
  description = "(optional) - ignoredFiles and includedFiles are file glob matches using https://golang.org/pkg/path/filepath/#Match\nextended with support for '**'.\n\nIf any of the files altered in the commit pass the ignoredFiles filter\nand includedFiles is empty, then as far as this filter is concerned, we\nshould trigger the build.\n\nIf any of the files altered in the commit pass the ignoredFiles filter\nand includedFiles is not empty, then we make sure that at least one of\nthose files matches a includedFiles glob. If not, then we do not trigger\na build."
  type        = list(string)
  default     = null
}

variable "name" {
  description = "(optional) - Name of the trigger. Must be unique within the project."
  type        = string
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "substitutions" {
  description = "(optional) - Substitutions data for Build resource."
  type        = map(string)
  default     = null
}

variable "tags" {
  description = "(optional) - Tags for annotation of a BuildTrigger"
  type        = list(string)
  default     = null
}

variable "build" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      artifacts = list(object(
        {
          images = list(string)
          objects = list(object(
            {
              location = string
              paths    = list(string)
              timing = list(object(
                {
                  end_time   = string
                  start_time = string
                }
              ))
            }
          ))
        }
      ))
      images      = list(string)
      logs_bucket = string
      options = list(object(
        {
          disk_size_gb            = number
          dynamic_substitutions   = bool
          env                     = list(string)
          log_streaming_option    = string
          logging                 = string
          machine_type            = string
          requested_verify_option = string
          secret_env              = list(string)
          source_provenance_hash  = list(string)
          substitution_option     = string
          volumes = list(object(
            {
              name = string
              path = string
            }
          ))
          worker_pool = string
        }
      ))
      queue_ttl = string
      secret = list(object(
        {
          kms_key_name = string
          secret_env   = map(string)
        }
      ))
      source = list(object(
        {
          repo_source = list(object(
            {
              branch_name   = string
              commit_sha    = string
              dir           = string
              invert_regex  = bool
              project_id    = string
              repo_name     = string
              substitutions = map(string)
              tag_name      = string
            }
          ))
          storage_source = list(object(
            {
              bucket     = string
              generation = string
              object     = string
            }
          ))
        }
      ))
      step = list(object(
        {
          args       = list(string)
          dir        = string
          entrypoint = string
          env        = list(string)
          id         = string
          name       = string
          secret_env = list(string)
          timeout    = string
          timing     = string
          volumes = list(object(
            {
              name = string
              path = string
            }
          ))
          wait_for = list(string)
        }
      ))
      substitutions = map(string)
      tags          = list(string)
      timeout       = string
    }
  ))
  default = []
}

variable "github" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      name  = string
      owner = string
      pull_request = list(object(
        {
          branch          = string
          comment_control = string
          invert_regex    = bool
        }
      ))
      push = list(object(
        {
          branch       = string
          invert_regex = bool
          tag          = string
        }
      ))
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

variable "trigger_template" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      branch_name  = string
      commit_sha   = string
      dir          = string
      invert_regex = bool
      project_id   = string
      repo_name    = string
      tag_name     = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "google_cloudbuild_trigger" "this" {
  description    = var.description
  disabled       = var.disabled
  filename       = var.filename
  ignored_files  = var.ignored_files
  included_files = var.included_files
  name           = var.name
  project        = var.project
  substitutions  = var.substitutions
  tags           = var.tags

  dynamic "build" {
    for_each = var.build
    content {
      images        = build.value["images"]
      logs_bucket   = build.value["logs_bucket"]
      queue_ttl     = build.value["queue_ttl"]
      substitutions = build.value["substitutions"]
      tags          = build.value["tags"]
      timeout       = build.value["timeout"]

      dynamic "artifacts" {
        for_each = build.value.artifacts
        content {
          images = artifacts.value["images"]

          dynamic "objects" {
            for_each = artifacts.value.objects
            content {
              location = objects.value["location"]
              paths    = objects.value["paths"]
            }
          }

        }
      }

      dynamic "options" {
        for_each = build.value.options
        content {
          disk_size_gb            = options.value["disk_size_gb"]
          dynamic_substitutions   = options.value["dynamic_substitutions"]
          env                     = options.value["env"]
          log_streaming_option    = options.value["log_streaming_option"]
          logging                 = options.value["logging"]
          machine_type            = options.value["machine_type"]
          requested_verify_option = options.value["requested_verify_option"]
          secret_env              = options.value["secret_env"]
          source_provenance_hash  = options.value["source_provenance_hash"]
          substitution_option     = options.value["substitution_option"]
          worker_pool             = options.value["worker_pool"]

          dynamic "volumes" {
            for_each = options.value.volumes
            content {
              name = volumes.value["name"]
              path = volumes.value["path"]
            }
          }

        }
      }

      dynamic "secret" {
        for_each = build.value.secret
        content {
          kms_key_name = secret.value["kms_key_name"]
          secret_env   = secret.value["secret_env"]
        }
      }

      dynamic "source" {
        for_each = build.value.source
        content {

          dynamic "repo_source" {
            for_each = source.value.repo_source
            content {
              branch_name   = repo_source.value["branch_name"]
              commit_sha    = repo_source.value["commit_sha"]
              dir           = repo_source.value["dir"]
              invert_regex  = repo_source.value["invert_regex"]
              project_id    = repo_source.value["project_id"]
              repo_name     = repo_source.value["repo_name"]
              substitutions = repo_source.value["substitutions"]
              tag_name      = repo_source.value["tag_name"]
            }
          }

          dynamic "storage_source" {
            for_each = source.value.storage_source
            content {
              bucket     = storage_source.value["bucket"]
              generation = storage_source.value["generation"]
              object     = storage_source.value["object"]
            }
          }

        }
      }

      dynamic "step" {
        for_each = build.value.step
        content {
          args       = step.value["args"]
          dir        = step.value["dir"]
          entrypoint = step.value["entrypoint"]
          env        = step.value["env"]
          id         = step.value["id"]
          name       = step.value["name"]
          secret_env = step.value["secret_env"]
          timeout    = step.value["timeout"]
          timing     = step.value["timing"]
          wait_for   = step.value["wait_for"]

          dynamic "volumes" {
            for_each = step.value.volumes
            content {
              name = volumes.value["name"]
              path = volumes.value["path"]
            }
          }

        }
      }

    }
  }

  dynamic "github" {
    for_each = var.github
    content {
      name  = github.value["name"]
      owner = github.value["owner"]

      dynamic "pull_request" {
        for_each = github.value.pull_request
        content {
          branch          = pull_request.value["branch"]
          comment_control = pull_request.value["comment_control"]
          invert_regex    = pull_request.value["invert_regex"]
        }
      }

      dynamic "push" {
        for_each = github.value.push
        content {
          branch       = push.value["branch"]
          invert_regex = push.value["invert_regex"]
          tag          = push.value["tag"]
        }
      }

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

  dynamic "trigger_template" {
    for_each = var.trigger_template
    content {
      branch_name  = trigger_template.value["branch_name"]
      commit_sha   = trigger_template.value["commit_sha"]
      dir          = trigger_template.value["dir"]
      invert_regex = trigger_template.value["invert_regex"]
      project_id   = trigger_template.value["project_id"]
      repo_name    = trigger_template.value["repo_name"]
      tag_name     = trigger_template.value["tag_name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "create_time" {
  description = "returns a string"
  value       = google_cloudbuild_trigger.this.create_time
}

output "id" {
  description = "returns a string"
  value       = google_cloudbuild_trigger.this.id
}

output "name" {
  description = "returns a string"
  value       = google_cloudbuild_trigger.this.name
}

output "project" {
  description = "returns a string"
  value       = google_cloudbuild_trigger.this.project
}

output "trigger_id" {
  description = "returns a string"
  value       = google_cloudbuild_trigger.this.trigger_id
}

output "this" {
  value = google_cloudbuild_trigger.this
}
```

[top](#index)