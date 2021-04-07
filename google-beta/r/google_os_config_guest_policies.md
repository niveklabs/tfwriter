# google_os_config_guest_policies

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
module "google_os_config_guest_policies" {
  source = "./modules/google-beta/r/google_os_config_guest_policies"

  # description - (optional) is a type of string
  description = null
  # etag - (optional) is a type of string
  etag = null
  # guest_policy_id - (required) is a type of string
  guest_policy_id = null
  # project - (optional) is a type of string
  project = null

  assignment = [{
    group_labels = [{
      labels = {}
    }]
    instance_name_prefixes = []
    instances              = []
    os_types = [{
      os_architecture = null
      os_short_name   = null
      os_version      = null
    }]
    zones = []
  }]

  package_repositories = [{
    apt = [{
      archive_type = null
      components   = []
      distribution = null
      gpg_key      = null
      uri          = null
    }]
    goo = [{
      name = null
      url  = null
    }]
    yum = [{
      base_url     = null
      display_name = null
      gpg_keys     = []
      id           = null
    }]
    zypper = [{
      base_url     = null
      display_name = null
      gpg_keys     = []
      id           = null
    }]
  }]

  packages = [{
    desired_state = null
    manager       = null
    name          = null
  }]

  recipes = [{
    artifacts = [{
      allow_insecure = null
      gcs = [{
        bucket     = null
        generation = null
        object     = null
      }]
      id = null
      remote = [{
        check_sum = null
        uri       = null
      }]
    }]
    desired_state = null
    install_steps = [{
      archive_extraction = [{
        artifact_id = null
        destination = null
        type        = null
      }]
      dpkg_installation = [{
        artifact_id = null
      }]
      file_copy = [{
        artifact_id = null
        destination = null
        overwrite   = null
        permissions = null
      }]
      file_exec = [{
        allowed_exit_codes = null
        args               = []
        artifact_id        = null
        local_path         = null
      }]
      msi_installation = [{
        allowed_exit_codes = []
        artifact_id        = null
        flags              = []
      }]
      rpm_installation = [{
        artifact_id = null
      }]
      script_run = [{
        allowed_exit_codes = []
        interpreter        = null
        script             = null
      }]
    }]
    name = null
    update_steps = [{
      archive_extraction = [{
        artifact_id = null
        destination = null
        type        = null
      }]
      dpkg_installation = [{
        artifact_id = null
      }]
      file_copy = [{
        artifact_id = null
        destination = null
        overwrite   = null
        permissions = null
      }]
      file_exec = [{
        allowed_exit_codes = []
        args               = []
        artifact_id        = null
        local_path         = null
      }]
      msi_installation = [{
        allowed_exit_codes = []
        artifact_id        = null
        flags              = []
      }]
      rpm_installation = [{
        artifact_id = null
      }]
      script_run = [{
        allowed_exit_codes = []
        interpreter        = null
        script             = null
      }]
    }]
    version = null
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
variable "description" {
  description = "(optional) - Description of the guest policy. Length of the description is limited to 1024 characters."
  type        = string
  default     = null
}

variable "etag" {
  description = "(optional) - The etag for this guest policy. If this is provided on update, it must match the server's etag."
  type        = string
  default     = null
}

variable "guest_policy_id" {
  description = "(required) - The logical name of the guest policy in the project with the following restrictions:\n* Must contain only lowercase letters, numbers, and hyphens.\n* Must start with a letter.\n* Must be between 1-63 characters.\n* Must end with a number or a letter.\n* Must be unique within the project."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "assignment" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      group_labels = list(object(
        {
          labels = map(string)
        }
      ))
      instance_name_prefixes = list(string)
      instances              = list(string)
      os_types = list(object(
        {
          os_architecture = string
          os_short_name   = string
          os_version      = string
        }
      ))
      zones = list(string)
    }
  ))
}

variable "package_repositories" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      apt = list(object(
        {
          archive_type = string
          components   = list(string)
          distribution = string
          gpg_key      = string
          uri          = string
        }
      ))
      goo = list(object(
        {
          name = string
          url  = string
        }
      ))
      yum = list(object(
        {
          base_url     = string
          display_name = string
          gpg_keys     = list(string)
          id           = string
        }
      ))
      zypper = list(object(
        {
          base_url     = string
          display_name = string
          gpg_keys     = list(string)
          id           = string
        }
      ))
    }
  ))
  default = []
}

variable "packages" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      desired_state = string
      manager       = string
      name          = string
    }
  ))
  default = []
}

variable "recipes" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      artifacts = list(object(
        {
          allow_insecure = bool
          gcs = list(object(
            {
              bucket     = string
              generation = number
              object     = string
            }
          ))
          id = string
          remote = list(object(
            {
              check_sum = string
              uri       = string
            }
          ))
        }
      ))
      desired_state = string
      install_steps = list(object(
        {
          archive_extraction = list(object(
            {
              artifact_id = string
              destination = string
              type        = string
            }
          ))
          dpkg_installation = list(object(
            {
              artifact_id = string
            }
          ))
          file_copy = list(object(
            {
              artifact_id = string
              destination = string
              overwrite   = bool
              permissions = string
            }
          ))
          file_exec = list(object(
            {
              allowed_exit_codes = string
              args               = list(string)
              artifact_id        = string
              local_path         = string
            }
          ))
          msi_installation = list(object(
            {
              allowed_exit_codes = list(number)
              artifact_id        = string
              flags              = list(string)
            }
          ))
          rpm_installation = list(object(
            {
              artifact_id = string
            }
          ))
          script_run = list(object(
            {
              allowed_exit_codes = list(number)
              interpreter        = string
              script             = string
            }
          ))
        }
      ))
      name = string
      update_steps = list(object(
        {
          archive_extraction = list(object(
            {
              artifact_id = string
              destination = string
              type        = string
            }
          ))
          dpkg_installation = list(object(
            {
              artifact_id = string
            }
          ))
          file_copy = list(object(
            {
              artifact_id = string
              destination = string
              overwrite   = bool
              permissions = string
            }
          ))
          file_exec = list(object(
            {
              allowed_exit_codes = list(number)
              args               = list(string)
              artifact_id        = string
              local_path         = string
            }
          ))
          msi_installation = list(object(
            {
              allowed_exit_codes = list(number)
              artifact_id        = string
              flags              = list(string)
            }
          ))
          rpm_installation = list(object(
            {
              artifact_id = string
            }
          ))
          script_run = list(object(
            {
              allowed_exit_codes = list(number)
              interpreter        = string
              script             = string
            }
          ))
        }
      ))
      version = string
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
resource "google_os_config_guest_policies" "this" {
  # description - (optional) is a type of string
  description = var.description
  # etag - (optional) is a type of string
  etag = var.etag
  # guest_policy_id - (required) is a type of string
  guest_policy_id = var.guest_policy_id
  # project - (optional) is a type of string
  project = var.project

  dynamic "assignment" {
    for_each = var.assignment
    content {
      # instance_name_prefixes - (optional) is a type of list of string
      instance_name_prefixes = assignment.value["instance_name_prefixes"]
      # instances - (optional) is a type of list of string
      instances = assignment.value["instances"]
      # zones - (optional) is a type of list of string
      zones = assignment.value["zones"]

      dynamic "group_labels" {
        for_each = assignment.value.group_labels
        content {
          # labels - (required) is a type of map of string
          labels = group_labels.value["labels"]
        }
      }

      dynamic "os_types" {
        for_each = assignment.value.os_types
        content {
          # os_architecture - (optional) is a type of string
          os_architecture = os_types.value["os_architecture"]
          # os_short_name - (optional) is a type of string
          os_short_name = os_types.value["os_short_name"]
          # os_version - (optional) is a type of string
          os_version = os_types.value["os_version"]
        }
      }

    }
  }

  dynamic "package_repositories" {
    for_each = var.package_repositories
    content {

      dynamic "apt" {
        for_each = package_repositories.value.apt
        content {
          # archive_type - (optional) is a type of string
          archive_type = apt.value["archive_type"]
          # components - (required) is a type of list of string
          components = apt.value["components"]
          # distribution - (required) is a type of string
          distribution = apt.value["distribution"]
          # gpg_key - (optional) is a type of string
          gpg_key = apt.value["gpg_key"]
          # uri - (required) is a type of string
          uri = apt.value["uri"]
        }
      }

      dynamic "goo" {
        for_each = package_repositories.value.goo
        content {
          # name - (required) is a type of string
          name = goo.value["name"]
          # url - (required) is a type of string
          url = goo.value["url"]
        }
      }

      dynamic "yum" {
        for_each = package_repositories.value.yum
        content {
          # base_url - (required) is a type of string
          base_url = yum.value["base_url"]
          # display_name - (optional) is a type of string
          display_name = yum.value["display_name"]
          # gpg_keys - (optional) is a type of list of string
          gpg_keys = yum.value["gpg_keys"]
          # id - (required) is a type of string
          id = yum.value["id"]
        }
      }

      dynamic "zypper" {
        for_each = package_repositories.value.zypper
        content {
          # base_url - (required) is a type of string
          base_url = zypper.value["base_url"]
          # display_name - (optional) is a type of string
          display_name = zypper.value["display_name"]
          # gpg_keys - (optional) is a type of list of string
          gpg_keys = zypper.value["gpg_keys"]
          # id - (required) is a type of string
          id = zypper.value["id"]
        }
      }

    }
  }

  dynamic "packages" {
    for_each = var.packages
    content {
      # desired_state - (optional) is a type of string
      desired_state = packages.value["desired_state"]
      # manager - (optional) is a type of string
      manager = packages.value["manager"]
      # name - (required) is a type of string
      name = packages.value["name"]
    }
  }

  dynamic "recipes" {
    for_each = var.recipes
    content {
      # desired_state - (optional) is a type of string
      desired_state = recipes.value["desired_state"]
      # name - (required) is a type of string
      name = recipes.value["name"]
      # version - (optional) is a type of string
      version = recipes.value["version"]

      dynamic "artifacts" {
        for_each = recipes.value.artifacts
        content {
          # allow_insecure - (optional) is a type of bool
          allow_insecure = artifacts.value["allow_insecure"]
          # id - (required) is a type of string
          id = artifacts.value["id"]

          dynamic "gcs" {
            for_each = artifacts.value.gcs
            content {
              # bucket - (optional) is a type of string
              bucket = gcs.value["bucket"]
              # generation - (optional) is a type of number
              generation = gcs.value["generation"]
              # object - (optional) is a type of string
              object = gcs.value["object"]
            }
          }

          dynamic "remote" {
            for_each = artifacts.value.remote
            content {
              # check_sum - (optional) is a type of string
              check_sum = remote.value["check_sum"]
              # uri - (optional) is a type of string
              uri = remote.value["uri"]
            }
          }

        }
      }

      dynamic "install_steps" {
        for_each = recipes.value.install_steps
        content {

          dynamic "archive_extraction" {
            for_each = install_steps.value.archive_extraction
            content {
              # artifact_id - (required) is a type of string
              artifact_id = archive_extraction.value["artifact_id"]
              # destination - (optional) is a type of string
              destination = archive_extraction.value["destination"]
              # type - (required) is a type of string
              type = archive_extraction.value["type"]
            }
          }

          dynamic "dpkg_installation" {
            for_each = install_steps.value.dpkg_installation
            content {
              # artifact_id - (required) is a type of string
              artifact_id = dpkg_installation.value["artifact_id"]
            }
          }

          dynamic "file_copy" {
            for_each = install_steps.value.file_copy
            content {
              # artifact_id - (required) is a type of string
              artifact_id = file_copy.value["artifact_id"]
              # destination - (required) is a type of string
              destination = file_copy.value["destination"]
              # overwrite - (optional) is a type of bool
              overwrite = file_copy.value["overwrite"]
              # permissions - (optional) is a type of string
              permissions = file_copy.value["permissions"]
            }
          }

          dynamic "file_exec" {
            for_each = install_steps.value.file_exec
            content {
              # allowed_exit_codes - (optional) is a type of string
              allowed_exit_codes = file_exec.value["allowed_exit_codes"]
              # args - (optional) is a type of list of string
              args = file_exec.value["args"]
              # artifact_id - (optional) is a type of string
              artifact_id = file_exec.value["artifact_id"]
              # local_path - (optional) is a type of string
              local_path = file_exec.value["local_path"]
            }
          }

          dynamic "msi_installation" {
            for_each = install_steps.value.msi_installation
            content {
              # allowed_exit_codes - (optional) is a type of list of number
              allowed_exit_codes = msi_installation.value["allowed_exit_codes"]
              # artifact_id - (required) is a type of string
              artifact_id = msi_installation.value["artifact_id"]
              # flags - (optional) is a type of list of string
              flags = msi_installation.value["flags"]
            }
          }

          dynamic "rpm_installation" {
            for_each = install_steps.value.rpm_installation
            content {
              # artifact_id - (required) is a type of string
              artifact_id = rpm_installation.value["artifact_id"]
            }
          }

          dynamic "script_run" {
            for_each = install_steps.value.script_run
            content {
              # allowed_exit_codes - (optional) is a type of list of number
              allowed_exit_codes = script_run.value["allowed_exit_codes"]
              # interpreter - (optional) is a type of string
              interpreter = script_run.value["interpreter"]
              # script - (required) is a type of string
              script = script_run.value["script"]
            }
          }

        }
      }

      dynamic "update_steps" {
        for_each = recipes.value.update_steps
        content {

          dynamic "archive_extraction" {
            for_each = update_steps.value.archive_extraction
            content {
              # artifact_id - (required) is a type of string
              artifact_id = archive_extraction.value["artifact_id"]
              # destination - (optional) is a type of string
              destination = archive_extraction.value["destination"]
              # type - (required) is a type of string
              type = archive_extraction.value["type"]
            }
          }

          dynamic "dpkg_installation" {
            for_each = update_steps.value.dpkg_installation
            content {
              # artifact_id - (required) is a type of string
              artifact_id = dpkg_installation.value["artifact_id"]
            }
          }

          dynamic "file_copy" {
            for_each = update_steps.value.file_copy
            content {
              # artifact_id - (required) is a type of string
              artifact_id = file_copy.value["artifact_id"]
              # destination - (required) is a type of string
              destination = file_copy.value["destination"]
              # overwrite - (optional) is a type of bool
              overwrite = file_copy.value["overwrite"]
              # permissions - (optional) is a type of string
              permissions = file_copy.value["permissions"]
            }
          }

          dynamic "file_exec" {
            for_each = update_steps.value.file_exec
            content {
              # allowed_exit_codes - (optional) is a type of list of number
              allowed_exit_codes = file_exec.value["allowed_exit_codes"]
              # args - (optional) is a type of list of string
              args = file_exec.value["args"]
              # artifact_id - (optional) is a type of string
              artifact_id = file_exec.value["artifact_id"]
              # local_path - (optional) is a type of string
              local_path = file_exec.value["local_path"]
            }
          }

          dynamic "msi_installation" {
            for_each = update_steps.value.msi_installation
            content {
              # allowed_exit_codes - (optional) is a type of list of number
              allowed_exit_codes = msi_installation.value["allowed_exit_codes"]
              # artifact_id - (required) is a type of string
              artifact_id = msi_installation.value["artifact_id"]
              # flags - (optional) is a type of list of string
              flags = msi_installation.value["flags"]
            }
          }

          dynamic "rpm_installation" {
            for_each = update_steps.value.rpm_installation
            content {
              # artifact_id - (required) is a type of string
              artifact_id = rpm_installation.value["artifact_id"]
            }
          }

          dynamic "script_run" {
            for_each = update_steps.value.script_run
            content {
              # allowed_exit_codes - (optional) is a type of list of number
              allowed_exit_codes = script_run.value["allowed_exit_codes"]
              # interpreter - (optional) is a type of string
              interpreter = script_run.value["interpreter"]
              # script - (required) is a type of string
              script = script_run.value["script"]
            }
          }

        }
      }

    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "create_time" {
  description = "returns a string"
  value       = google_os_config_guest_policies.this.create_time
}

output "etag" {
  description = "returns a string"
  value       = google_os_config_guest_policies.this.etag
}

output "id" {
  description = "returns a string"
  value       = google_os_config_guest_policies.this.id
}

output "name" {
  description = "returns a string"
  value       = google_os_config_guest_policies.this.name
}

output "project" {
  description = "returns a string"
  value       = google_os_config_guest_policies.this.project
}

output "update_time" {
  description = "returns a string"
  value       = google_os_config_guest_policies.this.update_time
}

output "this" {
  value = google_os_config_guest_policies.this
}
```

[top](#index)