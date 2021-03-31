# oci

[back](../)

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "oci" {
  version = "4.19.0"

  # auth - (optional) is a type of string
  auth = null
  # config_file_profile - (optional) is a type of string
  config_file_profile = null
  # disable_auto_retries - (optional) is a type of bool
  disable_auto_retries = null
  # fingerprint - (optional) is a type of string
  fingerprint = null
  # private_key - (optional) is a type of string
  private_key = null
  # private_key_password - (optional) is a type of string
  private_key_password = null
  # private_key_path - (optional) is a type of string
  private_key_path = null
  # region - (optional) is a type of string
  region = null
  # retry_duration_seconds - (optional) is a type of number
  retry_duration_seconds = null
  # tenancy_ocid - (optional) is a type of string
  tenancy_ocid = null
  # user_ocid - (optional) is a type of string
  user_ocid = null
}
```

[top](#index)

### Resources


- [oci_analytics_analytics_instance](./r/oci_analytics_analytics_instance.md)

- [oci_analytics_analytics_instance_private_access_channel](./r/oci_analytics_analytics_instance_private_access_channel.md)

- [oci_analytics_analytics_instance_vanity_url](./r/oci_analytics_analytics_instance_vanity_url.md)

- [oci_apigateway_api](./r/oci_apigateway_api.md)

- [oci_apigateway_certificate](./r/oci_apigateway_certificate.md)

- [oci_apigateway_deployment](./r/oci_apigateway_deployment.md)

- [oci_apigateway_gateway](./r/oci_apigateway_gateway.md)

- [oci_artifacts_container_configuration](./r/oci_artifacts_container_configuration.md)

- [oci_artifacts_container_repository](./r/oci_artifacts_container_repository.md)

- [oci_audit_configuration](./r/oci_audit_configuration.md)

- [oci_autoscaling_auto_scaling_configuration](./r/oci_autoscaling_auto_scaling_configuration.md)

- [oci_bds_auto_scaling_configuration](./r/oci_bds_auto_scaling_configuration.md)

- [oci_bds_bds_instance](./r/oci_bds_bds_instance.md)

- [oci_blockchain_blockchain_platform](./r/oci_blockchain_blockchain_platform.md)

- [oci_blockchain_osn](./r/oci_blockchain_osn.md)

- [oci_blockchain_peer](./r/oci_blockchain_peer.md)

- [oci_budget_alert_rule](./r/oci_budget_alert_rule.md)

- [oci_budget_budget](./r/oci_budget_budget.md)

- [oci_cloud_guard_cloud_guard_configuration](./r/oci_cloud_guard_cloud_guard_configuration.md)

- [oci_cloud_guard_detector_recipe](./r/oci_cloud_guard_detector_recipe.md)

- [oci_cloud_guard_managed_list](./r/oci_cloud_guard_managed_list.md)

- [oci_cloud_guard_responder_recipe](./r/oci_cloud_guard_responder_recipe.md)

- [oci_cloud_guard_target](./r/oci_cloud_guard_target.md)

- [oci_containerengine_cluster](./r/oci_containerengine_cluster.md)

- [oci_containerengine_node_pool](./r/oci_containerengine_node_pool.md)

- [oci_core_app_catalog_listing_resource_version_agreement](./r/oci_core_app_catalog_listing_resource_version_agreement.md)

- [oci_core_app_catalog_subscription](./r/oci_core_app_catalog_subscription.md)

- [oci_core_boot_volume](./r/oci_core_boot_volume.md)

- [oci_core_boot_volume_backup](./r/oci_core_boot_volume_backup.md)

- [oci_core_cluster_network](./r/oci_core_cluster_network.md)

- [oci_core_compute_capacity_reservation](./r/oci_core_compute_capacity_reservation.md)

- [oci_core_compute_image_capability_schema](./r/oci_core_compute_image_capability_schema.md)

- [oci_core_console_history](./r/oci_core_console_history.md)

- [oci_core_cpe](./r/oci_core_cpe.md)

- [oci_core_cross_connect](./r/oci_core_cross_connect.md)

- [oci_core_cross_connect_group](./r/oci_core_cross_connect_group.md)

- [oci_core_dedicated_vm_host](./r/oci_core_dedicated_vm_host.md)

- [oci_core_default_dhcp_options](./r/oci_core_default_dhcp_options.md)

- [oci_core_default_route_table](./r/oci_core_default_route_table.md)

- [oci_core_default_security_list](./r/oci_core_default_security_list.md)

- [oci_core_dhcp_options](./r/oci_core_dhcp_options.md)

- [oci_core_drg](./r/oci_core_drg.md)

- [oci_core_drg_attachment](./r/oci_core_drg_attachment.md)

- [oci_core_image](./r/oci_core_image.md)

- [oci_core_instance](./r/oci_core_instance.md)

- [oci_core_instance_configuration](./r/oci_core_instance_configuration.md)

- [oci_core_instance_console_connection](./r/oci_core_instance_console_connection.md)

- [oci_core_instance_pool](./r/oci_core_instance_pool.md)

- [oci_core_instance_pool_instance](./r/oci_core_instance_pool_instance.md)

- [oci_core_internet_gateway](./r/oci_core_internet_gateway.md)

- [oci_core_ipsec](./r/oci_core_ipsec.md)

- [oci_core_ipsec_connection_tunnel_management](./r/oci_core_ipsec_connection_tunnel_management.md)

- [oci_core_listing_resource_version_agreement](./r/oci_core_listing_resource_version_agreement.md)

- [oci_core_local_peering_gateway](./r/oci_core_local_peering_gateway.md)

- [oci_core_nat_gateway](./r/oci_core_nat_gateway.md)

- [oci_core_network_security_group](./r/oci_core_network_security_group.md)

- [oci_core_network_security_group_security_rule](./r/oci_core_network_security_group_security_rule.md)

- [oci_core_private_ip](./r/oci_core_private_ip.md)

- [oci_core_public_ip](./r/oci_core_public_ip.md)

- [oci_core_public_ip_pool](./r/oci_core_public_ip_pool.md)

- [oci_core_public_ip_pool_capacity](./r/oci_core_public_ip_pool_capacity.md)

- [oci_core_remote_peering_connection](./r/oci_core_remote_peering_connection.md)

- [oci_core_route_table](./r/oci_core_route_table.md)

- [oci_core_route_table_attachment](./r/oci_core_route_table_attachment.md)

- [oci_core_security_list](./r/oci_core_security_list.md)

- [oci_core_service_gateway](./r/oci_core_service_gateway.md)

- [oci_core_shape_management](./r/oci_core_shape_management.md)

- [oci_core_subnet](./r/oci_core_subnet.md)

- [oci_core_vcn](./r/oci_core_vcn.md)

- [oci_core_virtual_circuit](./r/oci_core_virtual_circuit.md)

- [oci_core_virtual_network](./r/oci_core_virtual_network.md)

- [oci_core_vlan](./r/oci_core_vlan.md)

- [oci_core_vnic_attachment](./r/oci_core_vnic_attachment.md)

- [oci_core_volume](./r/oci_core_volume.md)

- [oci_core_volume_attachment](./r/oci_core_volume_attachment.md)

- [oci_core_volume_backup](./r/oci_core_volume_backup.md)

- [oci_core_volume_backup_policy](./r/oci_core_volume_backup_policy.md)

- [oci_core_volume_backup_policy_assignment](./r/oci_core_volume_backup_policy_assignment.md)

- [oci_core_volume_group](./r/oci_core_volume_group.md)

- [oci_core_volume_group_backup](./r/oci_core_volume_group_backup.md)

- [oci_data_safe_data_safe_configuration](./r/oci_data_safe_data_safe_configuration.md)

- [oci_data_safe_data_safe_private_endpoint](./r/oci_data_safe_data_safe_private_endpoint.md)

- [oci_data_safe_on_prem_connector](./r/oci_data_safe_on_prem_connector.md)

- [oci_database_autonomous_container_database](./r/oci_database_autonomous_container_database.md)

- [oci_database_autonomous_container_database_dataguard_association_operation](./r/oci_database_autonomous_container_database_dataguard_association_operation.md)

- [oci_database_autonomous_database](./r/oci_database_autonomous_database.md)

- [oci_database_autonomous_database_backup](./r/oci_database_autonomous_database_backup.md)

- [oci_database_autonomous_database_instance_wallet_management](./r/oci_database_autonomous_database_instance_wallet_management.md)

- [oci_database_autonomous_database_regional_wallet_management](./r/oci_database_autonomous_database_regional_wallet_management.md)

- [oci_database_autonomous_database_wallet](./r/oci_database_autonomous_database_wallet.md)

- [oci_database_autonomous_exadata_infrastructure](./r/oci_database_autonomous_exadata_infrastructure.md)

- [oci_database_autonomous_vm_cluster](./r/oci_database_autonomous_vm_cluster.md)

- [oci_database_backup](./r/oci_database_backup.md)

- [oci_database_backup_destination](./r/oci_database_backup_destination.md)

- [oci_database_cloud_exadata_infrastructure](./r/oci_database_cloud_exadata_infrastructure.md)

- [oci_database_cloud_vm_cluster](./r/oci_database_cloud_vm_cluster.md)

- [oci_database_data_guard_association](./r/oci_database_data_guard_association.md)

- [oci_database_database](./r/oci_database_database.md)

- [oci_database_database_software_image](./r/oci_database_database_software_image.md)

- [oci_database_database_upgrade](./r/oci_database_database_upgrade.md)

- [oci_database_db_home](./r/oci_database_db_home.md)

- [oci_database_db_node_console_connection](./r/oci_database_db_node_console_connection.md)

- [oci_database_db_system](./r/oci_database_db_system.md)

- [oci_database_exadata_infrastructure](./r/oci_database_exadata_infrastructure.md)

- [oci_database_exadata_iorm_config](./r/oci_database_exadata_iorm_config.md)

- [oci_database_external_container_database](./r/oci_database_external_container_database.md)

- [oci_database_external_container_database_management](./r/oci_database_external_container_database_management.md)

- [oci_database_external_database_connector](./r/oci_database_external_database_connector.md)

- [oci_database_external_non_container_database](./r/oci_database_external_non_container_database.md)

- [oci_database_external_non_container_database_management](./r/oci_database_external_non_container_database_management.md)

- [oci_database_external_pluggable_database](./r/oci_database_external_pluggable_database.md)

- [oci_database_external_pluggable_database_management](./r/oci_database_external_pluggable_database_management.md)

- [oci_database_key_store](./r/oci_database_key_store.md)

- [oci_database_maintenance_run](./r/oci_database_maintenance_run.md)

- [oci_database_management_managed_database_group](./r/oci_database_management_managed_database_group.md)

- [oci_database_migration](./r/oci_database_migration.md)

- [oci_database_vm_cluster](./r/oci_database_vm_cluster.md)

- [oci_database_vm_cluster_network](./r/oci_database_vm_cluster_network.md)

- [oci_datacatalog_catalog](./r/oci_datacatalog_catalog.md)

- [oci_datacatalog_catalog_private_endpoint](./r/oci_datacatalog_catalog_private_endpoint.md)

- [oci_datacatalog_connection](./r/oci_datacatalog_connection.md)

- [oci_datacatalog_data_asset](./r/oci_datacatalog_data_asset.md)

- [oci_dataflow_application](./r/oci_dataflow_application.md)

- [oci_dataflow_invoke_run](./r/oci_dataflow_invoke_run.md)

- [oci_dataflow_private_endpoint](./r/oci_dataflow_private_endpoint.md)

- [oci_dataintegration_workspace](./r/oci_dataintegration_workspace.md)

- [oci_datascience_model](./r/oci_datascience_model.md)

- [oci_datascience_model_deployment](./r/oci_datascience_model_deployment.md)

- [oci_datascience_model_provenance](./r/oci_datascience_model_provenance.md)

- [oci_datascience_notebook_session](./r/oci_datascience_notebook_session.md)

- [oci_datascience_project](./r/oci_datascience_project.md)

- [oci_dns_record](./r/oci_dns_record.md)

- [oci_dns_resolver](./r/oci_dns_resolver.md)

- [oci_dns_resolver_endpoint](./r/oci_dns_resolver_endpoint.md)

- [oci_dns_rrset](./r/oci_dns_rrset.md)

- [oci_dns_steering_policy](./r/oci_dns_steering_policy.md)

- [oci_dns_steering_policy_attachment](./r/oci_dns_steering_policy_attachment.md)

- [oci_dns_tsig_key](./r/oci_dns_tsig_key.md)

- [oci_dns_view](./r/oci_dns_view.md)

- [oci_dns_zone](./r/oci_dns_zone.md)

- [oci_email_sender](./r/oci_email_sender.md)

- [oci_email_suppression](./r/oci_email_suppression.md)

- [oci_events_rule](./r/oci_events_rule.md)

- [oci_file_storage_export](./r/oci_file_storage_export.md)

- [oci_file_storage_export_set](./r/oci_file_storage_export_set.md)

- [oci_file_storage_file_system](./r/oci_file_storage_file_system.md)

- [oci_file_storage_mount_target](./r/oci_file_storage_mount_target.md)

- [oci_file_storage_snapshot](./r/oci_file_storage_snapshot.md)

- [oci_functions_application](./r/oci_functions_application.md)

- [oci_functions_function](./r/oci_functions_function.md)

- [oci_functions_invoke_function](./r/oci_functions_invoke_function.md)

- [oci_golden_gate_database_registration](./r/oci_golden_gate_database_registration.md)

- [oci_golden_gate_deployment](./r/oci_golden_gate_deployment.md)

- [oci_golden_gate_deployment_backup](./r/oci_golden_gate_deployment_backup.md)

- [oci_health_checks_http_monitor](./r/oci_health_checks_http_monitor.md)

- [oci_health_checks_http_probe](./r/oci_health_checks_http_probe.md)

- [oci_health_checks_ping_monitor](./r/oci_health_checks_ping_monitor.md)

- [oci_health_checks_ping_probe](./r/oci_health_checks_ping_probe.md)

- [oci_identity_api_key](./r/oci_identity_api_key.md)

- [oci_identity_auth_token](./r/oci_identity_auth_token.md)

- [oci_identity_authentication_policy](./r/oci_identity_authentication_policy.md)

- [oci_identity_compartment](./r/oci_identity_compartment.md)

- [oci_identity_customer_secret_key](./r/oci_identity_customer_secret_key.md)

- [oci_identity_dynamic_group](./r/oci_identity_dynamic_group.md)

- [oci_identity_group](./r/oci_identity_group.md)

- [oci_identity_identity_provider](./r/oci_identity_identity_provider.md)

- [oci_identity_idp_group_mapping](./r/oci_identity_idp_group_mapping.md)

- [oci_identity_network_source](./r/oci_identity_network_source.md)

- [oci_identity_policy](./r/oci_identity_policy.md)

- [oci_identity_smtp_credential](./r/oci_identity_smtp_credential.md)

- [oci_identity_swift_password](./r/oci_identity_swift_password.md)

- [oci_identity_tag](./r/oci_identity_tag.md)

- [oci_identity_tag_default](./r/oci_identity_tag_default.md)

- [oci_identity_tag_namespace](./r/oci_identity_tag_namespace.md)

- [oci_identity_ui_password](./r/oci_identity_ui_password.md)

- [oci_identity_user](./r/oci_identity_user.md)

- [oci_identity_user_capabilities_management](./r/oci_identity_user_capabilities_management.md)

- [oci_identity_user_group_membership](./r/oci_identity_user_group_membership.md)

- [oci_integration_integration_instance](./r/oci_integration_integration_instance.md)

- [oci_kms_encrypted_data](./r/oci_kms_encrypted_data.md)

- [oci_kms_generated_key](./r/oci_kms_generated_key.md)

- [oci_kms_key](./r/oci_kms_key.md)

- [oci_kms_key_version](./r/oci_kms_key_version.md)

- [oci_kms_sign](./r/oci_kms_sign.md)

- [oci_kms_vault](./r/oci_kms_vault.md)

- [oci_kms_verify](./r/oci_kms_verify.md)

- [oci_limits_quota](./r/oci_limits_quota.md)

- [oci_load_balancer](./r/oci_load_balancer.md)

- [oci_load_balancer_backend](./r/oci_load_balancer_backend.md)

- [oci_load_balancer_backend_set](./r/oci_load_balancer_backend_set.md)

- [oci_load_balancer_backendset](./r/oci_load_balancer_backendset.md)

- [oci_load_balancer_certificate](./r/oci_load_balancer_certificate.md)

- [oci_load_balancer_hostname](./r/oci_load_balancer_hostname.md)

- [oci_load_balancer_listener](./r/oci_load_balancer_listener.md)

- [oci_load_balancer_load_balancer](./r/oci_load_balancer_load_balancer.md)

- [oci_load_balancer_load_balancer_routing_policy](./r/oci_load_balancer_load_balancer_routing_policy.md)

- [oci_load_balancer_path_route_set](./r/oci_load_balancer_path_route_set.md)

- [oci_load_balancer_rule_set](./r/oci_load_balancer_rule_set.md)

- [oci_load_balancer_ssl_cipher_suite](./r/oci_load_balancer_ssl_cipher_suite.md)

- [oci_log_analytics_log_analytics_entity](./r/oci_log_analytics_log_analytics_entity.md)

- [oci_log_analytics_log_analytics_log_group](./r/oci_log_analytics_log_analytics_log_group.md)

- [oci_log_analytics_namespace](./r/oci_log_analytics_namespace.md)

- [oci_logging_log](./r/oci_logging_log.md)

- [oci_logging_log_group](./r/oci_logging_log_group.md)

- [oci_logging_log_saved_search](./r/oci_logging_log_saved_search.md)

- [oci_logging_unified_agent_configuration](./r/oci_logging_unified_agent_configuration.md)

- [oci_management_agent_management_agent](./r/oci_management_agent_management_agent.md)

- [oci_management_agent_management_agent_install_key](./r/oci_management_agent_management_agent_install_key.md)

- [oci_management_dashboard_management_dashboards_import](./r/oci_management_dashboard_management_dashboards_import.md)

- [oci_marketplace_accepted_agreement](./r/oci_marketplace_accepted_agreement.md)

- [oci_marketplace_listing_package_agreement](./r/oci_marketplace_listing_package_agreement.md)

- [oci_marketplace_publication](./r/oci_marketplace_publication.md)

- [oci_metering_computation_query](./r/oci_metering_computation_query.md)

- [oci_metering_computation_usage](./r/oci_metering_computation_usage.md)

- [oci_monitoring_alarm](./r/oci_monitoring_alarm.md)

- [oci_mysql_analytics_cluster](./r/oci_mysql_analytics_cluster.md)

- [oci_mysql_channel](./r/oci_mysql_channel.md)

- [oci_mysql_heat_wave_cluster](./r/oci_mysql_heat_wave_cluster.md)

- [oci_mysql_mysql_backup](./r/oci_mysql_mysql_backup.md)

- [oci_mysql_mysql_db_system](./r/oci_mysql_mysql_db_system.md)

- [oci_network_load_balancer_backend](./r/oci_network_load_balancer_backend.md)

- [oci_network_load_balancer_backend_set](./r/oci_network_load_balancer_backend_set.md)

- [oci_network_load_balancer_listener](./r/oci_network_load_balancer_listener.md)

- [oci_network_load_balancer_network_load_balancer](./r/oci_network_load_balancer_network_load_balancer.md)

- [oci_nosql_index](./r/oci_nosql_index.md)

- [oci_nosql_table](./r/oci_nosql_table.md)

- [oci_objectstorage_bucket](./r/oci_objectstorage_bucket.md)

- [oci_objectstorage_namespace_metadata](./r/oci_objectstorage_namespace_metadata.md)

- [oci_objectstorage_object](./r/oci_objectstorage_object.md)

- [oci_objectstorage_object_lifecycle_policy](./r/oci_objectstorage_object_lifecycle_policy.md)

- [oci_objectstorage_preauthrequest](./r/oci_objectstorage_preauthrequest.md)

- [oci_objectstorage_replication_policy](./r/oci_objectstorage_replication_policy.md)

- [oci_oce_oce_instance](./r/oci_oce_oce_instance.md)

- [oci_ocvp_esxi_host](./r/oci_ocvp_esxi_host.md)

- [oci_ocvp_sddc](./r/oci_ocvp_sddc.md)

- [oci_oda_oda_instance](./r/oci_oda_oda_instance.md)

- [oci_ons_notification_topic](./r/oci_ons_notification_topic.md)

- [oci_ons_subscription](./r/oci_ons_subscription.md)

- [oci_optimizer_enrollment_status](./r/oci_optimizer_enrollment_status.md)

- [oci_optimizer_profile](./r/oci_optimizer_profile.md)

- [oci_optimizer_recommendation](./r/oci_optimizer_recommendation.md)

- [oci_optimizer_resource_action](./r/oci_optimizer_resource_action.md)

- [oci_osmanagement_managed_instance_group](./r/oci_osmanagement_managed_instance_group.md)

- [oci_osmanagement_managed_instance_management](./r/oci_osmanagement_managed_instance_management.md)

- [oci_osmanagement_software_source](./r/oci_osmanagement_software_source.md)

- [oci_sch_service_connector](./r/oci_sch_service_connector.md)

- [oci_streaming_connect_harness](./r/oci_streaming_connect_harness.md)

- [oci_streaming_stream](./r/oci_streaming_stream.md)

- [oci_streaming_stream_pool](./r/oci_streaming_stream_pool.md)

- [oci_waas_address_list](./r/oci_waas_address_list.md)

- [oci_waas_certificate](./r/oci_waas_certificate.md)

- [oci_waas_custom_protection_rule](./r/oci_waas_custom_protection_rule.md)

- [oci_waas_http_redirect](./r/oci_waas_http_redirect.md)

- [oci_waas_protection_rule](./r/oci_waas_protection_rule.md)

- [oci_waas_purge_cache](./r/oci_waas_purge_cache.md)

- [oci_waas_waas_policy](./r/oci_waas_waas_policy.md)


[top](#index)

### Datasources


- [oci_analytics_analytics_instance](./d/oci_analytics_analytics_instance.md)

- [oci_analytics_analytics_instance_private_access_channel](./d/oci_analytics_analytics_instance_private_access_channel.md)

- [oci_analytics_analytics_instances](./d/oci_analytics_analytics_instances.md)

- [oci_apigateway_api](./d/oci_apigateway_api.md)

- [oci_apigateway_api_content](./d/oci_apigateway_api_content.md)

- [oci_apigateway_api_deployment_specification](./d/oci_apigateway_api_deployment_specification.md)

- [oci_apigateway_api_validation](./d/oci_apigateway_api_validation.md)

- [oci_apigateway_apis](./d/oci_apigateway_apis.md)

- [oci_apigateway_certificate](./d/oci_apigateway_certificate.md)

- [oci_apigateway_certificates](./d/oci_apigateway_certificates.md)

- [oci_apigateway_deployment](./d/oci_apigateway_deployment.md)

- [oci_apigateway_deployments](./d/oci_apigateway_deployments.md)

- [oci_apigateway_gateway](./d/oci_apigateway_gateway.md)

- [oci_apigateway_gateways](./d/oci_apigateway_gateways.md)

- [oci_artifacts_container_configuration](./d/oci_artifacts_container_configuration.md)

- [oci_artifacts_container_repositories](./d/oci_artifacts_container_repositories.md)

- [oci_artifacts_container_repository](./d/oci_artifacts_container_repository.md)

- [oci_audit_configuration](./d/oci_audit_configuration.md)

- [oci_audit_events](./d/oci_audit_events.md)

- [oci_autoscaling_auto_scaling_configuration](./d/oci_autoscaling_auto_scaling_configuration.md)

- [oci_autoscaling_auto_scaling_configurations](./d/oci_autoscaling_auto_scaling_configurations.md)

- [oci_bds_auto_scaling_configuration](./d/oci_bds_auto_scaling_configuration.md)

- [oci_bds_auto_scaling_configurations](./d/oci_bds_auto_scaling_configurations.md)

- [oci_bds_bds_instance](./d/oci_bds_bds_instance.md)

- [oci_bds_bds_instances](./d/oci_bds_bds_instances.md)

- [oci_blockchain_blockchain_platform](./d/oci_blockchain_blockchain_platform.md)

- [oci_blockchain_blockchain_platforms](./d/oci_blockchain_blockchain_platforms.md)

- [oci_blockchain_osn](./d/oci_blockchain_osn.md)

- [oci_blockchain_osns](./d/oci_blockchain_osns.md)

- [oci_blockchain_peer](./d/oci_blockchain_peer.md)

- [oci_blockchain_peers](./d/oci_blockchain_peers.md)

- [oci_budget_alert_rule](./d/oci_budget_alert_rule.md)

- [oci_budget_alert_rules](./d/oci_budget_alert_rules.md)

- [oci_budget_budget](./d/oci_budget_budget.md)

- [oci_budget_budgets](./d/oci_budget_budgets.md)

- [oci_cloud_guard_cloud_guard_configuration](./d/oci_cloud_guard_cloud_guard_configuration.md)

- [oci_cloud_guard_detector_recipe](./d/oci_cloud_guard_detector_recipe.md)

- [oci_cloud_guard_detector_recipes](./d/oci_cloud_guard_detector_recipes.md)

- [oci_cloud_guard_managed_list](./d/oci_cloud_guard_managed_list.md)

- [oci_cloud_guard_managed_lists](./d/oci_cloud_guard_managed_lists.md)

- [oci_cloud_guard_responder_recipe](./d/oci_cloud_guard_responder_recipe.md)

- [oci_cloud_guard_responder_recipes](./d/oci_cloud_guard_responder_recipes.md)

- [oci_cloud_guard_target](./d/oci_cloud_guard_target.md)

- [oci_cloud_guard_targets](./d/oci_cloud_guard_targets.md)

- [oci_computeinstanceagent_instance_agent_plugin](./d/oci_computeinstanceagent_instance_agent_plugin.md)

- [oci_computeinstanceagent_instance_agent_plugins](./d/oci_computeinstanceagent_instance_agent_plugins.md)

- [oci_computeinstanceagent_instance_available_plugins](./d/oci_computeinstanceagent_instance_available_plugins.md)

- [oci_containerengine_cluster_kube_config](./d/oci_containerengine_cluster_kube_config.md)

- [oci_containerengine_cluster_option](./d/oci_containerengine_cluster_option.md)

- [oci_containerengine_clusters](./d/oci_containerengine_clusters.md)

- [oci_containerengine_node_pool](./d/oci_containerengine_node_pool.md)

- [oci_containerengine_node_pool_option](./d/oci_containerengine_node_pool_option.md)

- [oci_containerengine_node_pools](./d/oci_containerengine_node_pools.md)

- [oci_containerengine_work_request_errors](./d/oci_containerengine_work_request_errors.md)

- [oci_containerengine_work_request_log_entries](./d/oci_containerengine_work_request_log_entries.md)

- [oci_containerengine_work_requests](./d/oci_containerengine_work_requests.md)

- [oci_core_app_catalog_listing](./d/oci_core_app_catalog_listing.md)

- [oci_core_app_catalog_listing_resource_version](./d/oci_core_app_catalog_listing_resource_version.md)

- [oci_core_app_catalog_listing_resource_versions](./d/oci_core_app_catalog_listing_resource_versions.md)

- [oci_core_app_catalog_listings](./d/oci_core_app_catalog_listings.md)

- [oci_core_app_catalog_subscriptions](./d/oci_core_app_catalog_subscriptions.md)

- [oci_core_boot_volume](./d/oci_core_boot_volume.md)

- [oci_core_boot_volume_attachments](./d/oci_core_boot_volume_attachments.md)

- [oci_core_boot_volume_backup](./d/oci_core_boot_volume_backup.md)

- [oci_core_boot_volume_backups](./d/oci_core_boot_volume_backups.md)

- [oci_core_boot_volumes](./d/oci_core_boot_volumes.md)

- [oci_core_byoip_allocated_ranges](./d/oci_core_byoip_allocated_ranges.md)

- [oci_core_byoip_range](./d/oci_core_byoip_range.md)

- [oci_core_byoip_ranges](./d/oci_core_byoip_ranges.md)

- [oci_core_cluster_network](./d/oci_core_cluster_network.md)

- [oci_core_cluster_network_instances](./d/oci_core_cluster_network_instances.md)

- [oci_core_cluster_networks](./d/oci_core_cluster_networks.md)

- [oci_core_compute_capacity_reservation](./d/oci_core_compute_capacity_reservation.md)

- [oci_core_compute_capacity_reservation_instance_shapes](./d/oci_core_compute_capacity_reservation_instance_shapes.md)

- [oci_core_compute_capacity_reservation_instances](./d/oci_core_compute_capacity_reservation_instances.md)

- [oci_core_compute_capacity_reservations](./d/oci_core_compute_capacity_reservations.md)

- [oci_core_compute_global_image_capability_schema](./d/oci_core_compute_global_image_capability_schema.md)

- [oci_core_compute_global_image_capability_schemas](./d/oci_core_compute_global_image_capability_schemas.md)

- [oci_core_compute_global_image_capability_schemas_version](./d/oci_core_compute_global_image_capability_schemas_version.md)

- [oci_core_compute_global_image_capability_schemas_versions](./d/oci_core_compute_global_image_capability_schemas_versions.md)

- [oci_core_compute_image_capability_schema](./d/oci_core_compute_image_capability_schema.md)

- [oci_core_compute_image_capability_schemas](./d/oci_core_compute_image_capability_schemas.md)

- [oci_core_console_histories](./d/oci_core_console_histories.md)

- [oci_core_console_history_data](./d/oci_core_console_history_data.md)

- [oci_core_cpe_device_shape](./d/oci_core_cpe_device_shape.md)

- [oci_core_cpe_device_shapes](./d/oci_core_cpe_device_shapes.md)

- [oci_core_cpes](./d/oci_core_cpes.md)

- [oci_core_cross_connect](./d/oci_core_cross_connect.md)

- [oci_core_cross_connect_group](./d/oci_core_cross_connect_group.md)

- [oci_core_cross_connect_groups](./d/oci_core_cross_connect_groups.md)

- [oci_core_cross_connect_locations](./d/oci_core_cross_connect_locations.md)

- [oci_core_cross_connect_port_speed_shapes](./d/oci_core_cross_connect_port_speed_shapes.md)

- [oci_core_cross_connect_status](./d/oci_core_cross_connect_status.md)

- [oci_core_cross_connects](./d/oci_core_cross_connects.md)

- [oci_core_dedicated_vm_host](./d/oci_core_dedicated_vm_host.md)

- [oci_core_dedicated_vm_host_instance_shapes](./d/oci_core_dedicated_vm_host_instance_shapes.md)

- [oci_core_dedicated_vm_host_shapes](./d/oci_core_dedicated_vm_host_shapes.md)

- [oci_core_dedicated_vm_hosts](./d/oci_core_dedicated_vm_hosts.md)

- [oci_core_dedicated_vm_hosts_instances](./d/oci_core_dedicated_vm_hosts_instances.md)

- [oci_core_dhcp_options](./d/oci_core_dhcp_options.md)

- [oci_core_drg_attachments](./d/oci_core_drg_attachments.md)

- [oci_core_drgs](./d/oci_core_drgs.md)

- [oci_core_fast_connect_provider_service](./d/oci_core_fast_connect_provider_service.md)

- [oci_core_fast_connect_provider_service_key](./d/oci_core_fast_connect_provider_service_key.md)

- [oci_core_fast_connect_provider_services](./d/oci_core_fast_connect_provider_services.md)

- [oci_core_image](./d/oci_core_image.md)

- [oci_core_image_shape](./d/oci_core_image_shape.md)

- [oci_core_image_shapes](./d/oci_core_image_shapes.md)

- [oci_core_images](./d/oci_core_images.md)

- [oci_core_instance](./d/oci_core_instance.md)

- [oci_core_instance_configuration](./d/oci_core_instance_configuration.md)

- [oci_core_instance_configurations](./d/oci_core_instance_configurations.md)

- [oci_core_instance_console_connections](./d/oci_core_instance_console_connections.md)

- [oci_core_instance_credentials](./d/oci_core_instance_credentials.md)

- [oci_core_instance_devices](./d/oci_core_instance_devices.md)

- [oci_core_instance_pool](./d/oci_core_instance_pool.md)

- [oci_core_instance_pool_instances](./d/oci_core_instance_pool_instances.md)

- [oci_core_instance_pool_load_balancer_attachment](./d/oci_core_instance_pool_load_balancer_attachment.md)

- [oci_core_instance_pools](./d/oci_core_instance_pools.md)

- [oci_core_instances](./d/oci_core_instances.md)

- [oci_core_internet_gateways](./d/oci_core_internet_gateways.md)

- [oci_core_ipsec_config](./d/oci_core_ipsec_config.md)

- [oci_core_ipsec_connection_tunnel](./d/oci_core_ipsec_connection_tunnel.md)

- [oci_core_ipsec_connection_tunnels](./d/oci_core_ipsec_connection_tunnels.md)

- [oci_core_ipsec_connections](./d/oci_core_ipsec_connections.md)

- [oci_core_ipsec_status](./d/oci_core_ipsec_status.md)

- [oci_core_letter_of_authority](./d/oci_core_letter_of_authority.md)

- [oci_core_listing_resource_version](./d/oci_core_listing_resource_version.md)

- [oci_core_listing_resource_versions](./d/oci_core_listing_resource_versions.md)

- [oci_core_local_peering_gateways](./d/oci_core_local_peering_gateways.md)

- [oci_core_nat_gateway](./d/oci_core_nat_gateway.md)

- [oci_core_nat_gateways](./d/oci_core_nat_gateways.md)

- [oci_core_network_security_group](./d/oci_core_network_security_group.md)

- [oci_core_network_security_group_security_rules](./d/oci_core_network_security_group_security_rules.md)

- [oci_core_network_security_group_vnics](./d/oci_core_network_security_group_vnics.md)

- [oci_core_network_security_groups](./d/oci_core_network_security_groups.md)

- [oci_core_peer_region_for_remote_peerings](./d/oci_core_peer_region_for_remote_peerings.md)

- [oci_core_private_ip](./d/oci_core_private_ip.md)

- [oci_core_private_ips](./d/oci_core_private_ips.md)

- [oci_core_public_ip](./d/oci_core_public_ip.md)

- [oci_core_public_ip_pool](./d/oci_core_public_ip_pool.md)

- [oci_core_public_ip_pools](./d/oci_core_public_ip_pools.md)

- [oci_core_public_ips](./d/oci_core_public_ips.md)

- [oci_core_remote_peering_connections](./d/oci_core_remote_peering_connections.md)

- [oci_core_route_tables](./d/oci_core_route_tables.md)

- [oci_core_security_lists](./d/oci_core_security_lists.md)

- [oci_core_service_gateways](./d/oci_core_service_gateways.md)

- [oci_core_services](./d/oci_core_services.md)

- [oci_core_shape](./d/oci_core_shape.md)

- [oci_core_shapes](./d/oci_core_shapes.md)

- [oci_core_subnet](./d/oci_core_subnet.md)

- [oci_core_subnets](./d/oci_core_subnets.md)

- [oci_core_vcn](./d/oci_core_vcn.md)

- [oci_core_vcn_dns_resolver_association](./d/oci_core_vcn_dns_resolver_association.md)

- [oci_core_vcns](./d/oci_core_vcns.md)

- [oci_core_virtual_circuit](./d/oci_core_virtual_circuit.md)

- [oci_core_virtual_circuit_bandwidth_shapes](./d/oci_core_virtual_circuit_bandwidth_shapes.md)

- [oci_core_virtual_circuit_public_prefixes](./d/oci_core_virtual_circuit_public_prefixes.md)

- [oci_core_virtual_circuits](./d/oci_core_virtual_circuits.md)

- [oci_core_virtual_networks](./d/oci_core_virtual_networks.md)

- [oci_core_vlan](./d/oci_core_vlan.md)

- [oci_core_vlans](./d/oci_core_vlans.md)

- [oci_core_vnic](./d/oci_core_vnic.md)

- [oci_core_vnic_attachments](./d/oci_core_vnic_attachments.md)

- [oci_core_volume](./d/oci_core_volume.md)

- [oci_core_volume_attachments](./d/oci_core_volume_attachments.md)

- [oci_core_volume_backup_policies](./d/oci_core_volume_backup_policies.md)

- [oci_core_volume_backup_policy_assignments](./d/oci_core_volume_backup_policy_assignments.md)

- [oci_core_volume_backups](./d/oci_core_volume_backups.md)

- [oci_core_volume_group_backups](./d/oci_core_volume_group_backups.md)

- [oci_core_volume_groups](./d/oci_core_volume_groups.md)

- [oci_core_volumes](./d/oci_core_volumes.md)

- [oci_data_safe_data_safe_configuration](./d/oci_data_safe_data_safe_configuration.md)

- [oci_data_safe_data_safe_private_endpoint](./d/oci_data_safe_data_safe_private_endpoint.md)

- [oci_data_safe_data_safe_private_endpoints](./d/oci_data_safe_data_safe_private_endpoints.md)

- [oci_data_safe_on_prem_connector](./d/oci_data_safe_on_prem_connector.md)

- [oci_data_safe_on_prem_connectors](./d/oci_data_safe_on_prem_connectors.md)

- [oci_database_autonomous_container_database](./d/oci_database_autonomous_container_database.md)

- [oci_database_autonomous_container_database_dataguard_association](./d/oci_database_autonomous_container_database_dataguard_association.md)

- [oci_database_autonomous_container_database_dataguard_associations](./d/oci_database_autonomous_container_database_dataguard_associations.md)

- [oci_database_autonomous_container_databases](./d/oci_database_autonomous_container_databases.md)

- [oci_database_autonomous_container_patches](./d/oci_database_autonomous_container_patches.md)

- [oci_database_autonomous_database](./d/oci_database_autonomous_database.md)

- [oci_database_autonomous_database_backup](./d/oci_database_autonomous_database_backup.md)

- [oci_database_autonomous_database_backups](./d/oci_database_autonomous_database_backups.md)

- [oci_database_autonomous_database_dataguard_association](./d/oci_database_autonomous_database_dataguard_association.md)

- [oci_database_autonomous_database_dataguard_associations](./d/oci_database_autonomous_database_dataguard_associations.md)

- [oci_database_autonomous_database_instance_wallet_management](./d/oci_database_autonomous_database_instance_wallet_management.md)

- [oci_database_autonomous_database_regional_wallet_management](./d/oci_database_autonomous_database_regional_wallet_management.md)

- [oci_database_autonomous_database_wallet](./d/oci_database_autonomous_database_wallet.md)

- [oci_database_autonomous_databases](./d/oci_database_autonomous_databases.md)

- [oci_database_autonomous_databases_clones](./d/oci_database_autonomous_databases_clones.md)

- [oci_database_autonomous_db_preview_versions](./d/oci_database_autonomous_db_preview_versions.md)

- [oci_database_autonomous_db_versions](./d/oci_database_autonomous_db_versions.md)

- [oci_database_autonomous_exadata_infrastructure](./d/oci_database_autonomous_exadata_infrastructure.md)

- [oci_database_autonomous_exadata_infrastructure_ocpu](./d/oci_database_autonomous_exadata_infrastructure_ocpu.md)

- [oci_database_autonomous_exadata_infrastructure_shapes](./d/oci_database_autonomous_exadata_infrastructure_shapes.md)

- [oci_database_autonomous_exadata_infrastructures](./d/oci_database_autonomous_exadata_infrastructures.md)

- [oci_database_autonomous_patch](./d/oci_database_autonomous_patch.md)

- [oci_database_autonomous_vm_cluster](./d/oci_database_autonomous_vm_cluster.md)

- [oci_database_autonomous_vm_clusters](./d/oci_database_autonomous_vm_clusters.md)

- [oci_database_backup_destination](./d/oci_database_backup_destination.md)

- [oci_database_backup_destinations](./d/oci_database_backup_destinations.md)

- [oci_database_backups](./d/oci_database_backups.md)

- [oci_database_cloud_exadata_infrastructure](./d/oci_database_cloud_exadata_infrastructure.md)

- [oci_database_cloud_exadata_infrastructures](./d/oci_database_cloud_exadata_infrastructures.md)

- [oci_database_cloud_vm_cluster](./d/oci_database_cloud_vm_cluster.md)

- [oci_database_cloud_vm_clusters](./d/oci_database_cloud_vm_clusters.md)

- [oci_database_data_guard_association](./d/oci_database_data_guard_association.md)

- [oci_database_data_guard_associations](./d/oci_database_data_guard_associations.md)

- [oci_database_database](./d/oci_database_database.md)

- [oci_database_database_software_image](./d/oci_database_database_software_image.md)

- [oci_database_database_software_images](./d/oci_database_database_software_images.md)

- [oci_database_database_upgrade_history_entries](./d/oci_database_database_upgrade_history_entries.md)

- [oci_database_database_upgrade_history_entry](./d/oci_database_database_upgrade_history_entry.md)

- [oci_database_databases](./d/oci_database_databases.md)

- [oci_database_db_home](./d/oci_database_db_home.md)

- [oci_database_db_home_patch_history_entries](./d/oci_database_db_home_patch_history_entries.md)

- [oci_database_db_home_patches](./d/oci_database_db_home_patches.md)

- [oci_database_db_homes](./d/oci_database_db_homes.md)

- [oci_database_db_node](./d/oci_database_db_node.md)

- [oci_database_db_node_console_connection](./d/oci_database_db_node_console_connection.md)

- [oci_database_db_node_console_connections](./d/oci_database_db_node_console_connections.md)

- [oci_database_db_nodes](./d/oci_database_db_nodes.md)

- [oci_database_db_system_patch_history_entries](./d/oci_database_db_system_patch_history_entries.md)

- [oci_database_db_system_patches](./d/oci_database_db_system_patches.md)

- [oci_database_db_system_shapes](./d/oci_database_db_system_shapes.md)

- [oci_database_db_systems](./d/oci_database_db_systems.md)

- [oci_database_db_versions](./d/oci_database_db_versions.md)

- [oci_database_exadata_infrastructure](./d/oci_database_exadata_infrastructure.md)

- [oci_database_exadata_infrastructure_download_config_file](./d/oci_database_exadata_infrastructure_download_config_file.md)

- [oci_database_exadata_infrastructures](./d/oci_database_exadata_infrastructures.md)

- [oci_database_exadata_iorm_config](./d/oci_database_exadata_iorm_config.md)

- [oci_database_external_container_database](./d/oci_database_external_container_database.md)

- [oci_database_external_container_databases](./d/oci_database_external_container_databases.md)

- [oci_database_external_database_connector](./d/oci_database_external_database_connector.md)

- [oci_database_external_database_connectors](./d/oci_database_external_database_connectors.md)

- [oci_database_external_non_container_database](./d/oci_database_external_non_container_database.md)

- [oci_database_external_non_container_databases](./d/oci_database_external_non_container_databases.md)

- [oci_database_external_pluggable_database](./d/oci_database_external_pluggable_database.md)

- [oci_database_external_pluggable_databases](./d/oci_database_external_pluggable_databases.md)

- [oci_database_flex_components](./d/oci_database_flex_components.md)

- [oci_database_gi_versions](./d/oci_database_gi_versions.md)

- [oci_database_key_store](./d/oci_database_key_store.md)

- [oci_database_key_stores](./d/oci_database_key_stores.md)

- [oci_database_maintenance_run](./d/oci_database_maintenance_run.md)

- [oci_database_maintenance_runs](./d/oci_database_maintenance_runs.md)

- [oci_database_management_managed_database](./d/oci_database_management_managed_database.md)

- [oci_database_management_managed_database_group](./d/oci_database_management_managed_database_group.md)

- [oci_database_management_managed_database_groups](./d/oci_database_management_managed_database_groups.md)

- [oci_database_management_managed_databases](./d/oci_database_management_managed_databases.md)

- [oci_database_vm_cluster](./d/oci_database_vm_cluster.md)

- [oci_database_vm_cluster_network](./d/oci_database_vm_cluster_network.md)

- [oci_database_vm_cluster_network_download_config_file](./d/oci_database_vm_cluster_network_download_config_file.md)

- [oci_database_vm_cluster_networks](./d/oci_database_vm_cluster_networks.md)

- [oci_database_vm_cluster_patch](./d/oci_database_vm_cluster_patch.md)

- [oci_database_vm_cluster_patch_history_entries](./d/oci_database_vm_cluster_patch_history_entries.md)

- [oci_database_vm_cluster_patch_history_entry](./d/oci_database_vm_cluster_patch_history_entry.md)

- [oci_database_vm_cluster_patches](./d/oci_database_vm_cluster_patches.md)

- [oci_database_vm_cluster_recommended_network](./d/oci_database_vm_cluster_recommended_network.md)

- [oci_database_vm_clusters](./d/oci_database_vm_clusters.md)

- [oci_datacatalog_catalog](./d/oci_datacatalog_catalog.md)

- [oci_datacatalog_catalog_private_endpoint](./d/oci_datacatalog_catalog_private_endpoint.md)

- [oci_datacatalog_catalog_private_endpoints](./d/oci_datacatalog_catalog_private_endpoints.md)

- [oci_datacatalog_catalog_type](./d/oci_datacatalog_catalog_type.md)

- [oci_datacatalog_catalog_types](./d/oci_datacatalog_catalog_types.md)

- [oci_datacatalog_catalogs](./d/oci_datacatalog_catalogs.md)

- [oci_datacatalog_connection](./d/oci_datacatalog_connection.md)

- [oci_datacatalog_connections](./d/oci_datacatalog_connections.md)

- [oci_datacatalog_data_asset](./d/oci_datacatalog_data_asset.md)

- [oci_datacatalog_data_assets](./d/oci_datacatalog_data_assets.md)

- [oci_dataflow_application](./d/oci_dataflow_application.md)

- [oci_dataflow_applications](./d/oci_dataflow_applications.md)

- [oci_dataflow_invoke_run](./d/oci_dataflow_invoke_run.md)

- [oci_dataflow_invoke_runs](./d/oci_dataflow_invoke_runs.md)

- [oci_dataflow_private_endpoint](./d/oci_dataflow_private_endpoint.md)

- [oci_dataflow_private_endpoints](./d/oci_dataflow_private_endpoints.md)

- [oci_dataflow_run_log](./d/oci_dataflow_run_log.md)

- [oci_dataflow_run_logs](./d/oci_dataflow_run_logs.md)

- [oci_dataintegration_workspace](./d/oci_dataintegration_workspace.md)

- [oci_dataintegration_workspaces](./d/oci_dataintegration_workspaces.md)

- [oci_datascience_model](./d/oci_datascience_model.md)

- [oci_datascience_model_deployment](./d/oci_datascience_model_deployment.md)

- [oci_datascience_model_deployment_shapes](./d/oci_datascience_model_deployment_shapes.md)

- [oci_datascience_model_deployments](./d/oci_datascience_model_deployments.md)

- [oci_datascience_model_provenance](./d/oci_datascience_model_provenance.md)

- [oci_datascience_models](./d/oci_datascience_models.md)

- [oci_datascience_notebook_session](./d/oci_datascience_notebook_session.md)

- [oci_datascience_notebook_session_shapes](./d/oci_datascience_notebook_session_shapes.md)

- [oci_datascience_notebook_sessions](./d/oci_datascience_notebook_sessions.md)

- [oci_datascience_project](./d/oci_datascience_project.md)

- [oci_datascience_projects](./d/oci_datascience_projects.md)

- [oci_dns_records](./d/oci_dns_records.md)

- [oci_dns_resolver](./d/oci_dns_resolver.md)

- [oci_dns_resolver_endpoint](./d/oci_dns_resolver_endpoint.md)

- [oci_dns_resolver_endpoints](./d/oci_dns_resolver_endpoints.md)

- [oci_dns_resolvers](./d/oci_dns_resolvers.md)

- [oci_dns_rrset](./d/oci_dns_rrset.md)

- [oci_dns_steering_policies](./d/oci_dns_steering_policies.md)

- [oci_dns_steering_policy](./d/oci_dns_steering_policy.md)

- [oci_dns_steering_policy_attachment](./d/oci_dns_steering_policy_attachment.md)

- [oci_dns_steering_policy_attachments](./d/oci_dns_steering_policy_attachments.md)

- [oci_dns_tsig_key](./d/oci_dns_tsig_key.md)

- [oci_dns_tsig_keys](./d/oci_dns_tsig_keys.md)

- [oci_dns_view](./d/oci_dns_view.md)

- [oci_dns_views](./d/oci_dns_views.md)

- [oci_dns_zones](./d/oci_dns_zones.md)

- [oci_email_sender](./d/oci_email_sender.md)

- [oci_email_senders](./d/oci_email_senders.md)

- [oci_email_suppression](./d/oci_email_suppression.md)

- [oci_email_suppressions](./d/oci_email_suppressions.md)

- [oci_events_rule](./d/oci_events_rule.md)

- [oci_events_rules](./d/oci_events_rules.md)

- [oci_file_storage_export_sets](./d/oci_file_storage_export_sets.md)

- [oci_file_storage_exports](./d/oci_file_storage_exports.md)

- [oci_file_storage_file_systems](./d/oci_file_storage_file_systems.md)

- [oci_file_storage_mount_targets](./d/oci_file_storage_mount_targets.md)

- [oci_file_storage_snapshot](./d/oci_file_storage_snapshot.md)

- [oci_file_storage_snapshots](./d/oci_file_storage_snapshots.md)

- [oci_functions_application](./d/oci_functions_application.md)

- [oci_functions_applications](./d/oci_functions_applications.md)

- [oci_functions_function](./d/oci_functions_function.md)

- [oci_functions_functions](./d/oci_functions_functions.md)

- [oci_golden_gate_database_registration](./d/oci_golden_gate_database_registration.md)

- [oci_golden_gate_database_registrations](./d/oci_golden_gate_database_registrations.md)

- [oci_golden_gate_deployment](./d/oci_golden_gate_deployment.md)

- [oci_golden_gate_deployment_backup](./d/oci_golden_gate_deployment_backup.md)

- [oci_golden_gate_deployment_backups](./d/oci_golden_gate_deployment_backups.md)

- [oci_golden_gate_deployments](./d/oci_golden_gate_deployments.md)

- [oci_health_checks_http_monitor](./d/oci_health_checks_http_monitor.md)

- [oci_health_checks_http_monitors](./d/oci_health_checks_http_monitors.md)

- [oci_health_checks_http_probe_results](./d/oci_health_checks_http_probe_results.md)

- [oci_health_checks_ping_monitor](./d/oci_health_checks_ping_monitor.md)

- [oci_health_checks_ping_monitors](./d/oci_health_checks_ping_monitors.md)

- [oci_health_checks_ping_probe_results](./d/oci_health_checks_ping_probe_results.md)

- [oci_health_checks_vantage_points](./d/oci_health_checks_vantage_points.md)

- [oci_identity_api_keys](./d/oci_identity_api_keys.md)

- [oci_identity_auth_tokens](./d/oci_identity_auth_tokens.md)

- [oci_identity_authentication_policy](./d/oci_identity_authentication_policy.md)

- [oci_identity_availability_domain](./d/oci_identity_availability_domain.md)

- [oci_identity_availability_domains](./d/oci_identity_availability_domains.md)

- [oci_identity_compartment](./d/oci_identity_compartment.md)

- [oci_identity_compartments](./d/oci_identity_compartments.md)

- [oci_identity_cost_tracking_tags](./d/oci_identity_cost_tracking_tags.md)

- [oci_identity_customer_secret_keys](./d/oci_identity_customer_secret_keys.md)

- [oci_identity_dynamic_groups](./d/oci_identity_dynamic_groups.md)

- [oci_identity_fault_domains](./d/oci_identity_fault_domains.md)

- [oci_identity_group](./d/oci_identity_group.md)

- [oci_identity_groups](./d/oci_identity_groups.md)

- [oci_identity_identity_provider_groups](./d/oci_identity_identity_provider_groups.md)

- [oci_identity_identity_providers](./d/oci_identity_identity_providers.md)

- [oci_identity_idp_group_mappings](./d/oci_identity_idp_group_mappings.md)

- [oci_identity_network_source](./d/oci_identity_network_source.md)

- [oci_identity_network_sources](./d/oci_identity_network_sources.md)

- [oci_identity_policies](./d/oci_identity_policies.md)

- [oci_identity_region_subscriptions](./d/oci_identity_region_subscriptions.md)

- [oci_identity_regions](./d/oci_identity_regions.md)

- [oci_identity_smtp_credentials](./d/oci_identity_smtp_credentials.md)

- [oci_identity_swift_passwords](./d/oci_identity_swift_passwords.md)

- [oci_identity_tag](./d/oci_identity_tag.md)

- [oci_identity_tag_default](./d/oci_identity_tag_default.md)

- [oci_identity_tag_defaults](./d/oci_identity_tag_defaults.md)

- [oci_identity_tag_namespaces](./d/oci_identity_tag_namespaces.md)

- [oci_identity_tags](./d/oci_identity_tags.md)

- [oci_identity_tenancy](./d/oci_identity_tenancy.md)

- [oci_identity_ui_password](./d/oci_identity_ui_password.md)

- [oci_identity_user](./d/oci_identity_user.md)

- [oci_identity_user_group_memberships](./d/oci_identity_user_group_memberships.md)

- [oci_identity_users](./d/oci_identity_users.md)

- [oci_integration_integration_instance](./d/oci_integration_integration_instance.md)

- [oci_integration_integration_instances](./d/oci_integration_integration_instances.md)

- [oci_kms_decrypted_data](./d/oci_kms_decrypted_data.md)

- [oci_kms_encrypted_data](./d/oci_kms_encrypted_data.md)

- [oci_kms_key](./d/oci_kms_key.md)

- [oci_kms_key_version](./d/oci_kms_key_version.md)

- [oci_kms_key_versions](./d/oci_kms_key_versions.md)

- [oci_kms_keys](./d/oci_kms_keys.md)

- [oci_kms_vault](./d/oci_kms_vault.md)

- [oci_kms_vault_usage](./d/oci_kms_vault_usage.md)

- [oci_kms_vaults](./d/oci_kms_vaults.md)

- [oci_limits_limit_definitions](./d/oci_limits_limit_definitions.md)

- [oci_limits_limit_values](./d/oci_limits_limit_values.md)

- [oci_limits_quota](./d/oci_limits_quota.md)

- [oci_limits_quotas](./d/oci_limits_quotas.md)

- [oci_limits_resource_availability](./d/oci_limits_resource_availability.md)

- [oci_limits_services](./d/oci_limits_services.md)

- [oci_load_balancer_backend_health](./d/oci_load_balancer_backend_health.md)

- [oci_load_balancer_backend_set_health](./d/oci_load_balancer_backend_set_health.md)

- [oci_load_balancer_backend_sets](./d/oci_load_balancer_backend_sets.md)

- [oci_load_balancer_backends](./d/oci_load_balancer_backends.md)

- [oci_load_balancer_backendsets](./d/oci_load_balancer_backendsets.md)

- [oci_load_balancer_certificates](./d/oci_load_balancer_certificates.md)

- [oci_load_balancer_health](./d/oci_load_balancer_health.md)

- [oci_load_balancer_hostnames](./d/oci_load_balancer_hostnames.md)

- [oci_load_balancer_listener_rules](./d/oci_load_balancer_listener_rules.md)

- [oci_load_balancer_load_balancer_routing_policies](./d/oci_load_balancer_load_balancer_routing_policies.md)

- [oci_load_balancer_load_balancer_routing_policy](./d/oci_load_balancer_load_balancer_routing_policy.md)

- [oci_load_balancer_load_balancers](./d/oci_load_balancer_load_balancers.md)

- [oci_load_balancer_path_route_sets](./d/oci_load_balancer_path_route_sets.md)

- [oci_load_balancer_policies](./d/oci_load_balancer_policies.md)

- [oci_load_balancer_protocols](./d/oci_load_balancer_protocols.md)

- [oci_load_balancer_rule_set](./d/oci_load_balancer_rule_set.md)

- [oci_load_balancer_rule_sets](./d/oci_load_balancer_rule_sets.md)

- [oci_load_balancer_shapes](./d/oci_load_balancer_shapes.md)

- [oci_load_balancer_ssl_cipher_suite](./d/oci_load_balancer_ssl_cipher_suite.md)

- [oci_load_balancer_ssl_cipher_suites](./d/oci_load_balancer_ssl_cipher_suites.md)

- [oci_load_balancers](./d/oci_load_balancers.md)

- [oci_log_analytics_log_analytics_entities](./d/oci_log_analytics_log_analytics_entities.md)

- [oci_log_analytics_log_analytics_entities_summary](./d/oci_log_analytics_log_analytics_entities_summary.md)

- [oci_log_analytics_log_analytics_entity](./d/oci_log_analytics_log_analytics_entity.md)

- [oci_log_analytics_log_analytics_log_group](./d/oci_log_analytics_log_analytics_log_group.md)

- [oci_log_analytics_log_analytics_log_groups](./d/oci_log_analytics_log_analytics_log_groups.md)

- [oci_log_analytics_log_analytics_log_groups_summary](./d/oci_log_analytics_log_analytics_log_groups_summary.md)

- [oci_log_analytics_namespace](./d/oci_log_analytics_namespace.md)

- [oci_log_analytics_namespaces](./d/oci_log_analytics_namespaces.md)

- [oci_logging_log](./d/oci_logging_log.md)

- [oci_logging_log_group](./d/oci_logging_log_group.md)

- [oci_logging_log_groups](./d/oci_logging_log_groups.md)

- [oci_logging_log_saved_search](./d/oci_logging_log_saved_search.md)

- [oci_logging_log_saved_searches](./d/oci_logging_log_saved_searches.md)

- [oci_logging_logs](./d/oci_logging_logs.md)

- [oci_logging_unified_agent_configuration](./d/oci_logging_unified_agent_configuration.md)

- [oci_logging_unified_agent_configurations](./d/oci_logging_unified_agent_configurations.md)

- [oci_management_agent_management_agent](./d/oci_management_agent_management_agent.md)

- [oci_management_agent_management_agent_available_histories](./d/oci_management_agent_management_agent_available_histories.md)

- [oci_management_agent_management_agent_images](./d/oci_management_agent_management_agent_images.md)

- [oci_management_agent_management_agent_install_key](./d/oci_management_agent_management_agent_install_key.md)

- [oci_management_agent_management_agent_install_keys](./d/oci_management_agent_management_agent_install_keys.md)

- [oci_management_agent_management_agent_plugins](./d/oci_management_agent_management_agent_plugins.md)

- [oci_management_agent_management_agents](./d/oci_management_agent_management_agents.md)

- [oci_management_dashboard_management_dashboards_export](./d/oci_management_dashboard_management_dashboards_export.md)

- [oci_marketplace_accepted_agreement](./d/oci_marketplace_accepted_agreement.md)

- [oci_marketplace_accepted_agreements](./d/oci_marketplace_accepted_agreements.md)

- [oci_marketplace_categories](./d/oci_marketplace_categories.md)

- [oci_marketplace_listing](./d/oci_marketplace_listing.md)

- [oci_marketplace_listing_package](./d/oci_marketplace_listing_package.md)

- [oci_marketplace_listing_package_agreements](./d/oci_marketplace_listing_package_agreements.md)

- [oci_marketplace_listing_packages](./d/oci_marketplace_listing_packages.md)

- [oci_marketplace_listing_taxes](./d/oci_marketplace_listing_taxes.md)

- [oci_marketplace_listings](./d/oci_marketplace_listings.md)

- [oci_marketplace_publication](./d/oci_marketplace_publication.md)

- [oci_marketplace_publication_package](./d/oci_marketplace_publication_package.md)

- [oci_marketplace_publication_packages](./d/oci_marketplace_publication_packages.md)

- [oci_marketplace_publications](./d/oci_marketplace_publications.md)

- [oci_marketplace_publishers](./d/oci_marketplace_publishers.md)

- [oci_metering_computation_configuration](./d/oci_metering_computation_configuration.md)

- [oci_metering_computation_queries](./d/oci_metering_computation_queries.md)

- [oci_metering_computation_query](./d/oci_metering_computation_query.md)

- [oci_monitoring_alarm](./d/oci_monitoring_alarm.md)

- [oci_monitoring_alarm_history_collection](./d/oci_monitoring_alarm_history_collection.md)

- [oci_monitoring_alarm_statuses](./d/oci_monitoring_alarm_statuses.md)

- [oci_monitoring_alarms](./d/oci_monitoring_alarms.md)

- [oci_monitoring_metric_data](./d/oci_monitoring_metric_data.md)

- [oci_monitoring_metrics](./d/oci_monitoring_metrics.md)

- [oci_mysql_analytics_cluster](./d/oci_mysql_analytics_cluster.md)

- [oci_mysql_channel](./d/oci_mysql_channel.md)

- [oci_mysql_channels](./d/oci_mysql_channels.md)

- [oci_mysql_heat_wave_cluster](./d/oci_mysql_heat_wave_cluster.md)

- [oci_mysql_mysql_backup](./d/oci_mysql_mysql_backup.md)

- [oci_mysql_mysql_backups](./d/oci_mysql_mysql_backups.md)

- [oci_mysql_mysql_configuration](./d/oci_mysql_mysql_configuration.md)

- [oci_mysql_mysql_configurations](./d/oci_mysql_mysql_configurations.md)

- [oci_mysql_mysql_db_system](./d/oci_mysql_mysql_db_system.md)

- [oci_mysql_mysql_db_systems](./d/oci_mysql_mysql_db_systems.md)

- [oci_mysql_mysql_versions](./d/oci_mysql_mysql_versions.md)

- [oci_mysql_shapes](./d/oci_mysql_shapes.md)

- [oci_network_load_balancer_backend_health](./d/oci_network_load_balancer_backend_health.md)

- [oci_network_load_balancer_backend_set](./d/oci_network_load_balancer_backend_set.md)

- [oci_network_load_balancer_backend_set_health](./d/oci_network_load_balancer_backend_set_health.md)

- [oci_network_load_balancer_backend_sets](./d/oci_network_load_balancer_backend_sets.md)

- [oci_network_load_balancer_backends](./d/oci_network_load_balancer_backends.md)

- [oci_network_load_balancer_listener](./d/oci_network_load_balancer_listener.md)

- [oci_network_load_balancer_listeners](./d/oci_network_load_balancer_listeners.md)

- [oci_network_load_balancer_network_load_balancer](./d/oci_network_load_balancer_network_load_balancer.md)

- [oci_network_load_balancer_network_load_balancer_health](./d/oci_network_load_balancer_network_load_balancer_health.md)

- [oci_network_load_balancer_network_load_balancers](./d/oci_network_load_balancer_network_load_balancers.md)

- [oci_network_load_balancer_network_load_balancers_policies](./d/oci_network_load_balancer_network_load_balancers_policies.md)

- [oci_network_load_balancer_network_load_balancers_protocols](./d/oci_network_load_balancer_network_load_balancers_protocols.md)

- [oci_nosql_index](./d/oci_nosql_index.md)

- [oci_nosql_indexes](./d/oci_nosql_indexes.md)

- [oci_nosql_table](./d/oci_nosql_table.md)

- [oci_nosql_tables](./d/oci_nosql_tables.md)

- [oci_objectstorage_bucket](./d/oci_objectstorage_bucket.md)

- [oci_objectstorage_bucket_summaries](./d/oci_objectstorage_bucket_summaries.md)

- [oci_objectstorage_namespace](./d/oci_objectstorage_namespace.md)

- [oci_objectstorage_namespace_metadata](./d/oci_objectstorage_namespace_metadata.md)

- [oci_objectstorage_object](./d/oci_objectstorage_object.md)

- [oci_objectstorage_object_head](./d/oci_objectstorage_object_head.md)

- [oci_objectstorage_object_lifecycle_policy](./d/oci_objectstorage_object_lifecycle_policy.md)

- [oci_objectstorage_object_versions](./d/oci_objectstorage_object_versions.md)

- [oci_objectstorage_objects](./d/oci_objectstorage_objects.md)

- [oci_objectstorage_preauthrequest](./d/oci_objectstorage_preauthrequest.md)

- [oci_objectstorage_preauthrequests](./d/oci_objectstorage_preauthrequests.md)

- [oci_objectstorage_replication_policies](./d/oci_objectstorage_replication_policies.md)

- [oci_objectstorage_replication_policy](./d/oci_objectstorage_replication_policy.md)

- [oci_objectstorage_replication_sources](./d/oci_objectstorage_replication_sources.md)

- [oci_oce_oce_instance](./d/oci_oce_oce_instance.md)

- [oci_oce_oce_instances](./d/oci_oce_oce_instances.md)

- [oci_ocvp_esxi_host](./d/oci_ocvp_esxi_host.md)

- [oci_ocvp_esxi_hosts](./d/oci_ocvp_esxi_hosts.md)

- [oci_ocvp_sddc](./d/oci_ocvp_sddc.md)

- [oci_ocvp_sddcs](./d/oci_ocvp_sddcs.md)

- [oci_ocvp_supported_vmware_software_versions](./d/oci_ocvp_supported_vmware_software_versions.md)

- [oci_oda_oda_instance](./d/oci_oda_oda_instance.md)

- [oci_oda_oda_instances](./d/oci_oda_oda_instances.md)

- [oci_ons_notification_topic](./d/oci_ons_notification_topic.md)

- [oci_ons_notification_topics](./d/oci_ons_notification_topics.md)

- [oci_ons_subscription](./d/oci_ons_subscription.md)

- [oci_ons_subscriptions](./d/oci_ons_subscriptions.md)

- [oci_optimizer_categories](./d/oci_optimizer_categories.md)

- [oci_optimizer_category](./d/oci_optimizer_category.md)

- [oci_optimizer_enrollment_status](./d/oci_optimizer_enrollment_status.md)

- [oci_optimizer_enrollment_statuses](./d/oci_optimizer_enrollment_statuses.md)

- [oci_optimizer_histories](./d/oci_optimizer_histories.md)

- [oci_optimizer_profile](./d/oci_optimizer_profile.md)

- [oci_optimizer_profiles](./d/oci_optimizer_profiles.md)

- [oci_optimizer_recommendation](./d/oci_optimizer_recommendation.md)

- [oci_optimizer_recommendation_strategies](./d/oci_optimizer_recommendation_strategies.md)

- [oci_optimizer_recommendation_strategy](./d/oci_optimizer_recommendation_strategy.md)

- [oci_optimizer_recommendations](./d/oci_optimizer_recommendations.md)

- [oci_optimizer_resource_action](./d/oci_optimizer_resource_action.md)

- [oci_optimizer_resource_actions](./d/oci_optimizer_resource_actions.md)

- [oci_osmanagement_managed_instance](./d/oci_osmanagement_managed_instance.md)

- [oci_osmanagement_managed_instance_group](./d/oci_osmanagement_managed_instance_group.md)

- [oci_osmanagement_managed_instance_groups](./d/oci_osmanagement_managed_instance_groups.md)

- [oci_osmanagement_managed_instances](./d/oci_osmanagement_managed_instances.md)

- [oci_osmanagement_software_source](./d/oci_osmanagement_software_source.md)

- [oci_osmanagement_software_sources](./d/oci_osmanagement_software_sources.md)

- [oci_resourcemanager_stack](./d/oci_resourcemanager_stack.md)

- [oci_resourcemanager_stack_tf_state](./d/oci_resourcemanager_stack_tf_state.md)

- [oci_resourcemanager_stacks](./d/oci_resourcemanager_stacks.md)

- [oci_sch_service_connector](./d/oci_sch_service_connector.md)

- [oci_sch_service_connectors](./d/oci_sch_service_connectors.md)

- [oci_streaming_connect_harness](./d/oci_streaming_connect_harness.md)

- [oci_streaming_connect_harnesses](./d/oci_streaming_connect_harnesses.md)

- [oci_streaming_stream](./d/oci_streaming_stream.md)

- [oci_streaming_stream_pool](./d/oci_streaming_stream_pool.md)

- [oci_streaming_stream_pools](./d/oci_streaming_stream_pools.md)

- [oci_streaming_streams](./d/oci_streaming_streams.md)

- [oci_vault_secret](./d/oci_vault_secret.md)

- [oci_vault_secret_version](./d/oci_vault_secret_version.md)

- [oci_vault_secrets](./d/oci_vault_secrets.md)

- [oci_waas_address_list](./d/oci_waas_address_list.md)

- [oci_waas_address_lists](./d/oci_waas_address_lists.md)

- [oci_waas_certificate](./d/oci_waas_certificate.md)

- [oci_waas_certificates](./d/oci_waas_certificates.md)

- [oci_waas_custom_protection_rule](./d/oci_waas_custom_protection_rule.md)

- [oci_waas_custom_protection_rules](./d/oci_waas_custom_protection_rules.md)

- [oci_waas_edge_subnets](./d/oci_waas_edge_subnets.md)

- [oci_waas_http_redirect](./d/oci_waas_http_redirect.md)

- [oci_waas_http_redirects](./d/oci_waas_http_redirects.md)

- [oci_waas_protection_rule](./d/oci_waas_protection_rule.md)

- [oci_waas_protection_rules](./d/oci_waas_protection_rules.md)

- [oci_waas_waas_policies](./d/oci_waas_waas_policies.md)

- [oci_waas_waas_policy](./d/oci_waas_waas_policy.md)


[top](#index)