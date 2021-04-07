# google_dataproc_job

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
module "google_dataproc_job" {
  source = "./modules/google-beta/r/google_dataproc_job"

  # force_delete - (optional) is a type of bool
  force_delete = null
  # labels - (optional) is a type of map of string
  labels = {}
  # project - (optional) is a type of string
  project = null
  # region - (optional) is a type of string
  region = null

  hadoop_config = [{
    archive_uris  = []
    args          = []
    file_uris     = []
    jar_file_uris = []
    logging_config = [{
      driver_log_levels = {}
    }]
    main_class        = null
    main_jar_file_uri = null
    properties        = {}
  }]

  hive_config = [{
    continue_on_failure = null
    jar_file_uris       = []
    properties          = {}
    query_file_uri      = null
    query_list          = []
    script_variables    = {}
  }]

  pig_config = [{
    continue_on_failure = null
    jar_file_uris       = []
    logging_config = [{
      driver_log_levels = {}
    }]
    properties       = {}
    query_file_uri   = null
    query_list       = []
    script_variables = {}
  }]

  placement = [{
    cluster_name = null
    cluster_uuid = null
  }]

  pyspark_config = [{
    archive_uris  = []
    args          = []
    file_uris     = []
    jar_file_uris = []
    logging_config = [{
      driver_log_levels = {}
    }]
    main_python_file_uri = null
    properties           = {}
    python_file_uris     = []
  }]

  reference = [{
    job_id = null
  }]

  scheduling = [{
    max_failures_per_hour = null
    max_failures_total    = null
  }]

  spark_config = [{
    archive_uris  = []
    args          = []
    file_uris     = []
    jar_file_uris = []
    logging_config = [{
      driver_log_levels = {}
    }]
    main_class        = null
    main_jar_file_uri = null
    properties        = {}
  }]

  sparksql_config = [{
    jar_file_uris = []
    logging_config = [{
      driver_log_levels = {}
    }]
    properties       = {}
    query_file_uri   = null
    query_list       = []
    script_variables = {}
  }]

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "force_delete" {
  description = "(optional) - By default, you can only delete inactive jobs within Dataproc. Setting this to true, and calling destroy, will ensure that the job is first cancelled before issuing the delete."
  type        = bool
  default     = null
}

variable "labels" {
  description = "(optional) - Optional. The labels to associate with this job."
  type        = map(string)
  default     = null
}

variable "project" {
  description = "(optional) - The project in which the cluster can be found and jobs subsequently run against. If it is not provided, the provider project is used."
  type        = string
  default     = null
}

variable "region" {
  description = "(optional) - The Cloud Dataproc region. This essentially determines which clusters are available for this job to be submitted to. If not specified, defaults to global."
  type        = string
  default     = null
}

variable "hadoop_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      archive_uris  = list(string)
      args          = list(string)
      file_uris     = list(string)
      jar_file_uris = list(string)
      logging_config = list(object(
        {
          driver_log_levels = map(string)
        }
      ))
      main_class        = string
      main_jar_file_uri = string
      properties        = map(string)
    }
  ))
  default = []
}

variable "hive_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      continue_on_failure = bool
      jar_file_uris       = list(string)
      properties          = map(string)
      query_file_uri      = string
      query_list          = list(string)
      script_variables    = map(string)
    }
  ))
  default = []
}

variable "pig_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      continue_on_failure = bool
      jar_file_uris       = list(string)
      logging_config = list(object(
        {
          driver_log_levels = map(string)
        }
      ))
      properties       = map(string)
      query_file_uri   = string
      query_list       = list(string)
      script_variables = map(string)
    }
  ))
  default = []
}

variable "placement" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      cluster_name = string
      cluster_uuid = string
    }
  ))
}

variable "pyspark_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      archive_uris  = list(string)
      args          = list(string)
      file_uris     = list(string)
      jar_file_uris = list(string)
      logging_config = list(object(
        {
          driver_log_levels = map(string)
        }
      ))
      main_python_file_uri = string
      properties           = map(string)
      python_file_uris     = list(string)
    }
  ))
  default = []
}

variable "reference" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      job_id = string
    }
  ))
  default = []
}

variable "scheduling" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      max_failures_per_hour = number
      max_failures_total    = number
    }
  ))
  default = []
}

variable "spark_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      archive_uris  = list(string)
      args          = list(string)
      file_uris     = list(string)
      jar_file_uris = list(string)
      logging_config = list(object(
        {
          driver_log_levels = map(string)
        }
      ))
      main_class        = string
      main_jar_file_uri = string
      properties        = map(string)
    }
  ))
  default = []
}

variable "sparksql_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      jar_file_uris = list(string)
      logging_config = list(object(
        {
          driver_log_levels = map(string)
        }
      ))
      properties       = map(string)
      query_file_uri   = string
      query_list       = list(string)
      script_variables = map(string)
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
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "google_dataproc_job" "this" {
  # force_delete - (optional) is a type of bool
  force_delete = var.force_delete
  # labels - (optional) is a type of map of string
  labels = var.labels
  # project - (optional) is a type of string
  project = var.project
  # region - (optional) is a type of string
  region = var.region

  dynamic "hadoop_config" {
    for_each = var.hadoop_config
    content {
      # archive_uris - (optional) is a type of list of string
      archive_uris = hadoop_config.value["archive_uris"]
      # args - (optional) is a type of list of string
      args = hadoop_config.value["args"]
      # file_uris - (optional) is a type of list of string
      file_uris = hadoop_config.value["file_uris"]
      # jar_file_uris - (optional) is a type of list of string
      jar_file_uris = hadoop_config.value["jar_file_uris"]
      # main_class - (optional) is a type of string
      main_class = hadoop_config.value["main_class"]
      # main_jar_file_uri - (optional) is a type of string
      main_jar_file_uri = hadoop_config.value["main_jar_file_uri"]
      # properties - (optional) is a type of map of string
      properties = hadoop_config.value["properties"]

      dynamic "logging_config" {
        for_each = hadoop_config.value.logging_config
        content {
          # driver_log_levels - (required) is a type of map of string
          driver_log_levels = logging_config.value["driver_log_levels"]
        }
      }

    }
  }

  dynamic "hive_config" {
    for_each = var.hive_config
    content {
      # continue_on_failure - (optional) is a type of bool
      continue_on_failure = hive_config.value["continue_on_failure"]
      # jar_file_uris - (optional) is a type of list of string
      jar_file_uris = hive_config.value["jar_file_uris"]
      # properties - (optional) is a type of map of string
      properties = hive_config.value["properties"]
      # query_file_uri - (optional) is a type of string
      query_file_uri = hive_config.value["query_file_uri"]
      # query_list - (optional) is a type of list of string
      query_list = hive_config.value["query_list"]
      # script_variables - (optional) is a type of map of string
      script_variables = hive_config.value["script_variables"]
    }
  }

  dynamic "pig_config" {
    for_each = var.pig_config
    content {
      # continue_on_failure - (optional) is a type of bool
      continue_on_failure = pig_config.value["continue_on_failure"]
      # jar_file_uris - (optional) is a type of list of string
      jar_file_uris = pig_config.value["jar_file_uris"]
      # properties - (optional) is a type of map of string
      properties = pig_config.value["properties"]
      # query_file_uri - (optional) is a type of string
      query_file_uri = pig_config.value["query_file_uri"]
      # query_list - (optional) is a type of list of string
      query_list = pig_config.value["query_list"]
      # script_variables - (optional) is a type of map of string
      script_variables = pig_config.value["script_variables"]

      dynamic "logging_config" {
        for_each = pig_config.value.logging_config
        content {
          # driver_log_levels - (required) is a type of map of string
          driver_log_levels = logging_config.value["driver_log_levels"]
        }
      }

    }
  }

  dynamic "placement" {
    for_each = var.placement
    content {
      # cluster_name - (required) is a type of string
      cluster_name = placement.value["cluster_name"]
    }
  }

  dynamic "pyspark_config" {
    for_each = var.pyspark_config
    content {
      # archive_uris - (optional) is a type of list of string
      archive_uris = pyspark_config.value["archive_uris"]
      # args - (optional) is a type of list of string
      args = pyspark_config.value["args"]
      # file_uris - (optional) is a type of list of string
      file_uris = pyspark_config.value["file_uris"]
      # jar_file_uris - (optional) is a type of list of string
      jar_file_uris = pyspark_config.value["jar_file_uris"]
      # main_python_file_uri - (required) is a type of string
      main_python_file_uri = pyspark_config.value["main_python_file_uri"]
      # properties - (optional) is a type of map of string
      properties = pyspark_config.value["properties"]
      # python_file_uris - (optional) is a type of list of string
      python_file_uris = pyspark_config.value["python_file_uris"]

      dynamic "logging_config" {
        for_each = pyspark_config.value.logging_config
        content {
          # driver_log_levels - (required) is a type of map of string
          driver_log_levels = logging_config.value["driver_log_levels"]
        }
      }

    }
  }

  dynamic "reference" {
    for_each = var.reference
    content {
      # job_id - (optional) is a type of string
      job_id = reference.value["job_id"]
    }
  }

  dynamic "scheduling" {
    for_each = var.scheduling
    content {
      # max_failures_per_hour - (required) is a type of number
      max_failures_per_hour = scheduling.value["max_failures_per_hour"]
      # max_failures_total - (required) is a type of number
      max_failures_total = scheduling.value["max_failures_total"]
    }
  }

  dynamic "spark_config" {
    for_each = var.spark_config
    content {
      # archive_uris - (optional) is a type of list of string
      archive_uris = spark_config.value["archive_uris"]
      # args - (optional) is a type of list of string
      args = spark_config.value["args"]
      # file_uris - (optional) is a type of list of string
      file_uris = spark_config.value["file_uris"]
      # jar_file_uris - (optional) is a type of list of string
      jar_file_uris = spark_config.value["jar_file_uris"]
      # main_class - (optional) is a type of string
      main_class = spark_config.value["main_class"]
      # main_jar_file_uri - (optional) is a type of string
      main_jar_file_uri = spark_config.value["main_jar_file_uri"]
      # properties - (optional) is a type of map of string
      properties = spark_config.value["properties"]

      dynamic "logging_config" {
        for_each = spark_config.value.logging_config
        content {
          # driver_log_levels - (required) is a type of map of string
          driver_log_levels = logging_config.value["driver_log_levels"]
        }
      }

    }
  }

  dynamic "sparksql_config" {
    for_each = var.sparksql_config
    content {
      # jar_file_uris - (optional) is a type of list of string
      jar_file_uris = sparksql_config.value["jar_file_uris"]
      # properties - (optional) is a type of map of string
      properties = sparksql_config.value["properties"]
      # query_file_uri - (optional) is a type of string
      query_file_uri = sparksql_config.value["query_file_uri"]
      # query_list - (optional) is a type of list of string
      query_list = sparksql_config.value["query_list"]
      # script_variables - (optional) is a type of map of string
      script_variables = sparksql_config.value["script_variables"]

      dynamic "logging_config" {
        for_each = sparksql_config.value.logging_config
        content {
          # driver_log_levels - (required) is a type of map of string
          driver_log_levels = logging_config.value["driver_log_levels"]
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
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "driver_controls_files_uri" {
  description = "returns a string"
  value       = google_dataproc_job.this.driver_controls_files_uri
}

output "driver_output_resource_uri" {
  description = "returns a string"
  value       = google_dataproc_job.this.driver_output_resource_uri
}

output "id" {
  description = "returns a string"
  value       = google_dataproc_job.this.id
}

output "project" {
  description = "returns a string"
  value       = google_dataproc_job.this.project
}

output "status" {
  description = "returns a list of object"
  value       = google_dataproc_job.this.status
}

output "this" {
  value = google_dataproc_job.this
}
```

[top](#index)