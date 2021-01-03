# digitalocean_app

[back](../digitalocean.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    digitalocean = ">= 2.3.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "digitalocean_app" {
  source = "./modules/digitalocean/r/digitalocean_app"


  spec = [{
    database = [{
      cluster_name = null
      db_name      = null
      db_user      = null
      engine       = null
      name         = null
      production   = null
      version      = null
    }]
    domains = []
    name    = null
    region  = null
    service = [{
      build_command   = null
      dockerfile_path = null
      env = [{
        key   = null
        scope = null
        type  = null
        value = null
      }]
      environment_slug = null
      git = [{
        branch         = null
        repo_clone_url = null
      }]
      github = [{
        branch         = null
        deploy_on_push = null
        repo           = null
      }]
      health_check = [{
        failure_threshold     = null
        http_path             = null
        initial_delay_seconds = null
        period_seconds        = null
        success_threshold     = null
        timeout_seconds       = null
      }]
      http_port          = null
      instance_count     = null
      instance_size_slug = null
      name               = null
      routes = [{
        path = null
      }]
      run_command = null
      source_dir  = null
    }]
    static_site = [{
      build_command   = null
      dockerfile_path = null
      env = [{
        key   = null
        scope = null
        type  = null
        value = null
      }]
      environment_slug = null
      error_document   = null
      git = [{
        branch         = null
        repo_clone_url = null
      }]
      github = [{
        branch         = null
        deploy_on_push = null
        repo           = null
      }]
      index_document = null
      name           = null
      output_dir     = null
      routes = [{
        path = null
      }]
      source_dir = null
    }]
    worker = [{
      build_command   = null
      dockerfile_path = null
      env = [{
        key   = null
        scope = null
        type  = null
        value = null
      }]
      environment_slug = null
      git = [{
        branch         = null
        repo_clone_url = null
      }]
      github = [{
        branch         = null
        deploy_on_push = null
        repo           = null
      }]
      instance_count     = null
      instance_size_slug = null
      name               = null
      routes = [{
        path = null
      }]
      run_command = null
      source_dir  = null
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "spec" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      database = list(object(
        {
          cluster_name = string
          db_name      = string
          db_user      = string
          engine       = string
          name         = string
          production   = bool
          version      = string
        }
      ))
      domains = set(string)
      name    = string
      region  = string
      service = list(object(
        {
          build_command   = string
          dockerfile_path = string
          env = set(object(
            {
              key   = string
              scope = string
              type  = string
              value = string
            }
          ))
          environment_slug = string
          git = list(object(
            {
              branch         = string
              repo_clone_url = string
            }
          ))
          github = list(object(
            {
              branch         = string
              deploy_on_push = bool
              repo           = string
            }
          ))
          health_check = list(object(
            {
              failure_threshold     = number
              http_path             = string
              initial_delay_seconds = number
              period_seconds        = number
              success_threshold     = number
              timeout_seconds       = number
            }
          ))
          http_port          = number
          instance_count     = number
          instance_size_slug = string
          name               = string
          routes = list(object(
            {
              path = string
            }
          ))
          run_command = string
          source_dir  = string
        }
      ))
      static_site = list(object(
        {
          build_command   = string
          dockerfile_path = string
          env = set(object(
            {
              key   = string
              scope = string
              type  = string
              value = string
            }
          ))
          environment_slug = string
          error_document   = string
          git = list(object(
            {
              branch         = string
              repo_clone_url = string
            }
          ))
          github = list(object(
            {
              branch         = string
              deploy_on_push = bool
              repo           = string
            }
          ))
          index_document = string
          name           = string
          output_dir     = string
          routes = list(object(
            {
              path = string
            }
          ))
          source_dir = string
        }
      ))
      worker = list(object(
        {
          build_command   = string
          dockerfile_path = string
          env = set(object(
            {
              key   = string
              scope = string
              type  = string
              value = string
            }
          ))
          environment_slug = string
          git = list(object(
            {
              branch         = string
              repo_clone_url = string
            }
          ))
          github = list(object(
            {
              branch         = string
              deploy_on_push = bool
              repo           = string
            }
          ))
          instance_count     = number
          instance_size_slug = string
          name               = string
          routes = list(object(
            {
              path = string
            }
          ))
          run_command = string
          source_dir  = string
        }
      ))
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "digitalocean_app" "this" {

  dynamic "spec" {
    for_each = var.spec
    content {
      domains = spec.value["domains"]
      name    = spec.value["name"]
      region  = spec.value["region"]

      dynamic "database" {
        for_each = spec.value.database
        content {
          cluster_name = database.value["cluster_name"]
          db_name      = database.value["db_name"]
          db_user      = database.value["db_user"]
          engine       = database.value["engine"]
          name         = database.value["name"]
          production   = database.value["production"]
          version      = database.value["version"]
        }
      }

      dynamic "service" {
        for_each = spec.value.service
        content {
          build_command      = service.value["build_command"]
          dockerfile_path    = service.value["dockerfile_path"]
          environment_slug   = service.value["environment_slug"]
          http_port          = service.value["http_port"]
          instance_count     = service.value["instance_count"]
          instance_size_slug = service.value["instance_size_slug"]
          name               = service.value["name"]
          run_command        = service.value["run_command"]
          source_dir         = service.value["source_dir"]

          dynamic "env" {
            for_each = service.value.env
            content {
              key   = env.value["key"]
              scope = env.value["scope"]
              type  = env.value["type"]
              value = env.value["value"]
            }
          }

          dynamic "git" {
            for_each = service.value.git
            content {
              branch         = git.value["branch"]
              repo_clone_url = git.value["repo_clone_url"]
            }
          }

          dynamic "github" {
            for_each = service.value.github
            content {
              branch         = github.value["branch"]
              deploy_on_push = github.value["deploy_on_push"]
              repo           = github.value["repo"]
            }
          }

          dynamic "health_check" {
            for_each = service.value.health_check
            content {
              failure_threshold     = health_check.value["failure_threshold"]
              http_path             = health_check.value["http_path"]
              initial_delay_seconds = health_check.value["initial_delay_seconds"]
              period_seconds        = health_check.value["period_seconds"]
              success_threshold     = health_check.value["success_threshold"]
              timeout_seconds       = health_check.value["timeout_seconds"]
            }
          }

          dynamic "routes" {
            for_each = service.value.routes
            content {
              path = routes.value["path"]
            }
          }

        }
      }

      dynamic "static_site" {
        for_each = spec.value.static_site
        content {
          build_command    = static_site.value["build_command"]
          dockerfile_path  = static_site.value["dockerfile_path"]
          environment_slug = static_site.value["environment_slug"]
          error_document   = static_site.value["error_document"]
          index_document   = static_site.value["index_document"]
          name             = static_site.value["name"]
          output_dir       = static_site.value["output_dir"]
          source_dir       = static_site.value["source_dir"]

          dynamic "env" {
            for_each = static_site.value.env
            content {
              key   = env.value["key"]
              scope = env.value["scope"]
              type  = env.value["type"]
              value = env.value["value"]
            }
          }

          dynamic "git" {
            for_each = static_site.value.git
            content {
              branch         = git.value["branch"]
              repo_clone_url = git.value["repo_clone_url"]
            }
          }

          dynamic "github" {
            for_each = static_site.value.github
            content {
              branch         = github.value["branch"]
              deploy_on_push = github.value["deploy_on_push"]
              repo           = github.value["repo"]
            }
          }

          dynamic "routes" {
            for_each = static_site.value.routes
            content {
              path = routes.value["path"]
            }
          }

        }
      }

      dynamic "worker" {
        for_each = spec.value.worker
        content {
          build_command      = worker.value["build_command"]
          dockerfile_path    = worker.value["dockerfile_path"]
          environment_slug   = worker.value["environment_slug"]
          instance_count     = worker.value["instance_count"]
          instance_size_slug = worker.value["instance_size_slug"]
          name               = worker.value["name"]
          run_command        = worker.value["run_command"]
          source_dir         = worker.value["source_dir"]

          dynamic "env" {
            for_each = worker.value.env
            content {
              key   = env.value["key"]
              scope = env.value["scope"]
              type  = env.value["type"]
              value = env.value["value"]
            }
          }

          dynamic "git" {
            for_each = worker.value.git
            content {
              branch         = git.value["branch"]
              repo_clone_url = git.value["repo_clone_url"]
            }
          }

          dynamic "github" {
            for_each = worker.value.github
            content {
              branch         = github.value["branch"]
              deploy_on_push = github.value["deploy_on_push"]
              repo           = github.value["repo"]
            }
          }

          dynamic "routes" {
            for_each = worker.value.routes
            content {
              path = routes.value["path"]
            }
          }

        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "active_deployment_id" {
  description = "returns a string"
  value       = digitalocean_app.this.active_deployment_id
}

output "created_at" {
  description = "returns a string"
  value       = digitalocean_app.this.created_at
}

output "default_ingress" {
  description = "returns a string"
  value       = digitalocean_app.this.default_ingress
}

output "id" {
  description = "returns a string"
  value       = digitalocean_app.this.id
}

output "live_url" {
  description = "returns a string"
  value       = digitalocean_app.this.live_url
}

output "updated_at" {
  description = "returns a string"
  value       = digitalocean_app.this.updated_at
}

output "this" {
  value = digitalocean_app.this
}
```

[top](#index)