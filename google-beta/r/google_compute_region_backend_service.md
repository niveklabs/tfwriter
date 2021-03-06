# google_compute_region_backend_service

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
module "google_compute_region_backend_service" {
  source = "./modules/google-beta/r/google_compute_region_backend_service"

  # affinity_cookie_ttl_sec - (optional) is a type of number
  affinity_cookie_ttl_sec = null
  # connection_draining_timeout_sec - (optional) is a type of number
  connection_draining_timeout_sec = null
  # description - (optional) is a type of string
  description = null
  # enable_cdn - (optional) is a type of bool
  enable_cdn = null
  # health_checks - (optional) is a type of set of string
  health_checks = []
  # load_balancing_scheme - (optional) is a type of string
  load_balancing_scheme = null
  # locality_lb_policy - (optional) is a type of string
  locality_lb_policy = null
  # name - (required) is a type of string
  name = null
  # network - (optional) is a type of string
  network = null
  # port_name - (optional) is a type of string
  port_name = null
  # project - (optional) is a type of string
  project = null
  # protocol - (optional) is a type of string
  protocol = null
  # region - (optional) is a type of string
  region = null
  # session_affinity - (optional) is a type of string
  session_affinity = null
  # timeout_sec - (optional) is a type of number
  timeout_sec = null

  backend = [{
    balancing_mode               = null
    capacity_scaler              = null
    description                  = null
    failover                     = null
    group                        = null
    max_connections              = null
    max_connections_per_endpoint = null
    max_connections_per_instance = null
    max_rate                     = null
    max_rate_per_endpoint        = null
    max_rate_per_instance        = null
    max_utilization              = null
  }]

  cdn_policy = [{
    cache_key_policy = [{
      include_host           = null
      include_protocol       = null
      include_query_string   = null
      query_string_blacklist = []
      query_string_whitelist = []
    }]
    cache_mode       = null
    client_ttl       = null
    default_ttl      = null
    max_ttl          = null
    negative_caching = null
    negative_caching_policy = [{
      code = null
      ttl  = null
    }]
    serve_while_stale            = null
    signed_url_cache_max_age_sec = null
  }]

  circuit_breakers = [{
    connect_timeout = [{
      nanos   = null
      seconds = null
    }]
    max_connections             = null
    max_pending_requests        = null
    max_requests                = null
    max_requests_per_connection = null
    max_retries                 = null
  }]

  consistent_hash = [{
    http_cookie = [{
      name = null
      path = null
      ttl = [{
        nanos   = null
        seconds = null
      }]
    }]
    http_header_name  = null
    minimum_ring_size = null
  }]

  failover_policy = [{
    disable_connection_drain_on_failover = null
    drop_traffic_if_unhealthy            = null
    failover_ratio                       = null
  }]

  log_config = [{
    enable      = null
    sample_rate = null
  }]

  outlier_detection = [{
    base_ejection_time = [{
      nanos   = null
      seconds = null
    }]
    consecutive_errors                    = null
    consecutive_gateway_failure           = null
    enforcing_consecutive_errors          = null
    enforcing_consecutive_gateway_failure = null
    enforcing_success_rate                = null
    interval = [{
      nanos   = null
      seconds = null
    }]
    max_ejection_percent        = null
    success_rate_minimum_hosts  = null
    success_rate_request_volume = null
    success_rate_stdev_factor   = null
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
variable "affinity_cookie_ttl_sec" {
  description = "(optional) - Lifetime of cookies in seconds if session_affinity is\nGENERATED_COOKIE. If set to 0, the cookie is non-persistent and lasts\nonly until the end of the browser session (or equivalent). The\nmaximum allowed value for TTL is one day.\n\nWhen the load balancing scheme is INTERNAL, this field is not used."
  type        = number
  default     = null
}

variable "connection_draining_timeout_sec" {
  description = "(optional) - Time for which instance will be drained (not accept new\nconnections, but still work to finish started)."
  type        = number
  default     = null
}

variable "description" {
  description = "(optional) - An optional description of this resource."
  type        = string
  default     = null
}

variable "enable_cdn" {
  description = "(optional) - If true, enable Cloud CDN for this RegionBackendService."
  type        = bool
  default     = null
}

variable "health_checks" {
  description = "(optional) - The set of URLs to HealthCheck resources for health checking\nthis RegionBackendService. Currently at most one health\ncheck can be specified.\n\nA health check must be specified unless the backend service uses an internet\nor serverless NEG as a backend."
  type        = set(string)
  default     = null
}

variable "load_balancing_scheme" {
  description = "(optional) - Indicates what kind of load balancing this regional backend service\nwill be used for. A backend service created for one type of load\nbalancing cannot be used with the other(s). Default value: \"INTERNAL\" Possible values: [\"EXTERNAL\", \"INTERNAL\", \"INTERNAL_MANAGED\"]"
  type        = string
  default     = null
}

variable "locality_lb_policy" {
  description = "(optional) - The load balancing algorithm used within the scope of the locality.\nThe possible values are -\n\n* ROUND_ROBIN - This is a simple policy in which each healthy backend\n                is selected in round robin order.\n\n* LEAST_REQUEST - An O(1) algorithm which selects two random healthy\n                  hosts and picks the host which has fewer active requests.\n\n* RING_HASH - The ring/modulo hash load balancer implements consistent\n              hashing to backends. The algorithm has the property that the\n              addition/removal of a host from a set of N hosts only affects\n              1/N of the requests.\n\n* RANDOM - The load balancer selects a random healthy host.\n\n* ORIGINAL_DESTINATION - Backend host is selected based on the client\n                         connection metadata, i.e., connections are opened\n                         to the same address as the destination address of\n                         the incoming connection before the connection\n                         was redirected to the load balancer.\n\n* MAGLEV - used as a drop in replacement for the ring hash load balancer.\n           Maglev is not as stable as ring hash but has faster table lookup\n           build times and host selection times. For more information about\n           Maglev, refer to https://ai.google/research/pubs/pub44824\n\nThis field is applicable only when the 'load_balancing_scheme' is set to\nINTERNAL_MANAGED and the 'protocol' is set to HTTP, HTTPS, or HTTP2. Possible values: [\"ROUND_ROBIN\", \"LEAST_REQUEST\", \"RING_HASH\", \"RANDOM\", \"ORIGINAL_DESTINATION\", \"MAGLEV\"]"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Name of the resource. Provided by the client when the resource is\ncreated. The name must be 1-63 characters long, and comply with\nRFC1035. Specifically, the name must be 1-63 characters long and match\nthe regular expression '[a-z]([-a-z0-9]*[a-z0-9])?' which means the\nfirst character must be a lowercase letter, and all following\ncharacters must be a dash, lowercase letter, or digit, except the last\ncharacter, which cannot be a dash."
  type        = string
}

variable "network" {
  description = "(optional) - The URL of the network to which this backend service belongs.\nThis field can only be specified when the load balancing scheme is set to INTERNAL."
  type        = string
  default     = null
}

variable "port_name" {
  description = "(optional) - A named port on a backend instance group representing the port for\ncommunication to the backend VMs in that group. Required when the\nloadBalancingScheme is EXTERNAL, INTERNAL_MANAGED, or INTERNAL_SELF_MANAGED\nand the backends are instance groups. The named port must be defined on each\nbackend instance group. This parameter has no meaning if the backends are NEGs. API sets a\ndefault of \"http\" if not given.\nMust be omitted when the loadBalancingScheme is INTERNAL (Internal TCP/UDP Load Balancing)."
  type        = string
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "protocol" {
  description = "(optional) - The protocol this RegionBackendService uses to communicate with backends.\nThe default is HTTP. **NOTE**: HTTP2 is only valid for beta HTTP/2 load balancer\ntypes and may result in errors if used with the GA API. Possible values: [\"HTTP\", \"HTTPS\", \"HTTP2\", \"SSL\", \"TCP\", \"UDP\", \"GRPC\"]"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional) - The Region in which the created backend service should reside.\nIf it is not provided, the provider region is used."
  type        = string
  default     = null
}

variable "session_affinity" {
  description = "(optional) - Type of session affinity to use. The default is NONE. Session affinity is\nnot applicable if the protocol is UDP. Possible values: [\"NONE\", \"CLIENT_IP\", \"CLIENT_IP_PORT_PROTO\", \"CLIENT_IP_PROTO\", \"GENERATED_COOKIE\", \"HEADER_FIELD\", \"HTTP_COOKIE\"]"
  type        = string
  default     = null
}

variable "timeout_sec" {
  description = "(optional) - How many seconds to wait for the backend before considering it a\nfailed request. Default is 30 seconds. Valid range is [1, 86400]."
  type        = number
  default     = null
}

variable "backend" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      balancing_mode               = string
      capacity_scaler              = number
      description                  = string
      failover                     = bool
      group                        = string
      max_connections              = number
      max_connections_per_endpoint = number
      max_connections_per_instance = number
      max_rate                     = number
      max_rate_per_endpoint        = number
      max_rate_per_instance        = number
      max_utilization              = number
    }
  ))
  default = []
}

variable "cdn_policy" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      cache_key_policy = list(object(
        {
          include_host           = bool
          include_protocol       = bool
          include_query_string   = bool
          query_string_blacklist = set(string)
          query_string_whitelist = set(string)
        }
      ))
      cache_mode       = string
      client_ttl       = number
      default_ttl      = number
      max_ttl          = number
      negative_caching = bool
      negative_caching_policy = list(object(
        {
          code = number
          ttl  = number
        }
      ))
      serve_while_stale            = number
      signed_url_cache_max_age_sec = number
    }
  ))
  default = []
}

variable "circuit_breakers" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      connect_timeout = list(object(
        {
          nanos   = number
          seconds = number
        }
      ))
      max_connections             = number
      max_pending_requests        = number
      max_requests                = number
      max_requests_per_connection = number
      max_retries                 = number
    }
  ))
  default = []
}

variable "consistent_hash" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      http_cookie = list(object(
        {
          name = string
          path = string
          ttl = list(object(
            {
              nanos   = number
              seconds = number
            }
          ))
        }
      ))
      http_header_name  = string
      minimum_ring_size = number
    }
  ))
  default = []
}

variable "failover_policy" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      disable_connection_drain_on_failover = bool
      drop_traffic_if_unhealthy            = bool
      failover_ratio                       = number
    }
  ))
  default = []
}

variable "log_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      enable      = bool
      sample_rate = number
    }
  ))
  default = []
}

variable "outlier_detection" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      base_ejection_time = list(object(
        {
          nanos   = number
          seconds = number
        }
      ))
      consecutive_errors                    = number
      consecutive_gateway_failure           = number
      enforcing_consecutive_errors          = number
      enforcing_consecutive_gateway_failure = number
      enforcing_success_rate                = number
      interval = list(object(
        {
          nanos   = number
          seconds = number
        }
      ))
      max_ejection_percent        = number
      success_rate_minimum_hosts  = number
      success_rate_request_volume = number
      success_rate_stdev_factor   = number
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
resource "google_compute_region_backend_service" "this" {
  # affinity_cookie_ttl_sec - (optional) is a type of number
  affinity_cookie_ttl_sec = var.affinity_cookie_ttl_sec
  # connection_draining_timeout_sec - (optional) is a type of number
  connection_draining_timeout_sec = var.connection_draining_timeout_sec
  # description - (optional) is a type of string
  description = var.description
  # enable_cdn - (optional) is a type of bool
  enable_cdn = var.enable_cdn
  # health_checks - (optional) is a type of set of string
  health_checks = var.health_checks
  # load_balancing_scheme - (optional) is a type of string
  load_balancing_scheme = var.load_balancing_scheme
  # locality_lb_policy - (optional) is a type of string
  locality_lb_policy = var.locality_lb_policy
  # name - (required) is a type of string
  name = var.name
  # network - (optional) is a type of string
  network = var.network
  # port_name - (optional) is a type of string
  port_name = var.port_name
  # project - (optional) is a type of string
  project = var.project
  # protocol - (optional) is a type of string
  protocol = var.protocol
  # region - (optional) is a type of string
  region = var.region
  # session_affinity - (optional) is a type of string
  session_affinity = var.session_affinity
  # timeout_sec - (optional) is a type of number
  timeout_sec = var.timeout_sec

  dynamic "backend" {
    for_each = var.backend
    content {
      # balancing_mode - (optional) is a type of string
      balancing_mode = backend.value["balancing_mode"]
      # capacity_scaler - (optional) is a type of number
      capacity_scaler = backend.value["capacity_scaler"]
      # description - (optional) is a type of string
      description = backend.value["description"]
      # failover - (optional) is a type of bool
      failover = backend.value["failover"]
      # group - (required) is a type of string
      group = backend.value["group"]
      # max_connections - (optional) is a type of number
      max_connections = backend.value["max_connections"]
      # max_connections_per_endpoint - (optional) is a type of number
      max_connections_per_endpoint = backend.value["max_connections_per_endpoint"]
      # max_connections_per_instance - (optional) is a type of number
      max_connections_per_instance = backend.value["max_connections_per_instance"]
      # max_rate - (optional) is a type of number
      max_rate = backend.value["max_rate"]
      # max_rate_per_endpoint - (optional) is a type of number
      max_rate_per_endpoint = backend.value["max_rate_per_endpoint"]
      # max_rate_per_instance - (optional) is a type of number
      max_rate_per_instance = backend.value["max_rate_per_instance"]
      # max_utilization - (optional) is a type of number
      max_utilization = backend.value["max_utilization"]
    }
  }

  dynamic "cdn_policy" {
    for_each = var.cdn_policy
    content {
      # cache_mode - (optional) is a type of string
      cache_mode = cdn_policy.value["cache_mode"]
      # client_ttl - (optional) is a type of number
      client_ttl = cdn_policy.value["client_ttl"]
      # default_ttl - (optional) is a type of number
      default_ttl = cdn_policy.value["default_ttl"]
      # max_ttl - (optional) is a type of number
      max_ttl = cdn_policy.value["max_ttl"]
      # negative_caching - (optional) is a type of bool
      negative_caching = cdn_policy.value["negative_caching"]
      # serve_while_stale - (optional) is a type of number
      serve_while_stale = cdn_policy.value["serve_while_stale"]
      # signed_url_cache_max_age_sec - (optional) is a type of number
      signed_url_cache_max_age_sec = cdn_policy.value["signed_url_cache_max_age_sec"]

      dynamic "cache_key_policy" {
        for_each = cdn_policy.value.cache_key_policy
        content {
          # include_host - (optional) is a type of bool
          include_host = cache_key_policy.value["include_host"]
          # include_protocol - (optional) is a type of bool
          include_protocol = cache_key_policy.value["include_protocol"]
          # include_query_string - (optional) is a type of bool
          include_query_string = cache_key_policy.value["include_query_string"]
          # query_string_blacklist - (optional) is a type of set of string
          query_string_blacklist = cache_key_policy.value["query_string_blacklist"]
          # query_string_whitelist - (optional) is a type of set of string
          query_string_whitelist = cache_key_policy.value["query_string_whitelist"]
        }
      }

      dynamic "negative_caching_policy" {
        for_each = cdn_policy.value.negative_caching_policy
        content {
          # code - (optional) is a type of number
          code = negative_caching_policy.value["code"]
          # ttl - (optional) is a type of number
          ttl = negative_caching_policy.value["ttl"]
        }
      }

    }
  }

  dynamic "circuit_breakers" {
    for_each = var.circuit_breakers
    content {
      # max_connections - (optional) is a type of number
      max_connections = circuit_breakers.value["max_connections"]
      # max_pending_requests - (optional) is a type of number
      max_pending_requests = circuit_breakers.value["max_pending_requests"]
      # max_requests - (optional) is a type of number
      max_requests = circuit_breakers.value["max_requests"]
      # max_requests_per_connection - (optional) is a type of number
      max_requests_per_connection = circuit_breakers.value["max_requests_per_connection"]
      # max_retries - (optional) is a type of number
      max_retries = circuit_breakers.value["max_retries"]

      dynamic "connect_timeout" {
        for_each = circuit_breakers.value.connect_timeout
        content {
          # nanos - (optional) is a type of number
          nanos = connect_timeout.value["nanos"]
          # seconds - (required) is a type of number
          seconds = connect_timeout.value["seconds"]
        }
      }

    }
  }

  dynamic "consistent_hash" {
    for_each = var.consistent_hash
    content {
      # http_header_name - (optional) is a type of string
      http_header_name = consistent_hash.value["http_header_name"]
      # minimum_ring_size - (optional) is a type of number
      minimum_ring_size = consistent_hash.value["minimum_ring_size"]

      dynamic "http_cookie" {
        for_each = consistent_hash.value.http_cookie
        content {
          # name - (optional) is a type of string
          name = http_cookie.value["name"]
          # path - (optional) is a type of string
          path = http_cookie.value["path"]

          dynamic "ttl" {
            for_each = http_cookie.value.ttl
            content {
              # nanos - (optional) is a type of number
              nanos = ttl.value["nanos"]
              # seconds - (required) is a type of number
              seconds = ttl.value["seconds"]
            }
          }

        }
      }

    }
  }

  dynamic "failover_policy" {
    for_each = var.failover_policy
    content {
      # disable_connection_drain_on_failover - (optional) is a type of bool
      disable_connection_drain_on_failover = failover_policy.value["disable_connection_drain_on_failover"]
      # drop_traffic_if_unhealthy - (optional) is a type of bool
      drop_traffic_if_unhealthy = failover_policy.value["drop_traffic_if_unhealthy"]
      # failover_ratio - (optional) is a type of number
      failover_ratio = failover_policy.value["failover_ratio"]
    }
  }

  dynamic "log_config" {
    for_each = var.log_config
    content {
      # enable - (optional) is a type of bool
      enable = log_config.value["enable"]
      # sample_rate - (optional) is a type of number
      sample_rate = log_config.value["sample_rate"]
    }
  }

  dynamic "outlier_detection" {
    for_each = var.outlier_detection
    content {
      # consecutive_errors - (optional) is a type of number
      consecutive_errors = outlier_detection.value["consecutive_errors"]
      # consecutive_gateway_failure - (optional) is a type of number
      consecutive_gateway_failure = outlier_detection.value["consecutive_gateway_failure"]
      # enforcing_consecutive_errors - (optional) is a type of number
      enforcing_consecutive_errors = outlier_detection.value["enforcing_consecutive_errors"]
      # enforcing_consecutive_gateway_failure - (optional) is a type of number
      enforcing_consecutive_gateway_failure = outlier_detection.value["enforcing_consecutive_gateway_failure"]
      # enforcing_success_rate - (optional) is a type of number
      enforcing_success_rate = outlier_detection.value["enforcing_success_rate"]
      # max_ejection_percent - (optional) is a type of number
      max_ejection_percent = outlier_detection.value["max_ejection_percent"]
      # success_rate_minimum_hosts - (optional) is a type of number
      success_rate_minimum_hosts = outlier_detection.value["success_rate_minimum_hosts"]
      # success_rate_request_volume - (optional) is a type of number
      success_rate_request_volume = outlier_detection.value["success_rate_request_volume"]
      # success_rate_stdev_factor - (optional) is a type of number
      success_rate_stdev_factor = outlier_detection.value["success_rate_stdev_factor"]

      dynamic "base_ejection_time" {
        for_each = outlier_detection.value.base_ejection_time
        content {
          # nanos - (optional) is a type of number
          nanos = base_ejection_time.value["nanos"]
          # seconds - (required) is a type of number
          seconds = base_ejection_time.value["seconds"]
        }
      }

      dynamic "interval" {
        for_each = outlier_detection.value.interval
        content {
          # nanos - (optional) is a type of number
          nanos = interval.value["nanos"]
          # seconds - (required) is a type of number
          seconds = interval.value["seconds"]
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
output "creation_timestamp" {
  description = "returns a string"
  value       = google_compute_region_backend_service.this.creation_timestamp
}

output "fingerprint" {
  description = "returns a string"
  value       = google_compute_region_backend_service.this.fingerprint
}

output "id" {
  description = "returns a string"
  value       = google_compute_region_backend_service.this.id
}

output "port_name" {
  description = "returns a string"
  value       = google_compute_region_backend_service.this.port_name
}

output "project" {
  description = "returns a string"
  value       = google_compute_region_backend_service.this.project
}

output "protocol" {
  description = "returns a string"
  value       = google_compute_region_backend_service.this.protocol
}

output "region" {
  description = "returns a string"
  value       = google_compute_region_backend_service.this.region
}

output "self_link" {
  description = "returns a string"
  value       = google_compute_region_backend_service.this.self_link
}

output "session_affinity" {
  description = "returns a string"
  value       = google_compute_region_backend_service.this.session_affinity
}

output "timeout_sec" {
  description = "returns a number"
  value       = google_compute_region_backend_service.this.timeout_sec
}

output "this" {
  value = google_compute_region_backend_service.this
}
```

[top](#index)