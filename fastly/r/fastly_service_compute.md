# fastly_service_compute

[back](../fastly.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fastly = ">= 0.27.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fastly_service_compute" {
  source = "./modules/fastly/r/fastly_service_compute"

  # activate - (optional) is a type of bool
  activate = null
  # comment - (optional) is a type of string
  comment = null
  # force_destroy - (optional) is a type of bool
  force_destroy = null
  # name - (required) is a type of string
  name = null
  # version_comment - (optional) is a type of string
  version_comment = null

  backend = [{
    address               = null
    auto_loadbalance      = null
    between_bytes_timeout = null
    connect_timeout       = null
    error_threshold       = null
    first_byte_timeout    = null
    healthcheck           = null
    max_conn              = null
    max_tls_version       = null
    min_tls_version       = null
    name                  = null
    override_host         = null
    port                  = null
    shield                = null
    ssl_ca_cert           = null
    ssl_cert_hostname     = null
    ssl_check_cert        = null
    ssl_ciphers           = null
    ssl_client_cert       = null
    ssl_client_key        = null
    ssl_hostname          = null
    ssl_sni_hostname      = null
    use_ssl               = null
    weight                = null
  }]

  bigquerylogging = [{
    dataset    = null
    email      = null
    name       = null
    project_id = null
    secret_key = null
    table      = null
    template   = null
  }]

  blobstoragelogging = [{
    account_name     = null
    container        = null
    gzip_level       = null
    message_type     = null
    name             = null
    path             = null
    period           = null
    public_key       = null
    sas_token        = null
    timestamp_format = null
  }]

  dictionary = [{
    dictionary_id = null
    force_destroy = null
    name          = null
    write_only    = null
  }]

  domain = [{
    comment = null
    name    = null
  }]

  gcslogging = [{
    bucket_name      = null
    email            = null
    gzip_level       = null
    message_type     = null
    name             = null
    path             = null
    period           = null
    secret_key       = null
    timestamp_format = null
  }]

  healthcheck = [{
    check_interval    = null
    expected_response = null
    host              = null
    http_version      = null
    initial           = null
    method            = null
    name              = null
    path              = null
    threshold         = null
    timeout           = null
    window            = null
  }]

  httpslogging = [{
    content_type        = null
    header_name         = null
    header_value        = null
    json_format         = null
    message_type        = null
    method              = null
    name                = null
    request_max_bytes   = null
    request_max_entries = null
    tls_ca_cert         = null
    tls_client_cert     = null
    tls_client_key      = null
    tls_hostname        = null
    url                 = null
  }]

  logentries = [{
    name    = null
    port    = null
    token   = null
    use_tls = null
  }]

  logging_cloudfiles = [{
    access_key       = null
    bucket_name      = null
    gzip_level       = null
    message_type     = null
    name             = null
    path             = null
    period           = null
    public_key       = null
    region           = null
    timestamp_format = null
    user             = null
  }]

  logging_datadog = [{
    name   = null
    region = null
    token  = null
  }]

  logging_digitalocean = [{
    access_key       = null
    bucket_name      = null
    domain           = null
    gzip_level       = null
    message_type     = null
    name             = null
    path             = null
    period           = null
    public_key       = null
    secret_key       = null
    timestamp_format = null
  }]

  logging_elasticsearch = [{
    index               = null
    name                = null
    password            = null
    pipeline            = null
    request_max_bytes   = null
    request_max_entries = null
    tls_ca_cert         = null
    tls_client_cert     = null
    tls_client_key      = null
    tls_hostname        = null
    url                 = null
    user                = null
  }]

  logging_ftp = [{
    address          = null
    gzip_level       = null
    message_type     = null
    name             = null
    password         = null
    path             = null
    period           = null
    port             = null
    public_key       = null
    timestamp_format = null
    user             = null
  }]

  logging_googlepubsub = [{
    name       = null
    project_id = null
    secret_key = null
    topic      = null
    user       = null
  }]

  logging_heroku = [{
    name  = null
    token = null
    url   = null
  }]

  logging_honeycomb = [{
    dataset = null
    name    = null
    token   = null
  }]

  logging_kafka = [{
    auth_method       = null
    brokers           = null
    compression_codec = null
    name              = null
    parse_log_keyvals = null
    password          = null
    request_max_bytes = null
    required_acks     = null
    tls_ca_cert       = null
    tls_client_cert   = null
    tls_client_key    = null
    tls_hostname      = null
    topic             = null
    use_tls           = null
    user              = null
  }]

  logging_kinesis = [{
    access_key = null
    name       = null
    region     = null
    secret_key = null
    topic      = null
  }]

  logging_loggly = [{
    name  = null
    token = null
  }]

  logging_logshuttle = [{
    name  = null
    token = null
    url   = null
  }]

  logging_newrelic = [{
    name  = null
    token = null
  }]

  logging_openstack = [{
    access_key       = null
    bucket_name      = null
    gzip_level       = null
    message_type     = null
    name             = null
    path             = null
    period           = null
    public_key       = null
    timestamp_format = null
    url              = null
    user             = null
  }]

  logging_scalyr = [{
    name   = null
    region = null
    token  = null
  }]

  logging_sftp = [{
    address          = null
    gzip_level       = null
    message_type     = null
    name             = null
    password         = null
    path             = null
    period           = null
    port             = null
    public_key       = null
    secret_key       = null
    ssh_known_hosts  = null
    timestamp_format = null
    user             = null
  }]

  package = [{
    filename         = null
    source_code_hash = null
  }]

  papertrail = [{
    address = null
    name    = null
    port    = null
  }]

  s3logging = [{
    bucket_name                       = null
    domain                            = null
    gzip_level                        = null
    message_type                      = null
    name                              = null
    path                              = null
    period                            = null
    public_key                        = null
    redundancy                        = null
    s3_access_key                     = null
    s3_secret_key                     = null
    server_side_encryption            = null
    server_side_encryption_kms_key_id = null
    timestamp_format                  = null
  }]

  splunk = [{
    name            = null
    tls_ca_cert     = null
    tls_client_cert = null
    tls_client_key  = null
    tls_hostname    = null
    token           = null
    url             = null
  }]

  sumologic = [{
    message_type = null
    name         = null
    url          = null
  }]

  syslog = [{
    address         = null
    message_type    = null
    name            = null
    port            = null
    tls_ca_cert     = null
    tls_client_cert = null
    tls_client_key  = null
    tls_hostname    = null
    token           = null
    use_tls         = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "activate" {
  description = "(optional) - Conditionally prevents the Service from being activated. The apply step will continue to create a new draft version but will not activate it if this is set to `false`. Default `true`"
  type        = bool
  default     = null
}

variable "comment" {
  description = "(optional) - Description field for the service. Default `Managed by Terraform`"
  type        = string
  default     = null
}

variable "force_destroy" {
  description = "(optional) - Services that are active cannot be destroyed. In order to destroy the Service, set `force_destroy` to `true`. Default `false`"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required) - The unique name for the Service to create"
  type        = string
}

variable "version_comment" {
  description = "(optional) - Description field for the version"
  type        = string
  default     = null
}

variable "backend" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      address               = string
      auto_loadbalance      = bool
      between_bytes_timeout = number
      connect_timeout       = number
      error_threshold       = number
      first_byte_timeout    = number
      healthcheck           = string
      max_conn              = number
      max_tls_version       = string
      min_tls_version       = string
      name                  = string
      override_host         = string
      port                  = number
      shield                = string
      ssl_ca_cert           = string
      ssl_cert_hostname     = string
      ssl_check_cert        = bool
      ssl_ciphers           = string
      ssl_client_cert       = string
      ssl_client_key        = string
      ssl_hostname          = string
      ssl_sni_hostname      = string
      use_ssl               = bool
      weight                = number
    }
  ))
}

variable "bigquerylogging" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      dataset    = string
      email      = string
      name       = string
      project_id = string
      secret_key = string
      table      = string
      template   = string
    }
  ))
  default = []
}

variable "blobstoragelogging" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      account_name     = string
      container        = string
      gzip_level       = number
      message_type     = string
      name             = string
      path             = string
      period           = number
      public_key       = string
      sas_token        = string
      timestamp_format = string
    }
  ))
  default = []
}

variable "dictionary" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      dictionary_id = string
      force_destroy = bool
      name          = string
      write_only    = bool
    }
  ))
  default = []
}

variable "domain" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      comment = string
      name    = string
    }
  ))
}

variable "gcslogging" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      bucket_name      = string
      email            = string
      gzip_level       = number
      message_type     = string
      name             = string
      path             = string
      period           = number
      secret_key       = string
      timestamp_format = string
    }
  ))
  default = []
}

variable "healthcheck" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      check_interval    = number
      expected_response = number
      host              = string
      http_version      = string
      initial           = number
      method            = string
      name              = string
      path              = string
      threshold         = number
      timeout           = number
      window            = number
    }
  ))
  default = []
}

variable "httpslogging" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      content_type        = string
      header_name         = string
      header_value        = string
      json_format         = string
      message_type        = string
      method              = string
      name                = string
      request_max_bytes   = number
      request_max_entries = number
      tls_ca_cert         = string
      tls_client_cert     = string
      tls_client_key      = string
      tls_hostname        = string
      url                 = string
    }
  ))
  default = []
}

variable "logentries" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name    = string
      port    = number
      token   = string
      use_tls = bool
    }
  ))
  default = []
}

variable "logging_cloudfiles" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      access_key       = string
      bucket_name      = string
      gzip_level       = number
      message_type     = string
      name             = string
      path             = string
      period           = number
      public_key       = string
      region           = string
      timestamp_format = string
      user             = string
    }
  ))
  default = []
}

variable "logging_datadog" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name   = string
      region = string
      token  = string
    }
  ))
  default = []
}

variable "logging_digitalocean" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      access_key       = string
      bucket_name      = string
      domain           = string
      gzip_level       = number
      message_type     = string
      name             = string
      path             = string
      period           = number
      public_key       = string
      secret_key       = string
      timestamp_format = string
    }
  ))
  default = []
}

variable "logging_elasticsearch" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      index               = string
      name                = string
      password            = string
      pipeline            = string
      request_max_bytes   = number
      request_max_entries = number
      tls_ca_cert         = string
      tls_client_cert     = string
      tls_client_key      = string
      tls_hostname        = string
      url                 = string
      user                = string
    }
  ))
  default = []
}

variable "logging_ftp" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      address          = string
      gzip_level       = number
      message_type     = string
      name             = string
      password         = string
      path             = string
      period           = number
      port             = number
      public_key       = string
      timestamp_format = string
      user             = string
    }
  ))
  default = []
}

variable "logging_googlepubsub" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name       = string
      project_id = string
      secret_key = string
      topic      = string
      user       = string
    }
  ))
  default = []
}

variable "logging_heroku" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name  = string
      token = string
      url   = string
    }
  ))
  default = []
}

variable "logging_honeycomb" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      dataset = string
      name    = string
      token   = string
    }
  ))
  default = []
}

variable "logging_kafka" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      auth_method       = string
      brokers           = string
      compression_codec = string
      name              = string
      parse_log_keyvals = bool
      password          = string
      request_max_bytes = number
      required_acks     = string
      tls_ca_cert       = string
      tls_client_cert   = string
      tls_client_key    = string
      tls_hostname      = string
      topic             = string
      use_tls           = bool
      user              = string
    }
  ))
  default = []
}

variable "logging_kinesis" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      access_key = string
      name       = string
      region     = string
      secret_key = string
      topic      = string
    }
  ))
  default = []
}

variable "logging_loggly" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name  = string
      token = string
    }
  ))
  default = []
}

variable "logging_logshuttle" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name  = string
      token = string
      url   = string
    }
  ))
  default = []
}

variable "logging_newrelic" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name  = string
      token = string
    }
  ))
  default = []
}

variable "logging_openstack" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      access_key       = string
      bucket_name      = string
      gzip_level       = number
      message_type     = string
      name             = string
      path             = string
      period           = number
      public_key       = string
      timestamp_format = string
      url              = string
      user             = string
    }
  ))
  default = []
}

variable "logging_scalyr" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name   = string
      region = string
      token  = string
    }
  ))
  default = []
}

variable "logging_sftp" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      address          = string
      gzip_level       = number
      message_type     = string
      name             = string
      password         = string
      path             = string
      period           = number
      port             = number
      public_key       = string
      secret_key       = string
      ssh_known_hosts  = string
      timestamp_format = string
      user             = string
    }
  ))
  default = []
}

variable "package" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      filename         = string
      source_code_hash = string
    }
  ))
}

variable "papertrail" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      address = string
      name    = string
      port    = number
    }
  ))
  default = []
}

variable "s3logging" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      bucket_name                       = string
      domain                            = string
      gzip_level                        = number
      message_type                      = string
      name                              = string
      path                              = string
      period                            = number
      public_key                        = string
      redundancy                        = string
      s3_access_key                     = string
      s3_secret_key                     = string
      server_side_encryption            = string
      server_side_encryption_kms_key_id = string
      timestamp_format                  = string
    }
  ))
  default = []
}

variable "splunk" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name            = string
      tls_ca_cert     = string
      tls_client_cert = string
      tls_client_key  = string
      tls_hostname    = string
      token           = string
      url             = string
    }
  ))
  default = []
}

variable "sumologic" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      message_type = string
      name         = string
      url          = string
    }
  ))
  default = []
}

variable "syslog" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      address         = string
      message_type    = string
      name            = string
      port            = number
      tls_ca_cert     = string
      tls_client_cert = string
      tls_client_key  = string
      tls_hostname    = string
      token           = string
      use_tls         = bool
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fastly_service_compute" "this" {
  # activate - (optional) is a type of bool
  activate = var.activate
  # comment - (optional) is a type of string
  comment = var.comment
  # force_destroy - (optional) is a type of bool
  force_destroy = var.force_destroy
  # name - (required) is a type of string
  name = var.name
  # version_comment - (optional) is a type of string
  version_comment = var.version_comment

  dynamic "backend" {
    for_each = var.backend
    content {
      # address - (required) is a type of string
      address = backend.value["address"]
      # auto_loadbalance - (optional) is a type of bool
      auto_loadbalance = backend.value["auto_loadbalance"]
      # between_bytes_timeout - (optional) is a type of number
      between_bytes_timeout = backend.value["between_bytes_timeout"]
      # connect_timeout - (optional) is a type of number
      connect_timeout = backend.value["connect_timeout"]
      # error_threshold - (optional) is a type of number
      error_threshold = backend.value["error_threshold"]
      # first_byte_timeout - (optional) is a type of number
      first_byte_timeout = backend.value["first_byte_timeout"]
      # healthcheck - (optional) is a type of string
      healthcheck = backend.value["healthcheck"]
      # max_conn - (optional) is a type of number
      max_conn = backend.value["max_conn"]
      # max_tls_version - (optional) is a type of string
      max_tls_version = backend.value["max_tls_version"]
      # min_tls_version - (optional) is a type of string
      min_tls_version = backend.value["min_tls_version"]
      # name - (required) is a type of string
      name = backend.value["name"]
      # override_host - (optional) is a type of string
      override_host = backend.value["override_host"]
      # port - (optional) is a type of number
      port = backend.value["port"]
      # shield - (optional) is a type of string
      shield = backend.value["shield"]
      # ssl_ca_cert - (optional) is a type of string
      ssl_ca_cert = backend.value["ssl_ca_cert"]
      # ssl_cert_hostname - (optional) is a type of string
      ssl_cert_hostname = backend.value["ssl_cert_hostname"]
      # ssl_check_cert - (optional) is a type of bool
      ssl_check_cert = backend.value["ssl_check_cert"]
      # ssl_ciphers - (optional) is a type of string
      ssl_ciphers = backend.value["ssl_ciphers"]
      # ssl_client_cert - (optional) is a type of string
      ssl_client_cert = backend.value["ssl_client_cert"]
      # ssl_client_key - (optional) is a type of string
      ssl_client_key = backend.value["ssl_client_key"]
      # ssl_hostname - (optional) is a type of string
      ssl_hostname = backend.value["ssl_hostname"]
      # ssl_sni_hostname - (optional) is a type of string
      ssl_sni_hostname = backend.value["ssl_sni_hostname"]
      # use_ssl - (optional) is a type of bool
      use_ssl = backend.value["use_ssl"]
      # weight - (optional) is a type of number
      weight = backend.value["weight"]
    }
  }

  dynamic "bigquerylogging" {
    for_each = var.bigquerylogging
    content {
      # dataset - (required) is a type of string
      dataset = bigquerylogging.value["dataset"]
      # email - (optional) is a type of string
      email = bigquerylogging.value["email"]
      # name - (required) is a type of string
      name = bigquerylogging.value["name"]
      # project_id - (required) is a type of string
      project_id = bigquerylogging.value["project_id"]
      # secret_key - (optional) is a type of string
      secret_key = bigquerylogging.value["secret_key"]
      # table - (required) is a type of string
      table = bigquerylogging.value["table"]
      # template - (optional) is a type of string
      template = bigquerylogging.value["template"]
    }
  }

  dynamic "blobstoragelogging" {
    for_each = var.blobstoragelogging
    content {
      # account_name - (required) is a type of string
      account_name = blobstoragelogging.value["account_name"]
      # container - (required) is a type of string
      container = blobstoragelogging.value["container"]
      # gzip_level - (optional) is a type of number
      gzip_level = blobstoragelogging.value["gzip_level"]
      # message_type - (optional) is a type of string
      message_type = blobstoragelogging.value["message_type"]
      # name - (required) is a type of string
      name = blobstoragelogging.value["name"]
      # path - (optional) is a type of string
      path = blobstoragelogging.value["path"]
      # period - (optional) is a type of number
      period = blobstoragelogging.value["period"]
      # public_key - (optional) is a type of string
      public_key = blobstoragelogging.value["public_key"]
      # sas_token - (optional) is a type of string
      sas_token = blobstoragelogging.value["sas_token"]
      # timestamp_format - (optional) is a type of string
      timestamp_format = blobstoragelogging.value["timestamp_format"]
    }
  }

  dynamic "dictionary" {
    for_each = var.dictionary
    content {
      # force_destroy - (optional) is a type of bool
      force_destroy = dictionary.value["force_destroy"]
      # name - (required) is a type of string
      name = dictionary.value["name"]
      # write_only - (optional) is a type of bool
      write_only = dictionary.value["write_only"]
    }
  }

  dynamic "domain" {
    for_each = var.domain
    content {
      # comment - (optional) is a type of string
      comment = domain.value["comment"]
      # name - (required) is a type of string
      name = domain.value["name"]
    }
  }

  dynamic "gcslogging" {
    for_each = var.gcslogging
    content {
      # bucket_name - (required) is a type of string
      bucket_name = gcslogging.value["bucket_name"]
      # email - (optional) is a type of string
      email = gcslogging.value["email"]
      # gzip_level - (optional) is a type of number
      gzip_level = gcslogging.value["gzip_level"]
      # message_type - (optional) is a type of string
      message_type = gcslogging.value["message_type"]
      # name - (required) is a type of string
      name = gcslogging.value["name"]
      # path - (optional) is a type of string
      path = gcslogging.value["path"]
      # period - (optional) is a type of number
      period = gcslogging.value["period"]
      # secret_key - (optional) is a type of string
      secret_key = gcslogging.value["secret_key"]
      # timestamp_format - (optional) is a type of string
      timestamp_format = gcslogging.value["timestamp_format"]
    }
  }

  dynamic "healthcheck" {
    for_each = var.healthcheck
    content {
      # check_interval - (optional) is a type of number
      check_interval = healthcheck.value["check_interval"]
      # expected_response - (optional) is a type of number
      expected_response = healthcheck.value["expected_response"]
      # host - (required) is a type of string
      host = healthcheck.value["host"]
      # http_version - (optional) is a type of string
      http_version = healthcheck.value["http_version"]
      # initial - (optional) is a type of number
      initial = healthcheck.value["initial"]
      # method - (optional) is a type of string
      method = healthcheck.value["method"]
      # name - (required) is a type of string
      name = healthcheck.value["name"]
      # path - (required) is a type of string
      path = healthcheck.value["path"]
      # threshold - (optional) is a type of number
      threshold = healthcheck.value["threshold"]
      # timeout - (optional) is a type of number
      timeout = healthcheck.value["timeout"]
      # window - (optional) is a type of number
      window = healthcheck.value["window"]
    }
  }

  dynamic "httpslogging" {
    for_each = var.httpslogging
    content {
      # content_type - (optional) is a type of string
      content_type = httpslogging.value["content_type"]
      # header_name - (optional) is a type of string
      header_name = httpslogging.value["header_name"]
      # header_value - (optional) is a type of string
      header_value = httpslogging.value["header_value"]
      # json_format - (optional) is a type of string
      json_format = httpslogging.value["json_format"]
      # message_type - (optional) is a type of string
      message_type = httpslogging.value["message_type"]
      # method - (optional) is a type of string
      method = httpslogging.value["method"]
      # name - (required) is a type of string
      name = httpslogging.value["name"]
      # request_max_bytes - (optional) is a type of number
      request_max_bytes = httpslogging.value["request_max_bytes"]
      # request_max_entries - (optional) is a type of number
      request_max_entries = httpslogging.value["request_max_entries"]
      # tls_ca_cert - (optional) is a type of string
      tls_ca_cert = httpslogging.value["tls_ca_cert"]
      # tls_client_cert - (optional) is a type of string
      tls_client_cert = httpslogging.value["tls_client_cert"]
      # tls_client_key - (optional) is a type of string
      tls_client_key = httpslogging.value["tls_client_key"]
      # tls_hostname - (optional) is a type of string
      tls_hostname = httpslogging.value["tls_hostname"]
      # url - (required) is a type of string
      url = httpslogging.value["url"]
    }
  }

  dynamic "logentries" {
    for_each = var.logentries
    content {
      # name - (required) is a type of string
      name = logentries.value["name"]
      # port - (optional) is a type of number
      port = logentries.value["port"]
      # token - (required) is a type of string
      token = logentries.value["token"]
      # use_tls - (optional) is a type of bool
      use_tls = logentries.value["use_tls"]
    }
  }

  dynamic "logging_cloudfiles" {
    for_each = var.logging_cloudfiles
    content {
      # access_key - (required) is a type of string
      access_key = logging_cloudfiles.value["access_key"]
      # bucket_name - (required) is a type of string
      bucket_name = logging_cloudfiles.value["bucket_name"]
      # gzip_level - (optional) is a type of number
      gzip_level = logging_cloudfiles.value["gzip_level"]
      # message_type - (optional) is a type of string
      message_type = logging_cloudfiles.value["message_type"]
      # name - (required) is a type of string
      name = logging_cloudfiles.value["name"]
      # path - (optional) is a type of string
      path = logging_cloudfiles.value["path"]
      # period - (optional) is a type of number
      period = logging_cloudfiles.value["period"]
      # public_key - (optional) is a type of string
      public_key = logging_cloudfiles.value["public_key"]
      # region - (optional) is a type of string
      region = logging_cloudfiles.value["region"]
      # timestamp_format - (optional) is a type of string
      timestamp_format = logging_cloudfiles.value["timestamp_format"]
      # user - (required) is a type of string
      user = logging_cloudfiles.value["user"]
    }
  }

  dynamic "logging_datadog" {
    for_each = var.logging_datadog
    content {
      # name - (required) is a type of string
      name = logging_datadog.value["name"]
      # region - (optional) is a type of string
      region = logging_datadog.value["region"]
      # token - (required) is a type of string
      token = logging_datadog.value["token"]
    }
  }

  dynamic "logging_digitalocean" {
    for_each = var.logging_digitalocean
    content {
      # access_key - (required) is a type of string
      access_key = logging_digitalocean.value["access_key"]
      # bucket_name - (required) is a type of string
      bucket_name = logging_digitalocean.value["bucket_name"]
      # domain - (optional) is a type of string
      domain = logging_digitalocean.value["domain"]
      # gzip_level - (optional) is a type of number
      gzip_level = logging_digitalocean.value["gzip_level"]
      # message_type - (optional) is a type of string
      message_type = logging_digitalocean.value["message_type"]
      # name - (required) is a type of string
      name = logging_digitalocean.value["name"]
      # path - (optional) is a type of string
      path = logging_digitalocean.value["path"]
      # period - (optional) is a type of number
      period = logging_digitalocean.value["period"]
      # public_key - (optional) is a type of string
      public_key = logging_digitalocean.value["public_key"]
      # secret_key - (required) is a type of string
      secret_key = logging_digitalocean.value["secret_key"]
      # timestamp_format - (optional) is a type of string
      timestamp_format = logging_digitalocean.value["timestamp_format"]
    }
  }

  dynamic "logging_elasticsearch" {
    for_each = var.logging_elasticsearch
    content {
      # index - (required) is a type of string
      index = logging_elasticsearch.value["index"]
      # name - (required) is a type of string
      name = logging_elasticsearch.value["name"]
      # password - (optional) is a type of string
      password = logging_elasticsearch.value["password"]
      # pipeline - (optional) is a type of string
      pipeline = logging_elasticsearch.value["pipeline"]
      # request_max_bytes - (optional) is a type of number
      request_max_bytes = logging_elasticsearch.value["request_max_bytes"]
      # request_max_entries - (optional) is a type of number
      request_max_entries = logging_elasticsearch.value["request_max_entries"]
      # tls_ca_cert - (optional) is a type of string
      tls_ca_cert = logging_elasticsearch.value["tls_ca_cert"]
      # tls_client_cert - (optional) is a type of string
      tls_client_cert = logging_elasticsearch.value["tls_client_cert"]
      # tls_client_key - (optional) is a type of string
      tls_client_key = logging_elasticsearch.value["tls_client_key"]
      # tls_hostname - (optional) is a type of string
      tls_hostname = logging_elasticsearch.value["tls_hostname"]
      # url - (required) is a type of string
      url = logging_elasticsearch.value["url"]
      # user - (optional) is a type of string
      user = logging_elasticsearch.value["user"]
    }
  }

  dynamic "logging_ftp" {
    for_each = var.logging_ftp
    content {
      # address - (required) is a type of string
      address = logging_ftp.value["address"]
      # gzip_level - (optional) is a type of number
      gzip_level = logging_ftp.value["gzip_level"]
      # message_type - (optional) is a type of string
      message_type = logging_ftp.value["message_type"]
      # name - (required) is a type of string
      name = logging_ftp.value["name"]
      # password - (required) is a type of string
      password = logging_ftp.value["password"]
      # path - (required) is a type of string
      path = logging_ftp.value["path"]
      # period - (optional) is a type of number
      period = logging_ftp.value["period"]
      # port - (optional) is a type of number
      port = logging_ftp.value["port"]
      # public_key - (optional) is a type of string
      public_key = logging_ftp.value["public_key"]
      # timestamp_format - (optional) is a type of string
      timestamp_format = logging_ftp.value["timestamp_format"]
      # user - (required) is a type of string
      user = logging_ftp.value["user"]
    }
  }

  dynamic "logging_googlepubsub" {
    for_each = var.logging_googlepubsub
    content {
      # name - (required) is a type of string
      name = logging_googlepubsub.value["name"]
      # project_id - (required) is a type of string
      project_id = logging_googlepubsub.value["project_id"]
      # secret_key - (optional) is a type of string
      secret_key = logging_googlepubsub.value["secret_key"]
      # topic - (required) is a type of string
      topic = logging_googlepubsub.value["topic"]
      # user - (optional) is a type of string
      user = logging_googlepubsub.value["user"]
    }
  }

  dynamic "logging_heroku" {
    for_each = var.logging_heroku
    content {
      # name - (required) is a type of string
      name = logging_heroku.value["name"]
      # token - (required) is a type of string
      token = logging_heroku.value["token"]
      # url - (required) is a type of string
      url = logging_heroku.value["url"]
    }
  }

  dynamic "logging_honeycomb" {
    for_each = var.logging_honeycomb
    content {
      # dataset - (required) is a type of string
      dataset = logging_honeycomb.value["dataset"]
      # name - (required) is a type of string
      name = logging_honeycomb.value["name"]
      # token - (required) is a type of string
      token = logging_honeycomb.value["token"]
    }
  }

  dynamic "logging_kafka" {
    for_each = var.logging_kafka
    content {
      # auth_method - (optional) is a type of string
      auth_method = logging_kafka.value["auth_method"]
      # brokers - (required) is a type of string
      brokers = logging_kafka.value["brokers"]
      # compression_codec - (optional) is a type of string
      compression_codec = logging_kafka.value["compression_codec"]
      # name - (required) is a type of string
      name = logging_kafka.value["name"]
      # parse_log_keyvals - (optional) is a type of bool
      parse_log_keyvals = logging_kafka.value["parse_log_keyvals"]
      # password - (optional) is a type of string
      password = logging_kafka.value["password"]
      # request_max_bytes - (optional) is a type of number
      request_max_bytes = logging_kafka.value["request_max_bytes"]
      # required_acks - (optional) is a type of string
      required_acks = logging_kafka.value["required_acks"]
      # tls_ca_cert - (optional) is a type of string
      tls_ca_cert = logging_kafka.value["tls_ca_cert"]
      # tls_client_cert - (optional) is a type of string
      tls_client_cert = logging_kafka.value["tls_client_cert"]
      # tls_client_key - (optional) is a type of string
      tls_client_key = logging_kafka.value["tls_client_key"]
      # tls_hostname - (optional) is a type of string
      tls_hostname = logging_kafka.value["tls_hostname"]
      # topic - (required) is a type of string
      topic = logging_kafka.value["topic"]
      # use_tls - (optional) is a type of bool
      use_tls = logging_kafka.value["use_tls"]
      # user - (optional) is a type of string
      user = logging_kafka.value["user"]
    }
  }

  dynamic "logging_kinesis" {
    for_each = var.logging_kinesis
    content {
      # access_key - (required) is a type of string
      access_key = logging_kinesis.value["access_key"]
      # name - (required) is a type of string
      name = logging_kinesis.value["name"]
      # region - (optional) is a type of string
      region = logging_kinesis.value["region"]
      # secret_key - (required) is a type of string
      secret_key = logging_kinesis.value["secret_key"]
      # topic - (required) is a type of string
      topic = logging_kinesis.value["topic"]
    }
  }

  dynamic "logging_loggly" {
    for_each = var.logging_loggly
    content {
      # name - (required) is a type of string
      name = logging_loggly.value["name"]
      # token - (required) is a type of string
      token = logging_loggly.value["token"]
    }
  }

  dynamic "logging_logshuttle" {
    for_each = var.logging_logshuttle
    content {
      # name - (required) is a type of string
      name = logging_logshuttle.value["name"]
      # token - (required) is a type of string
      token = logging_logshuttle.value["token"]
      # url - (required) is a type of string
      url = logging_logshuttle.value["url"]
    }
  }

  dynamic "logging_newrelic" {
    for_each = var.logging_newrelic
    content {
      # name - (required) is a type of string
      name = logging_newrelic.value["name"]
      # token - (required) is a type of string
      token = logging_newrelic.value["token"]
    }
  }

  dynamic "logging_openstack" {
    for_each = var.logging_openstack
    content {
      # access_key - (required) is a type of string
      access_key = logging_openstack.value["access_key"]
      # bucket_name - (required) is a type of string
      bucket_name = logging_openstack.value["bucket_name"]
      # gzip_level - (optional) is a type of number
      gzip_level = logging_openstack.value["gzip_level"]
      # message_type - (optional) is a type of string
      message_type = logging_openstack.value["message_type"]
      # name - (required) is a type of string
      name = logging_openstack.value["name"]
      # path - (optional) is a type of string
      path = logging_openstack.value["path"]
      # period - (optional) is a type of number
      period = logging_openstack.value["period"]
      # public_key - (optional) is a type of string
      public_key = logging_openstack.value["public_key"]
      # timestamp_format - (optional) is a type of string
      timestamp_format = logging_openstack.value["timestamp_format"]
      # url - (required) is a type of string
      url = logging_openstack.value["url"]
      # user - (required) is a type of string
      user = logging_openstack.value["user"]
    }
  }

  dynamic "logging_scalyr" {
    for_each = var.logging_scalyr
    content {
      # name - (required) is a type of string
      name = logging_scalyr.value["name"]
      # region - (optional) is a type of string
      region = logging_scalyr.value["region"]
      # token - (required) is a type of string
      token = logging_scalyr.value["token"]
    }
  }

  dynamic "logging_sftp" {
    for_each = var.logging_sftp
    content {
      # address - (required) is a type of string
      address = logging_sftp.value["address"]
      # gzip_level - (optional) is a type of number
      gzip_level = logging_sftp.value["gzip_level"]
      # message_type - (optional) is a type of string
      message_type = logging_sftp.value["message_type"]
      # name - (required) is a type of string
      name = logging_sftp.value["name"]
      # password - (optional) is a type of string
      password = logging_sftp.value["password"]
      # path - (required) is a type of string
      path = logging_sftp.value["path"]
      # period - (optional) is a type of number
      period = logging_sftp.value["period"]
      # port - (optional) is a type of number
      port = logging_sftp.value["port"]
      # public_key - (optional) is a type of string
      public_key = logging_sftp.value["public_key"]
      # secret_key - (optional) is a type of string
      secret_key = logging_sftp.value["secret_key"]
      # ssh_known_hosts - (required) is a type of string
      ssh_known_hosts = logging_sftp.value["ssh_known_hosts"]
      # timestamp_format - (optional) is a type of string
      timestamp_format = logging_sftp.value["timestamp_format"]
      # user - (required) is a type of string
      user = logging_sftp.value["user"]
    }
  }

  dynamic "package" {
    for_each = var.package
    content {
      # filename - (required) is a type of string
      filename = package.value["filename"]
      # source_code_hash - (optional) is a type of string
      source_code_hash = package.value["source_code_hash"]
    }
  }

  dynamic "papertrail" {
    for_each = var.papertrail
    content {
      # address - (required) is a type of string
      address = papertrail.value["address"]
      # name - (required) is a type of string
      name = papertrail.value["name"]
      # port - (required) is a type of number
      port = papertrail.value["port"]
    }
  }

  dynamic "s3logging" {
    for_each = var.s3logging
    content {
      # bucket_name - (required) is a type of string
      bucket_name = s3logging.value["bucket_name"]
      # domain - (optional) is a type of string
      domain = s3logging.value["domain"]
      # gzip_level - (optional) is a type of number
      gzip_level = s3logging.value["gzip_level"]
      # message_type - (optional) is a type of string
      message_type = s3logging.value["message_type"]
      # name - (required) is a type of string
      name = s3logging.value["name"]
      # path - (optional) is a type of string
      path = s3logging.value["path"]
      # period - (optional) is a type of number
      period = s3logging.value["period"]
      # public_key - (optional) is a type of string
      public_key = s3logging.value["public_key"]
      # redundancy - (optional) is a type of string
      redundancy = s3logging.value["redundancy"]
      # s3_access_key - (optional) is a type of string
      s3_access_key = s3logging.value["s3_access_key"]
      # s3_secret_key - (optional) is a type of string
      s3_secret_key = s3logging.value["s3_secret_key"]
      # server_side_encryption - (optional) is a type of string
      server_side_encryption = s3logging.value["server_side_encryption"]
      # server_side_encryption_kms_key_id - (optional) is a type of string
      server_side_encryption_kms_key_id = s3logging.value["server_side_encryption_kms_key_id"]
      # timestamp_format - (optional) is a type of string
      timestamp_format = s3logging.value["timestamp_format"]
    }
  }

  dynamic "splunk" {
    for_each = var.splunk
    content {
      # name - (required) is a type of string
      name = splunk.value["name"]
      # tls_ca_cert - (optional) is a type of string
      tls_ca_cert = splunk.value["tls_ca_cert"]
      # tls_client_cert - (optional) is a type of string
      tls_client_cert = splunk.value["tls_client_cert"]
      # tls_client_key - (optional) is a type of string
      tls_client_key = splunk.value["tls_client_key"]
      # tls_hostname - (optional) is a type of string
      tls_hostname = splunk.value["tls_hostname"]
      # token - (optional) is a type of string
      token = splunk.value["token"]
      # url - (required) is a type of string
      url = splunk.value["url"]
    }
  }

  dynamic "sumologic" {
    for_each = var.sumologic
    content {
      # message_type - (optional) is a type of string
      message_type = sumologic.value["message_type"]
      # name - (required) is a type of string
      name = sumologic.value["name"]
      # url - (required) is a type of string
      url = sumologic.value["url"]
    }
  }

  dynamic "syslog" {
    for_each = var.syslog
    content {
      # address - (required) is a type of string
      address = syslog.value["address"]
      # message_type - (optional) is a type of string
      message_type = syslog.value["message_type"]
      # name - (required) is a type of string
      name = syslog.value["name"]
      # port - (optional) is a type of number
      port = syslog.value["port"]
      # tls_ca_cert - (optional) is a type of string
      tls_ca_cert = syslog.value["tls_ca_cert"]
      # tls_client_cert - (optional) is a type of string
      tls_client_cert = syslog.value["tls_client_cert"]
      # tls_client_key - (optional) is a type of string
      tls_client_key = syslog.value["tls_client_key"]
      # tls_hostname - (optional) is a type of string
      tls_hostname = syslog.value["tls_hostname"]
      # token - (optional) is a type of string
      token = syslog.value["token"]
      # use_tls - (optional) is a type of bool
      use_tls = syslog.value["use_tls"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "active_version" {
  description = "returns a number"
  value       = fastly_service_compute.this.active_version
}

output "cloned_version" {
  description = "returns a number"
  value       = fastly_service_compute.this.cloned_version
}

output "id" {
  description = "returns a string"
  value       = fastly_service_compute.this.id
}

output "this" {
  value = fastly_service_compute.this
}
```

[top](#index)