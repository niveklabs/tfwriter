# azurerm

[back](../)

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "azurerm" {
  version = "2.54.0"

  # auxiliary_tenant_ids - (optional) is a type of list of string
  auxiliary_tenant_ids = []
  # client_certificate_password - (optional) is a type of string
  client_certificate_password = null
  # client_certificate_path - (optional) is a type of string
  client_certificate_path = null
  # client_id - (optional) is a type of string
  client_id = null
  # client_secret - (optional) is a type of string
  client_secret = null
  # disable_correlation_request_id - (optional) is a type of bool
  disable_correlation_request_id = null
  # disable_terraform_partner_id - (optional) is a type of bool
  disable_terraform_partner_id = null
  # environment - (optional) is a type of string
  environment = null
  # metadata_host - (optional) is a type of string
  metadata_host = null
  # metadata_url - (optional) is a type of string
  metadata_url = null
  # msi_endpoint - (optional) is a type of string
  msi_endpoint = null
  # partner_id - (optional) is a type of string
  partner_id = null
  # skip_credentials_validation - (optional) is a type of bool
  skip_credentials_validation = null
  # skip_provider_registration - (optional) is a type of bool
  skip_provider_registration = null
  # storage_use_azuread - (optional) is a type of bool
  storage_use_azuread = null
  # subscription_id - (optional) is a type of string
  subscription_id = null
  # tenant_id - (optional) is a type of string
  tenant_id = null
  # use_msi - (optional) is a type of bool
  use_msi = null

  # NestingList
  features {

    # NestingList
    key_vault {
      # purge_soft_delete_on_destroy - (optional) is a type of bool
      purge_soft_delete_on_destroy = null
      # recover_soft_deleted_key_vaults - (optional) is a type of bool
      recover_soft_deleted_key_vaults = null
    }

    # NestingList
    log_analytics_workspace {
      # permanently_delete_on_destroy - (required) is a type of bool
      permanently_delete_on_destroy = null
    }

    # NestingList
    network {
      # relaxed_locking - (required) is a type of bool
      relaxed_locking = null
    }

    # NestingList
    template_deployment {
      # delete_nested_items_during_deletion - (required) is a type of bool
      delete_nested_items_during_deletion = null
    }

    # NestingList
    virtual_machine {
      # delete_os_disk_on_deletion - (optional) is a type of bool
      delete_os_disk_on_deletion = null
      # graceful_shutdown - (optional) is a type of bool
      graceful_shutdown = null
    }

    # NestingList
    virtual_machine_scale_set {
      # roll_instances_when_required - (required) is a type of bool
      roll_instances_when_required = null
    }
  }
}
```

[top](#index)

### Resources


- [azurerm_advanced_threat_protection](./r/azurerm_advanced_threat_protection.md)

- [azurerm_analysis_services_server](./r/azurerm_analysis_services_server.md)

- [azurerm_api_management](./r/azurerm_api_management.md)

- [azurerm_api_management_api](./r/azurerm_api_management_api.md)

- [azurerm_api_management_api_diagnostic](./r/azurerm_api_management_api_diagnostic.md)

- [azurerm_api_management_api_operation](./r/azurerm_api_management_api_operation.md)

- [azurerm_api_management_api_operation_policy](./r/azurerm_api_management_api_operation_policy.md)

- [azurerm_api_management_api_policy](./r/azurerm_api_management_api_policy.md)

- [azurerm_api_management_api_schema](./r/azurerm_api_management_api_schema.md)

- [azurerm_api_management_api_version_set](./r/azurerm_api_management_api_version_set.md)

- [azurerm_api_management_authorization_server](./r/azurerm_api_management_authorization_server.md)

- [azurerm_api_management_backend](./r/azurerm_api_management_backend.md)

- [azurerm_api_management_certificate](./r/azurerm_api_management_certificate.md)

- [azurerm_api_management_custom_domain](./r/azurerm_api_management_custom_domain.md)

- [azurerm_api_management_diagnostic](./r/azurerm_api_management_diagnostic.md)

- [azurerm_api_management_group](./r/azurerm_api_management_group.md)

- [azurerm_api_management_group_user](./r/azurerm_api_management_group_user.md)

- [azurerm_api_management_identity_provider_aad](./r/azurerm_api_management_identity_provider_aad.md)

- [azurerm_api_management_identity_provider_aadb2c](./r/azurerm_api_management_identity_provider_aadb2c.md)

- [azurerm_api_management_identity_provider_facebook](./r/azurerm_api_management_identity_provider_facebook.md)

- [azurerm_api_management_identity_provider_google](./r/azurerm_api_management_identity_provider_google.md)

- [azurerm_api_management_identity_provider_microsoft](./r/azurerm_api_management_identity_provider_microsoft.md)

- [azurerm_api_management_identity_provider_twitter](./r/azurerm_api_management_identity_provider_twitter.md)

- [azurerm_api_management_logger](./r/azurerm_api_management_logger.md)

- [azurerm_api_management_named_value](./r/azurerm_api_management_named_value.md)

- [azurerm_api_management_openid_connect_provider](./r/azurerm_api_management_openid_connect_provider.md)

- [azurerm_api_management_policy](./r/azurerm_api_management_policy.md)

- [azurerm_api_management_product](./r/azurerm_api_management_product.md)

- [azurerm_api_management_product_api](./r/azurerm_api_management_product_api.md)

- [azurerm_api_management_product_group](./r/azurerm_api_management_product_group.md)

- [azurerm_api_management_product_policy](./r/azurerm_api_management_product_policy.md)

- [azurerm_api_management_property](./r/azurerm_api_management_property.md)

- [azurerm_api_management_subscription](./r/azurerm_api_management_subscription.md)

- [azurerm_api_management_user](./r/azurerm_api_management_user.md)

- [azurerm_app_configuration](./r/azurerm_app_configuration.md)

- [azurerm_app_service](./r/azurerm_app_service.md)

- [azurerm_app_service_active_slot](./r/azurerm_app_service_active_slot.md)

- [azurerm_app_service_certificate](./r/azurerm_app_service_certificate.md)

- [azurerm_app_service_certificate_binding](./r/azurerm_app_service_certificate_binding.md)

- [azurerm_app_service_certificate_order](./r/azurerm_app_service_certificate_order.md)

- [azurerm_app_service_custom_hostname_binding](./r/azurerm_app_service_custom_hostname_binding.md)

- [azurerm_app_service_environment](./r/azurerm_app_service_environment.md)

- [azurerm_app_service_hybrid_connection](./r/azurerm_app_service_hybrid_connection.md)

- [azurerm_app_service_managed_certificate](./r/azurerm_app_service_managed_certificate.md)

- [azurerm_app_service_plan](./r/azurerm_app_service_plan.md)

- [azurerm_app_service_slot](./r/azurerm_app_service_slot.md)

- [azurerm_app_service_slot_virtual_network_swift_connection](./r/azurerm_app_service_slot_virtual_network_swift_connection.md)

- [azurerm_app_service_source_control_token](./r/azurerm_app_service_source_control_token.md)

- [azurerm_app_service_virtual_network_swift_connection](./r/azurerm_app_service_virtual_network_swift_connection.md)

- [azurerm_application_gateway](./r/azurerm_application_gateway.md)

- [azurerm_application_insights](./r/azurerm_application_insights.md)

- [azurerm_application_insights_analytics_item](./r/azurerm_application_insights_analytics_item.md)

- [azurerm_application_insights_api_key](./r/azurerm_application_insights_api_key.md)

- [azurerm_application_insights_smart_detection_rule](./r/azurerm_application_insights_smart_detection_rule.md)

- [azurerm_application_insights_web_test](./r/azurerm_application_insights_web_test.md)

- [azurerm_application_security_group](./r/azurerm_application_security_group.md)

- [azurerm_attestation_provider](./r/azurerm_attestation_provider.md)

- [azurerm_automation_account](./r/azurerm_automation_account.md)

- [azurerm_automation_certificate](./r/azurerm_automation_certificate.md)

- [azurerm_automation_connection](./r/azurerm_automation_connection.md)

- [azurerm_automation_connection_certificate](./r/azurerm_automation_connection_certificate.md)

- [azurerm_automation_connection_classic_certificate](./r/azurerm_automation_connection_classic_certificate.md)

- [azurerm_automation_connection_service_principal](./r/azurerm_automation_connection_service_principal.md)

- [azurerm_automation_credential](./r/azurerm_automation_credential.md)

- [azurerm_automation_dsc_configuration](./r/azurerm_automation_dsc_configuration.md)

- [azurerm_automation_dsc_nodeconfiguration](./r/azurerm_automation_dsc_nodeconfiguration.md)

- [azurerm_automation_job_schedule](./r/azurerm_automation_job_schedule.md)

- [azurerm_automation_module](./r/azurerm_automation_module.md)

- [azurerm_automation_runbook](./r/azurerm_automation_runbook.md)

- [azurerm_automation_schedule](./r/azurerm_automation_schedule.md)

- [azurerm_automation_variable_bool](./r/azurerm_automation_variable_bool.md)

- [azurerm_automation_variable_datetime](./r/azurerm_automation_variable_datetime.md)

- [azurerm_automation_variable_int](./r/azurerm_automation_variable_int.md)

- [azurerm_automation_variable_string](./r/azurerm_automation_variable_string.md)

- [azurerm_availability_set](./r/azurerm_availability_set.md)

- [azurerm_backup_container_storage_account](./r/azurerm_backup_container_storage_account.md)

- [azurerm_backup_policy_file_share](./r/azurerm_backup_policy_file_share.md)

- [azurerm_backup_policy_vm](./r/azurerm_backup_policy_vm.md)

- [azurerm_backup_protected_file_share](./r/azurerm_backup_protected_file_share.md)

- [azurerm_backup_protected_vm](./r/azurerm_backup_protected_vm.md)

- [azurerm_bastion_host](./r/azurerm_bastion_host.md)

- [azurerm_batch_account](./r/azurerm_batch_account.md)

- [azurerm_batch_application](./r/azurerm_batch_application.md)

- [azurerm_batch_certificate](./r/azurerm_batch_certificate.md)

- [azurerm_batch_pool](./r/azurerm_batch_pool.md)

- [azurerm_blueprint_assignment](./r/azurerm_blueprint_assignment.md)

- [azurerm_bot_channel_directline](./r/azurerm_bot_channel_directline.md)

- [azurerm_bot_channel_email](./r/azurerm_bot_channel_email.md)

- [azurerm_bot_channel_ms_teams](./r/azurerm_bot_channel_ms_teams.md)

- [azurerm_bot_channel_slack](./r/azurerm_bot_channel_slack.md)

- [azurerm_bot_channels_registration](./r/azurerm_bot_channels_registration.md)

- [azurerm_bot_connection](./r/azurerm_bot_connection.md)

- [azurerm_bot_web_app](./r/azurerm_bot_web_app.md)

- [azurerm_cdn_endpoint](./r/azurerm_cdn_endpoint.md)

- [azurerm_cdn_profile](./r/azurerm_cdn_profile.md)

- [azurerm_cognitive_account](./r/azurerm_cognitive_account.md)

- [azurerm_container_group](./r/azurerm_container_group.md)

- [azurerm_container_registry](./r/azurerm_container_registry.md)

- [azurerm_container_registry_webhook](./r/azurerm_container_registry_webhook.md)

- [azurerm_cosmosdb_account](./r/azurerm_cosmosdb_account.md)

- [azurerm_cosmosdb_cassandra_keyspace](./r/azurerm_cosmosdb_cassandra_keyspace.md)

- [azurerm_cosmosdb_cassandra_table](./r/azurerm_cosmosdb_cassandra_table.md)

- [azurerm_cosmosdb_gremlin_database](./r/azurerm_cosmosdb_gremlin_database.md)

- [azurerm_cosmosdb_gremlin_graph](./r/azurerm_cosmosdb_gremlin_graph.md)

- [azurerm_cosmosdb_mongo_collection](./r/azurerm_cosmosdb_mongo_collection.md)

- [azurerm_cosmosdb_mongo_database](./r/azurerm_cosmosdb_mongo_database.md)

- [azurerm_cosmosdb_sql_container](./r/azurerm_cosmosdb_sql_container.md)

- [azurerm_cosmosdb_sql_database](./r/azurerm_cosmosdb_sql_database.md)

- [azurerm_cosmosdb_sql_stored_procedure](./r/azurerm_cosmosdb_sql_stored_procedure.md)

- [azurerm_cosmosdb_table](./r/azurerm_cosmosdb_table.md)

- [azurerm_cost_management_export_resource_group](./r/azurerm_cost_management_export_resource_group.md)

- [azurerm_custom_provider](./r/azurerm_custom_provider.md)

- [azurerm_dashboard](./r/azurerm_dashboard.md)

- [azurerm_data_factory](./r/azurerm_data_factory.md)

- [azurerm_data_factory_dataset_azure_blob](./r/azurerm_data_factory_dataset_azure_blob.md)

- [azurerm_data_factory_dataset_cosmosdb_sqlapi](./r/azurerm_data_factory_dataset_cosmosdb_sqlapi.md)

- [azurerm_data_factory_dataset_delimited_text](./r/azurerm_data_factory_dataset_delimited_text.md)

- [azurerm_data_factory_dataset_http](./r/azurerm_data_factory_dataset_http.md)

- [azurerm_data_factory_dataset_json](./r/azurerm_data_factory_dataset_json.md)

- [azurerm_data_factory_dataset_mysql](./r/azurerm_data_factory_dataset_mysql.md)

- [azurerm_data_factory_dataset_parquet](./r/azurerm_data_factory_dataset_parquet.md)

- [azurerm_data_factory_dataset_postgresql](./r/azurerm_data_factory_dataset_postgresql.md)

- [azurerm_data_factory_dataset_sql_server_table](./r/azurerm_data_factory_dataset_sql_server_table.md)

- [azurerm_data_factory_integration_runtime_azure](./r/azurerm_data_factory_integration_runtime_azure.md)

- [azurerm_data_factory_integration_runtime_azure_ssis](./r/azurerm_data_factory_integration_runtime_azure_ssis.md)

- [azurerm_data_factory_integration_runtime_managed](./r/azurerm_data_factory_integration_runtime_managed.md)

- [azurerm_data_factory_integration_runtime_self_hosted](./r/azurerm_data_factory_integration_runtime_self_hosted.md)

- [azurerm_data_factory_linked_service_azure_blob_storage](./r/azurerm_data_factory_linked_service_azure_blob_storage.md)

- [azurerm_data_factory_linked_service_azure_file_storage](./r/azurerm_data_factory_linked_service_azure_file_storage.md)

- [azurerm_data_factory_linked_service_azure_function](./r/azurerm_data_factory_linked_service_azure_function.md)

- [azurerm_data_factory_linked_service_azure_sql_database](./r/azurerm_data_factory_linked_service_azure_sql_database.md)

- [azurerm_data_factory_linked_service_azure_table_storage](./r/azurerm_data_factory_linked_service_azure_table_storage.md)

- [azurerm_data_factory_linked_service_cosmosdb](./r/azurerm_data_factory_linked_service_cosmosdb.md)

- [azurerm_data_factory_linked_service_data_lake_storage_gen2](./r/azurerm_data_factory_linked_service_data_lake_storage_gen2.md)

- [azurerm_data_factory_linked_service_key_vault](./r/azurerm_data_factory_linked_service_key_vault.md)

- [azurerm_data_factory_linked_service_mysql](./r/azurerm_data_factory_linked_service_mysql.md)

- [azurerm_data_factory_linked_service_postgresql](./r/azurerm_data_factory_linked_service_postgresql.md)

- [azurerm_data_factory_linked_service_sftp](./r/azurerm_data_factory_linked_service_sftp.md)

- [azurerm_data_factory_linked_service_snowflake](./r/azurerm_data_factory_linked_service_snowflake.md)

- [azurerm_data_factory_linked_service_sql_server](./r/azurerm_data_factory_linked_service_sql_server.md)

- [azurerm_data_factory_linked_service_synapse](./r/azurerm_data_factory_linked_service_synapse.md)

- [azurerm_data_factory_linked_service_web](./r/azurerm_data_factory_linked_service_web.md)

- [azurerm_data_factory_pipeline](./r/azurerm_data_factory_pipeline.md)

- [azurerm_data_factory_trigger_schedule](./r/azurerm_data_factory_trigger_schedule.md)

- [azurerm_data_lake_analytics_account](./r/azurerm_data_lake_analytics_account.md)

- [azurerm_data_lake_analytics_firewall_rule](./r/azurerm_data_lake_analytics_firewall_rule.md)

- [azurerm_data_lake_store](./r/azurerm_data_lake_store.md)

- [azurerm_data_lake_store_file](./r/azurerm_data_lake_store_file.md)

- [azurerm_data_lake_store_firewall_rule](./r/azurerm_data_lake_store_firewall_rule.md)

- [azurerm_data_share](./r/azurerm_data_share.md)

- [azurerm_data_share_account](./r/azurerm_data_share_account.md)

- [azurerm_data_share_dataset_blob_storage](./r/azurerm_data_share_dataset_blob_storage.md)

- [azurerm_data_share_dataset_data_lake_gen1](./r/azurerm_data_share_dataset_data_lake_gen1.md)

- [azurerm_data_share_dataset_data_lake_gen2](./r/azurerm_data_share_dataset_data_lake_gen2.md)

- [azurerm_data_share_dataset_kusto_cluster](./r/azurerm_data_share_dataset_kusto_cluster.md)

- [azurerm_data_share_dataset_kusto_database](./r/azurerm_data_share_dataset_kusto_database.md)

- [azurerm_database_migration_project](./r/azurerm_database_migration_project.md)

- [azurerm_database_migration_service](./r/azurerm_database_migration_service.md)

- [azurerm_databox_edge_device](./r/azurerm_databox_edge_device.md)

- [azurerm_databox_edge_order](./r/azurerm_databox_edge_order.md)

- [azurerm_databricks_workspace](./r/azurerm_databricks_workspace.md)

- [azurerm_dedicated_hardware_security_module](./r/azurerm_dedicated_hardware_security_module.md)

- [azurerm_dedicated_host](./r/azurerm_dedicated_host.md)

- [azurerm_dedicated_host_group](./r/azurerm_dedicated_host_group.md)

- [azurerm_dev_test_global_vm_shutdown_schedule](./r/azurerm_dev_test_global_vm_shutdown_schedule.md)

- [azurerm_dev_test_lab](./r/azurerm_dev_test_lab.md)

- [azurerm_dev_test_linux_virtual_machine](./r/azurerm_dev_test_linux_virtual_machine.md)

- [azurerm_dev_test_policy](./r/azurerm_dev_test_policy.md)

- [azurerm_dev_test_schedule](./r/azurerm_dev_test_schedule.md)

- [azurerm_dev_test_virtual_network](./r/azurerm_dev_test_virtual_network.md)

- [azurerm_dev_test_windows_virtual_machine](./r/azurerm_dev_test_windows_virtual_machine.md)

- [azurerm_devspace_controller](./r/azurerm_devspace_controller.md)

- [azurerm_digital_twins_endpoint_eventgrid](./r/azurerm_digital_twins_endpoint_eventgrid.md)

- [azurerm_digital_twins_endpoint_eventhub](./r/azurerm_digital_twins_endpoint_eventhub.md)

- [azurerm_digital_twins_endpoint_servicebus](./r/azurerm_digital_twins_endpoint_servicebus.md)

- [azurerm_digital_twins_instance](./r/azurerm_digital_twins_instance.md)

- [azurerm_disk_access](./r/azurerm_disk_access.md)

- [azurerm_disk_encryption_set](./r/azurerm_disk_encryption_set.md)

- [azurerm_dns_a_record](./r/azurerm_dns_a_record.md)

- [azurerm_dns_aaaa_record](./r/azurerm_dns_aaaa_record.md)

- [azurerm_dns_caa_record](./r/azurerm_dns_caa_record.md)

- [azurerm_dns_cname_record](./r/azurerm_dns_cname_record.md)

- [azurerm_dns_mx_record](./r/azurerm_dns_mx_record.md)

- [azurerm_dns_ns_record](./r/azurerm_dns_ns_record.md)

- [azurerm_dns_ptr_record](./r/azurerm_dns_ptr_record.md)

- [azurerm_dns_srv_record](./r/azurerm_dns_srv_record.md)

- [azurerm_dns_txt_record](./r/azurerm_dns_txt_record.md)

- [azurerm_dns_zone](./r/azurerm_dns_zone.md)

- [azurerm_eventgrid_domain](./r/azurerm_eventgrid_domain.md)

- [azurerm_eventgrid_domain_topic](./r/azurerm_eventgrid_domain_topic.md)

- [azurerm_eventgrid_event_subscription](./r/azurerm_eventgrid_event_subscription.md)

- [azurerm_eventgrid_system_topic](./r/azurerm_eventgrid_system_topic.md)

- [azurerm_eventgrid_system_topic_event_subscription](./r/azurerm_eventgrid_system_topic_event_subscription.md)

- [azurerm_eventgrid_topic](./r/azurerm_eventgrid_topic.md)

- [azurerm_eventhub](./r/azurerm_eventhub.md)

- [azurerm_eventhub_authorization_rule](./r/azurerm_eventhub_authorization_rule.md)

- [azurerm_eventhub_cluster](./r/azurerm_eventhub_cluster.md)

- [azurerm_eventhub_consumer_group](./r/azurerm_eventhub_consumer_group.md)

- [azurerm_eventhub_namespace](./r/azurerm_eventhub_namespace.md)

- [azurerm_eventhub_namespace_authorization_rule](./r/azurerm_eventhub_namespace_authorization_rule.md)

- [azurerm_eventhub_namespace_disaster_recovery_config](./r/azurerm_eventhub_namespace_disaster_recovery_config.md)

- [azurerm_express_route_circuit](./r/azurerm_express_route_circuit.md)

- [azurerm_express_route_circuit_authorization](./r/azurerm_express_route_circuit_authorization.md)

- [azurerm_express_route_circuit_peering](./r/azurerm_express_route_circuit_peering.md)

- [azurerm_express_route_gateway](./r/azurerm_express_route_gateway.md)

- [azurerm_firewall](./r/azurerm_firewall.md)

- [azurerm_firewall_application_rule_collection](./r/azurerm_firewall_application_rule_collection.md)

- [azurerm_firewall_nat_rule_collection](./r/azurerm_firewall_nat_rule_collection.md)

- [azurerm_firewall_network_rule_collection](./r/azurerm_firewall_network_rule_collection.md)

- [azurerm_firewall_policy](./r/azurerm_firewall_policy.md)

- [azurerm_firewall_policy_rule_collection_group](./r/azurerm_firewall_policy_rule_collection_group.md)

- [azurerm_frontdoor](./r/azurerm_frontdoor.md)

- [azurerm_frontdoor_custom_https_configuration](./r/azurerm_frontdoor_custom_https_configuration.md)

- [azurerm_frontdoor_firewall_policy](./r/azurerm_frontdoor_firewall_policy.md)

- [azurerm_function_app](./r/azurerm_function_app.md)

- [azurerm_function_app_slot](./r/azurerm_function_app_slot.md)

- [azurerm_hdinsight_hadoop_cluster](./r/azurerm_hdinsight_hadoop_cluster.md)

- [azurerm_hdinsight_hbase_cluster](./r/azurerm_hdinsight_hbase_cluster.md)

- [azurerm_hdinsight_interactive_query_cluster](./r/azurerm_hdinsight_interactive_query_cluster.md)

- [azurerm_hdinsight_kafka_cluster](./r/azurerm_hdinsight_kafka_cluster.md)

- [azurerm_hdinsight_ml_services_cluster](./r/azurerm_hdinsight_ml_services_cluster.md)

- [azurerm_hdinsight_rserver_cluster](./r/azurerm_hdinsight_rserver_cluster.md)

- [azurerm_hdinsight_spark_cluster](./r/azurerm_hdinsight_spark_cluster.md)

- [azurerm_hdinsight_storm_cluster](./r/azurerm_hdinsight_storm_cluster.md)

- [azurerm_healthcare_service](./r/azurerm_healthcare_service.md)

- [azurerm_hpc_cache](./r/azurerm_hpc_cache.md)

- [azurerm_hpc_cache_access_policy](./r/azurerm_hpc_cache_access_policy.md)

- [azurerm_hpc_cache_blob_target](./r/azurerm_hpc_cache_blob_target.md)

- [azurerm_hpc_cache_nfs_target](./r/azurerm_hpc_cache_nfs_target.md)

- [azurerm_image](./r/azurerm_image.md)

- [azurerm_integration_service_environment](./r/azurerm_integration_service_environment.md)

- [azurerm_iot_security_device_group](./r/azurerm_iot_security_device_group.md)

- [azurerm_iot_security_solution](./r/azurerm_iot_security_solution.md)

- [azurerm_iot_time_series_insights_access_policy](./r/azurerm_iot_time_series_insights_access_policy.md)

- [azurerm_iot_time_series_insights_gen2_environment](./r/azurerm_iot_time_series_insights_gen2_environment.md)

- [azurerm_iot_time_series_insights_reference_data_set](./r/azurerm_iot_time_series_insights_reference_data_set.md)

- [azurerm_iot_time_series_insights_standard_environment](./r/azurerm_iot_time_series_insights_standard_environment.md)

- [azurerm_iotcentral_application](./r/azurerm_iotcentral_application.md)

- [azurerm_iothub](./r/azurerm_iothub.md)

- [azurerm_iothub_consumer_group](./r/azurerm_iothub_consumer_group.md)

- [azurerm_iothub_dps](./r/azurerm_iothub_dps.md)

- [azurerm_iothub_dps_certificate](./r/azurerm_iothub_dps_certificate.md)

- [azurerm_iothub_dps_shared_access_policy](./r/azurerm_iothub_dps_shared_access_policy.md)

- [azurerm_iothub_endpoint_eventhub](./r/azurerm_iothub_endpoint_eventhub.md)

- [azurerm_iothub_endpoint_servicebus_queue](./r/azurerm_iothub_endpoint_servicebus_queue.md)

- [azurerm_iothub_endpoint_servicebus_topic](./r/azurerm_iothub_endpoint_servicebus_topic.md)

- [azurerm_iothub_endpoint_storage_container](./r/azurerm_iothub_endpoint_storage_container.md)

- [azurerm_iothub_enrichment](./r/azurerm_iothub_enrichment.md)

- [azurerm_iothub_fallback_route](./r/azurerm_iothub_fallback_route.md)

- [azurerm_iothub_route](./r/azurerm_iothub_route.md)

- [azurerm_iothub_shared_access_policy](./r/azurerm_iothub_shared_access_policy.md)

- [azurerm_ip_group](./r/azurerm_ip_group.md)

- [azurerm_key_vault](./r/azurerm_key_vault.md)

- [azurerm_key_vault_access_policy](./r/azurerm_key_vault_access_policy.md)

- [azurerm_key_vault_certificate](./r/azurerm_key_vault_certificate.md)

- [azurerm_key_vault_certificate_issuer](./r/azurerm_key_vault_certificate_issuer.md)

- [azurerm_key_vault_key](./r/azurerm_key_vault_key.md)

- [azurerm_key_vault_secret](./r/azurerm_key_vault_secret.md)

- [azurerm_kubernetes_cluster](./r/azurerm_kubernetes_cluster.md)

- [azurerm_kubernetes_cluster_node_pool](./r/azurerm_kubernetes_cluster_node_pool.md)

- [azurerm_kusto_attached_database_configuration](./r/azurerm_kusto_attached_database_configuration.md)

- [azurerm_kusto_cluster](./r/azurerm_kusto_cluster.md)

- [azurerm_kusto_cluster_customer_managed_key](./r/azurerm_kusto_cluster_customer_managed_key.md)

- [azurerm_kusto_cluster_principal_assignment](./r/azurerm_kusto_cluster_principal_assignment.md)

- [azurerm_kusto_database](./r/azurerm_kusto_database.md)

- [azurerm_kusto_database_principal](./r/azurerm_kusto_database_principal.md)

- [azurerm_kusto_database_principal_assignment](./r/azurerm_kusto_database_principal_assignment.md)

- [azurerm_kusto_eventgrid_data_connection](./r/azurerm_kusto_eventgrid_data_connection.md)

- [azurerm_kusto_eventhub_data_connection](./r/azurerm_kusto_eventhub_data_connection.md)

- [azurerm_kusto_iothub_data_connection](./r/azurerm_kusto_iothub_data_connection.md)

- [azurerm_lb](./r/azurerm_lb.md)

- [azurerm_lb_backend_address_pool](./r/azurerm_lb_backend_address_pool.md)

- [azurerm_lb_backend_address_pool_address](./r/azurerm_lb_backend_address_pool_address.md)

- [azurerm_lb_nat_pool](./r/azurerm_lb_nat_pool.md)

- [azurerm_lb_nat_rule](./r/azurerm_lb_nat_rule.md)

- [azurerm_lb_outbound_rule](./r/azurerm_lb_outbound_rule.md)

- [azurerm_lb_probe](./r/azurerm_lb_probe.md)

- [azurerm_lb_rule](./r/azurerm_lb_rule.md)

- [azurerm_lighthouse_assignment](./r/azurerm_lighthouse_assignment.md)

- [azurerm_lighthouse_definition](./r/azurerm_lighthouse_definition.md)

- [azurerm_linux_virtual_machine](./r/azurerm_linux_virtual_machine.md)

- [azurerm_linux_virtual_machine_scale_set](./r/azurerm_linux_virtual_machine_scale_set.md)

- [azurerm_local_network_gateway](./r/azurerm_local_network_gateway.md)

- [azurerm_log_analytics_cluster](./r/azurerm_log_analytics_cluster.md)

- [azurerm_log_analytics_cluster_customer_managed_key](./r/azurerm_log_analytics_cluster_customer_managed_key.md)

- [azurerm_log_analytics_data_export_rule](./r/azurerm_log_analytics_data_export_rule.md)

- [azurerm_log_analytics_datasource_windows_event](./r/azurerm_log_analytics_datasource_windows_event.md)

- [azurerm_log_analytics_datasource_windows_performance_counter](./r/azurerm_log_analytics_datasource_windows_performance_counter.md)

- [azurerm_log_analytics_linked_service](./r/azurerm_log_analytics_linked_service.md)

- [azurerm_log_analytics_linked_storage_account](./r/azurerm_log_analytics_linked_storage_account.md)

- [azurerm_log_analytics_saved_search](./r/azurerm_log_analytics_saved_search.md)

- [azurerm_log_analytics_solution](./r/azurerm_log_analytics_solution.md)

- [azurerm_log_analytics_storage_insights](./r/azurerm_log_analytics_storage_insights.md)

- [azurerm_log_analytics_workspace](./r/azurerm_log_analytics_workspace.md)

- [azurerm_logic_app_action_custom](./r/azurerm_logic_app_action_custom.md)

- [azurerm_logic_app_action_http](./r/azurerm_logic_app_action_http.md)

- [azurerm_logic_app_integration_account](./r/azurerm_logic_app_integration_account.md)

- [azurerm_logic_app_trigger_custom](./r/azurerm_logic_app_trigger_custom.md)

- [azurerm_logic_app_trigger_http_request](./r/azurerm_logic_app_trigger_http_request.md)

- [azurerm_logic_app_trigger_recurrence](./r/azurerm_logic_app_trigger_recurrence.md)

- [azurerm_logic_app_workflow](./r/azurerm_logic_app_workflow.md)

- [azurerm_machine_learning_workspace](./r/azurerm_machine_learning_workspace.md)

- [azurerm_maintenance_assignment_dedicated_host](./r/azurerm_maintenance_assignment_dedicated_host.md)

- [azurerm_maintenance_assignment_virtual_machine](./r/azurerm_maintenance_assignment_virtual_machine.md)

- [azurerm_maintenance_configuration](./r/azurerm_maintenance_configuration.md)

- [azurerm_managed_application](./r/azurerm_managed_application.md)

- [azurerm_managed_application_definition](./r/azurerm_managed_application_definition.md)

- [azurerm_managed_disk](./r/azurerm_managed_disk.md)

- [azurerm_management_group](./r/azurerm_management_group.md)

- [azurerm_management_group_subscription_association](./r/azurerm_management_group_subscription_association.md)

- [azurerm_management_group_template_deployment](./r/azurerm_management_group_template_deployment.md)

- [azurerm_management_lock](./r/azurerm_management_lock.md)

- [azurerm_maps_account](./r/azurerm_maps_account.md)

- [azurerm_mariadb_configuration](./r/azurerm_mariadb_configuration.md)

- [azurerm_mariadb_database](./r/azurerm_mariadb_database.md)

- [azurerm_mariadb_firewall_rule](./r/azurerm_mariadb_firewall_rule.md)

- [azurerm_mariadb_server](./r/azurerm_mariadb_server.md)

- [azurerm_mariadb_virtual_network_rule](./r/azurerm_mariadb_virtual_network_rule.md)

- [azurerm_marketplace_agreement](./r/azurerm_marketplace_agreement.md)

- [azurerm_media_asset](./r/azurerm_media_asset.md)

- [azurerm_media_content_key_policy](./r/azurerm_media_content_key_policy.md)

- [azurerm_media_job](./r/azurerm_media_job.md)

- [azurerm_media_live_event](./r/azurerm_media_live_event.md)

- [azurerm_media_services_account](./r/azurerm_media_services_account.md)

- [azurerm_media_streaming_endpoint](./r/azurerm_media_streaming_endpoint.md)

- [azurerm_media_streaming_locator](./r/azurerm_media_streaming_locator.md)

- [azurerm_media_streaming_policy](./r/azurerm_media_streaming_policy.md)

- [azurerm_media_transform](./r/azurerm_media_transform.md)

- [azurerm_monitor_action_group](./r/azurerm_monitor_action_group.md)

- [azurerm_monitor_action_rule_action_group](./r/azurerm_monitor_action_rule_action_group.md)

- [azurerm_monitor_action_rule_suppression](./r/azurerm_monitor_action_rule_suppression.md)

- [azurerm_monitor_activity_log_alert](./r/azurerm_monitor_activity_log_alert.md)

- [azurerm_monitor_autoscale_setting](./r/azurerm_monitor_autoscale_setting.md)

- [azurerm_monitor_diagnostic_setting](./r/azurerm_monitor_diagnostic_setting.md)

- [azurerm_monitor_log_profile](./r/azurerm_monitor_log_profile.md)

- [azurerm_monitor_metric_alert](./r/azurerm_monitor_metric_alert.md)

- [azurerm_monitor_scheduled_query_rules_alert](./r/azurerm_monitor_scheduled_query_rules_alert.md)

- [azurerm_monitor_scheduled_query_rules_log](./r/azurerm_monitor_scheduled_query_rules_log.md)

- [azurerm_monitor_smart_detector_alert_rule](./r/azurerm_monitor_smart_detector_alert_rule.md)

- [azurerm_mssql_database](./r/azurerm_mssql_database.md)

- [azurerm_mssql_database_extended_auditing_policy](./r/azurerm_mssql_database_extended_auditing_policy.md)

- [azurerm_mssql_database_vulnerability_assessment_rule_baseline](./r/azurerm_mssql_database_vulnerability_assessment_rule_baseline.md)

- [azurerm_mssql_elasticpool](./r/azurerm_mssql_elasticpool.md)

- [azurerm_mssql_firewall_rule](./r/azurerm_mssql_firewall_rule.md)

- [azurerm_mssql_server](./r/azurerm_mssql_server.md)

- [azurerm_mssql_server_extended_auditing_policy](./r/azurerm_mssql_server_extended_auditing_policy.md)

- [azurerm_mssql_server_security_alert_policy](./r/azurerm_mssql_server_security_alert_policy.md)

- [azurerm_mssql_server_vulnerability_assessment](./r/azurerm_mssql_server_vulnerability_assessment.md)

- [azurerm_mssql_virtual_machine](./r/azurerm_mssql_virtual_machine.md)

- [azurerm_mssql_virtual_network_rule](./r/azurerm_mssql_virtual_network_rule.md)

- [azurerm_mysql_active_directory_administrator](./r/azurerm_mysql_active_directory_administrator.md)

- [azurerm_mysql_configuration](./r/azurerm_mysql_configuration.md)

- [azurerm_mysql_database](./r/azurerm_mysql_database.md)

- [azurerm_mysql_firewall_rule](./r/azurerm_mysql_firewall_rule.md)

- [azurerm_mysql_server](./r/azurerm_mysql_server.md)

- [azurerm_mysql_server_key](./r/azurerm_mysql_server_key.md)

- [azurerm_mysql_virtual_network_rule](./r/azurerm_mysql_virtual_network_rule.md)

- [azurerm_nat_gateway](./r/azurerm_nat_gateway.md)

- [azurerm_nat_gateway_public_ip_association](./r/azurerm_nat_gateway_public_ip_association.md)

- [azurerm_netapp_account](./r/azurerm_netapp_account.md)

- [azurerm_netapp_pool](./r/azurerm_netapp_pool.md)

- [azurerm_netapp_snapshot](./r/azurerm_netapp_snapshot.md)

- [azurerm_netapp_volume](./r/azurerm_netapp_volume.md)

- [azurerm_network_connection_monitor](./r/azurerm_network_connection_monitor.md)

- [azurerm_network_ddos_protection_plan](./r/azurerm_network_ddos_protection_plan.md)

- [azurerm_network_interface](./r/azurerm_network_interface.md)

- [azurerm_network_interface_application_gateway_backend_address_pool_association](./r/azurerm_network_interface_application_gateway_backend_address_pool_association.md)

- [azurerm_network_interface_application_security_group_association](./r/azurerm_network_interface_application_security_group_association.md)

- [azurerm_network_interface_backend_address_pool_association](./r/azurerm_network_interface_backend_address_pool_association.md)

- [azurerm_network_interface_nat_rule_association](./r/azurerm_network_interface_nat_rule_association.md)

- [azurerm_network_interface_security_group_association](./r/azurerm_network_interface_security_group_association.md)

- [azurerm_network_packet_capture](./r/azurerm_network_packet_capture.md)

- [azurerm_network_profile](./r/azurerm_network_profile.md)

- [azurerm_network_security_group](./r/azurerm_network_security_group.md)

- [azurerm_network_security_rule](./r/azurerm_network_security_rule.md)

- [azurerm_network_watcher](./r/azurerm_network_watcher.md)

- [azurerm_network_watcher_flow_log](./r/azurerm_network_watcher_flow_log.md)

- [azurerm_notification_hub](./r/azurerm_notification_hub.md)

- [azurerm_notification_hub_authorization_rule](./r/azurerm_notification_hub_authorization_rule.md)

- [azurerm_notification_hub_namespace](./r/azurerm_notification_hub_namespace.md)

- [azurerm_orchestrated_virtual_machine_scale_set](./r/azurerm_orchestrated_virtual_machine_scale_set.md)

- [azurerm_packet_capture](./r/azurerm_packet_capture.md)

- [azurerm_point_to_site_vpn_gateway](./r/azurerm_point_to_site_vpn_gateway.md)

- [azurerm_policy_assignment](./r/azurerm_policy_assignment.md)

- [azurerm_policy_definition](./r/azurerm_policy_definition.md)

- [azurerm_policy_remediation](./r/azurerm_policy_remediation.md)

- [azurerm_policy_set_definition](./r/azurerm_policy_set_definition.md)

- [azurerm_postgresql_active_directory_administrator](./r/azurerm_postgresql_active_directory_administrator.md)

- [azurerm_postgresql_configuration](./r/azurerm_postgresql_configuration.md)

- [azurerm_postgresql_database](./r/azurerm_postgresql_database.md)

- [azurerm_postgresql_firewall_rule](./r/azurerm_postgresql_firewall_rule.md)

- [azurerm_postgresql_server](./r/azurerm_postgresql_server.md)

- [azurerm_postgresql_server_key](./r/azurerm_postgresql_server_key.md)

- [azurerm_postgresql_virtual_network_rule](./r/azurerm_postgresql_virtual_network_rule.md)

- [azurerm_powerbi_embedded](./r/azurerm_powerbi_embedded.md)

- [azurerm_private_dns_a_record](./r/azurerm_private_dns_a_record.md)

- [azurerm_private_dns_aaaa_record](./r/azurerm_private_dns_aaaa_record.md)

- [azurerm_private_dns_cname_record](./r/azurerm_private_dns_cname_record.md)

- [azurerm_private_dns_mx_record](./r/azurerm_private_dns_mx_record.md)

- [azurerm_private_dns_ptr_record](./r/azurerm_private_dns_ptr_record.md)

- [azurerm_private_dns_srv_record](./r/azurerm_private_dns_srv_record.md)

- [azurerm_private_dns_txt_record](./r/azurerm_private_dns_txt_record.md)

- [azurerm_private_dns_zone](./r/azurerm_private_dns_zone.md)

- [azurerm_private_dns_zone_virtual_network_link](./r/azurerm_private_dns_zone_virtual_network_link.md)

- [azurerm_private_endpoint](./r/azurerm_private_endpoint.md)

- [azurerm_private_link_service](./r/azurerm_private_link_service.md)

- [azurerm_proximity_placement_group](./r/azurerm_proximity_placement_group.md)

- [azurerm_public_ip](./r/azurerm_public_ip.md)

- [azurerm_public_ip_prefix](./r/azurerm_public_ip_prefix.md)

- [azurerm_purview_account](./r/azurerm_purview_account.md)

- [azurerm_recovery_services_vault](./r/azurerm_recovery_services_vault.md)

- [azurerm_redis_cache](./r/azurerm_redis_cache.md)

- [azurerm_redis_enterprise_cluster](./r/azurerm_redis_enterprise_cluster.md)

- [azurerm_redis_enterprise_database](./r/azurerm_redis_enterprise_database.md)

- [azurerm_redis_firewall_rule](./r/azurerm_redis_firewall_rule.md)

- [azurerm_redis_linked_server](./r/azurerm_redis_linked_server.md)

- [azurerm_relay_hybrid_connection](./r/azurerm_relay_hybrid_connection.md)

- [azurerm_relay_namespace](./r/azurerm_relay_namespace.md)

- [azurerm_resource_group](./r/azurerm_resource_group.md)

- [azurerm_resource_group_template_deployment](./r/azurerm_resource_group_template_deployment.md)

- [azurerm_resource_provider_registration](./r/azurerm_resource_provider_registration.md)

- [azurerm_role_assignment](./r/azurerm_role_assignment.md)

- [azurerm_role_definition](./r/azurerm_role_definition.md)

- [azurerm_route](./r/azurerm_route.md)

- [azurerm_route_filter](./r/azurerm_route_filter.md)

- [azurerm_route_table](./r/azurerm_route_table.md)

- [azurerm_search_service](./r/azurerm_search_service.md)

- [azurerm_security_center_assessment](./r/azurerm_security_center_assessment.md)

- [azurerm_security_center_assessment_metadata](./r/azurerm_security_center_assessment_metadata.md)

- [azurerm_security_center_assessment_policy](./r/azurerm_security_center_assessment_policy.md)

- [azurerm_security_center_auto_provisioning](./r/azurerm_security_center_auto_provisioning.md)

- [azurerm_security_center_automation](./r/azurerm_security_center_automation.md)

- [azurerm_security_center_contact](./r/azurerm_security_center_contact.md)

- [azurerm_security_center_server_vulnerability_assessment](./r/azurerm_security_center_server_vulnerability_assessment.md)

- [azurerm_security_center_setting](./r/azurerm_security_center_setting.md)

- [azurerm_security_center_subscription_pricing](./r/azurerm_security_center_subscription_pricing.md)

- [azurerm_security_center_workspace](./r/azurerm_security_center_workspace.md)

- [azurerm_sentinel_alert_rule_fusion](./r/azurerm_sentinel_alert_rule_fusion.md)

- [azurerm_sentinel_alert_rule_ms_security_incident](./r/azurerm_sentinel_alert_rule_ms_security_incident.md)

- [azurerm_sentinel_alert_rule_scheduled](./r/azurerm_sentinel_alert_rule_scheduled.md)

- [azurerm_sentinel_data_connector_aws_cloud_trail](./r/azurerm_sentinel_data_connector_aws_cloud_trail.md)

- [azurerm_sentinel_data_connector_azure_active_directory](./r/azurerm_sentinel_data_connector_azure_active_directory.md)

- [azurerm_sentinel_data_connector_azure_advanced_threat_protection](./r/azurerm_sentinel_data_connector_azure_advanced_threat_protection.md)

- [azurerm_sentinel_data_connector_azure_security_center](./r/azurerm_sentinel_data_connector_azure_security_center.md)

- [azurerm_sentinel_data_connector_microsoft_cloud_app_security](./r/azurerm_sentinel_data_connector_microsoft_cloud_app_security.md)

- [azurerm_sentinel_data_connector_office_365](./r/azurerm_sentinel_data_connector_office_365.md)

- [azurerm_sentinel_data_connector_threat_intelligence](./r/azurerm_sentinel_data_connector_threat_intelligence.md)

- [azurerm_service_fabric_cluster](./r/azurerm_service_fabric_cluster.md)

- [azurerm_service_fabric_mesh_application](./r/azurerm_service_fabric_mesh_application.md)

- [azurerm_service_fabric_mesh_local_network](./r/azurerm_service_fabric_mesh_local_network.md)

- [azurerm_service_fabric_mesh_secret](./r/azurerm_service_fabric_mesh_secret.md)

- [azurerm_service_fabric_mesh_secret_value](./r/azurerm_service_fabric_mesh_secret_value.md)

- [azurerm_servicebus_namespace](./r/azurerm_servicebus_namespace.md)

- [azurerm_servicebus_namespace_authorization_rule](./r/azurerm_servicebus_namespace_authorization_rule.md)

- [azurerm_servicebus_namespace_network_rule_set](./r/azurerm_servicebus_namespace_network_rule_set.md)

- [azurerm_servicebus_queue](./r/azurerm_servicebus_queue.md)

- [azurerm_servicebus_queue_authorization_rule](./r/azurerm_servicebus_queue_authorization_rule.md)

- [azurerm_servicebus_subscription](./r/azurerm_servicebus_subscription.md)

- [azurerm_servicebus_subscription_rule](./r/azurerm_servicebus_subscription_rule.md)

- [azurerm_servicebus_topic](./r/azurerm_servicebus_topic.md)

- [azurerm_servicebus_topic_authorization_rule](./r/azurerm_servicebus_topic_authorization_rule.md)

- [azurerm_shared_image](./r/azurerm_shared_image.md)

- [azurerm_shared_image_gallery](./r/azurerm_shared_image_gallery.md)

- [azurerm_shared_image_version](./r/azurerm_shared_image_version.md)

- [azurerm_signalr_service](./r/azurerm_signalr_service.md)

- [azurerm_site_recovery_fabric](./r/azurerm_site_recovery_fabric.md)

- [azurerm_site_recovery_network_mapping](./r/azurerm_site_recovery_network_mapping.md)

- [azurerm_site_recovery_protection_container](./r/azurerm_site_recovery_protection_container.md)

- [azurerm_site_recovery_protection_container_mapping](./r/azurerm_site_recovery_protection_container_mapping.md)

- [azurerm_site_recovery_replicated_vm](./r/azurerm_site_recovery_replicated_vm.md)

- [azurerm_site_recovery_replication_policy](./r/azurerm_site_recovery_replication_policy.md)

- [azurerm_snapshot](./r/azurerm_snapshot.md)

- [azurerm_spatial_anchors_account](./r/azurerm_spatial_anchors_account.md)

- [azurerm_spring_cloud_active_deployment](./r/azurerm_spring_cloud_active_deployment.md)

- [azurerm_spring_cloud_app](./r/azurerm_spring_cloud_app.md)

- [azurerm_spring_cloud_certificate](./r/azurerm_spring_cloud_certificate.md)

- [azurerm_spring_cloud_custom_domain](./r/azurerm_spring_cloud_custom_domain.md)

- [azurerm_spring_cloud_java_deployment](./r/azurerm_spring_cloud_java_deployment.md)

- [azurerm_spring_cloud_service](./r/azurerm_spring_cloud_service.md)

- [azurerm_sql_active_directory_administrator](./r/azurerm_sql_active_directory_administrator.md)

- [azurerm_sql_database](./r/azurerm_sql_database.md)

- [azurerm_sql_elasticpool](./r/azurerm_sql_elasticpool.md)

- [azurerm_sql_failover_group](./r/azurerm_sql_failover_group.md)

- [azurerm_sql_firewall_rule](./r/azurerm_sql_firewall_rule.md)

- [azurerm_sql_server](./r/azurerm_sql_server.md)

- [azurerm_sql_virtual_network_rule](./r/azurerm_sql_virtual_network_rule.md)

- [azurerm_ssh_public_key](./r/azurerm_ssh_public_key.md)

- [azurerm_stack_hci_cluster](./r/azurerm_stack_hci_cluster.md)

- [azurerm_storage_account](./r/azurerm_storage_account.md)

- [azurerm_storage_account_customer_managed_key](./r/azurerm_storage_account_customer_managed_key.md)

- [azurerm_storage_account_network_rules](./r/azurerm_storage_account_network_rules.md)

- [azurerm_storage_blob](./r/azurerm_storage_blob.md)

- [azurerm_storage_container](./r/azurerm_storage_container.md)

- [azurerm_storage_data_lake_gen2_filesystem](./r/azurerm_storage_data_lake_gen2_filesystem.md)

- [azurerm_storage_data_lake_gen2_path](./r/azurerm_storage_data_lake_gen2_path.md)

- [azurerm_storage_encryption_scope](./r/azurerm_storage_encryption_scope.md)

- [azurerm_storage_management_policy](./r/azurerm_storage_management_policy.md)

- [azurerm_storage_queue](./r/azurerm_storage_queue.md)

- [azurerm_storage_share](./r/azurerm_storage_share.md)

- [azurerm_storage_share_directory](./r/azurerm_storage_share_directory.md)

- [azurerm_storage_share_file](./r/azurerm_storage_share_file.md)

- [azurerm_storage_sync](./r/azurerm_storage_sync.md)

- [azurerm_storage_sync_cloud_endpoint](./r/azurerm_storage_sync_cloud_endpoint.md)

- [azurerm_storage_sync_group](./r/azurerm_storage_sync_group.md)

- [azurerm_storage_table](./r/azurerm_storage_table.md)

- [azurerm_storage_table_entity](./r/azurerm_storage_table_entity.md)

- [azurerm_stream_analytics_function_javascript_udf](./r/azurerm_stream_analytics_function_javascript_udf.md)

- [azurerm_stream_analytics_job](./r/azurerm_stream_analytics_job.md)

- [azurerm_stream_analytics_output_blob](./r/azurerm_stream_analytics_output_blob.md)

- [azurerm_stream_analytics_output_eventhub](./r/azurerm_stream_analytics_output_eventhub.md)

- [azurerm_stream_analytics_output_mssql](./r/azurerm_stream_analytics_output_mssql.md)

- [azurerm_stream_analytics_output_servicebus_queue](./r/azurerm_stream_analytics_output_servicebus_queue.md)

- [azurerm_stream_analytics_output_servicebus_topic](./r/azurerm_stream_analytics_output_servicebus_topic.md)

- [azurerm_stream_analytics_reference_input_blob](./r/azurerm_stream_analytics_reference_input_blob.md)

- [azurerm_stream_analytics_stream_input_blob](./r/azurerm_stream_analytics_stream_input_blob.md)

- [azurerm_stream_analytics_stream_input_eventhub](./r/azurerm_stream_analytics_stream_input_eventhub.md)

- [azurerm_stream_analytics_stream_input_iothub](./r/azurerm_stream_analytics_stream_input_iothub.md)

- [azurerm_subnet](./r/azurerm_subnet.md)

- [azurerm_subnet_nat_gateway_association](./r/azurerm_subnet_nat_gateway_association.md)

- [azurerm_subnet_network_security_group_association](./r/azurerm_subnet_network_security_group_association.md)

- [azurerm_subnet_route_table_association](./r/azurerm_subnet_route_table_association.md)

- [azurerm_subnet_service_endpoint_storage_policy](./r/azurerm_subnet_service_endpoint_storage_policy.md)

- [azurerm_subscription](./r/azurerm_subscription.md)

- [azurerm_subscription_template_deployment](./r/azurerm_subscription_template_deployment.md)

- [azurerm_synapse_firewall_rule](./r/azurerm_synapse_firewall_rule.md)

- [azurerm_synapse_managed_private_endpoint](./r/azurerm_synapse_managed_private_endpoint.md)

- [azurerm_synapse_role_assignment](./r/azurerm_synapse_role_assignment.md)

- [azurerm_synapse_spark_pool](./r/azurerm_synapse_spark_pool.md)

- [azurerm_synapse_sql_pool](./r/azurerm_synapse_sql_pool.md)

- [azurerm_synapse_workspace](./r/azurerm_synapse_workspace.md)

- [azurerm_template_deployment](./r/azurerm_template_deployment.md)

- [azurerm_tenant_template_deployment](./r/azurerm_tenant_template_deployment.md)

- [azurerm_traffic_manager_endpoint](./r/azurerm_traffic_manager_endpoint.md)

- [azurerm_traffic_manager_profile](./r/azurerm_traffic_manager_profile.md)

- [azurerm_user_assigned_identity](./r/azurerm_user_assigned_identity.md)

- [azurerm_virtual_desktop_application_group](./r/azurerm_virtual_desktop_application_group.md)

- [azurerm_virtual_desktop_host_pool](./r/azurerm_virtual_desktop_host_pool.md)

- [azurerm_virtual_desktop_workspace](./r/azurerm_virtual_desktop_workspace.md)

- [azurerm_virtual_desktop_workspace_application_group_association](./r/azurerm_virtual_desktop_workspace_application_group_association.md)

- [azurerm_virtual_hub](./r/azurerm_virtual_hub.md)

- [azurerm_virtual_hub_bgp_connection](./r/azurerm_virtual_hub_bgp_connection.md)

- [azurerm_virtual_hub_connection](./r/azurerm_virtual_hub_connection.md)

- [azurerm_virtual_hub_ip](./r/azurerm_virtual_hub_ip.md)

- [azurerm_virtual_hub_route_table](./r/azurerm_virtual_hub_route_table.md)

- [azurerm_virtual_hub_security_partner_provider](./r/azurerm_virtual_hub_security_partner_provider.md)

- [azurerm_virtual_machine](./r/azurerm_virtual_machine.md)

- [azurerm_virtual_machine_data_disk_attachment](./r/azurerm_virtual_machine_data_disk_attachment.md)

- [azurerm_virtual_machine_extension](./r/azurerm_virtual_machine_extension.md)

- [azurerm_virtual_machine_scale_set](./r/azurerm_virtual_machine_scale_set.md)

- [azurerm_virtual_machine_scale_set_extension](./r/azurerm_virtual_machine_scale_set_extension.md)

- [azurerm_virtual_network](./r/azurerm_virtual_network.md)

- [azurerm_virtual_network_gateway](./r/azurerm_virtual_network_gateway.md)

- [azurerm_virtual_network_gateway_connection](./r/azurerm_virtual_network_gateway_connection.md)

- [azurerm_virtual_network_peering](./r/azurerm_virtual_network_peering.md)

- [azurerm_virtual_wan](./r/azurerm_virtual_wan.md)

- [azurerm_vmware_private_cloud](./r/azurerm_vmware_private_cloud.md)

- [azurerm_vpn_gateway](./r/azurerm_vpn_gateway.md)

- [azurerm_vpn_gateway_connection](./r/azurerm_vpn_gateway_connection.md)

- [azurerm_vpn_server_configuration](./r/azurerm_vpn_server_configuration.md)

- [azurerm_vpn_site](./r/azurerm_vpn_site.md)

- [azurerm_web_application_firewall_policy](./r/azurerm_web_application_firewall_policy.md)

- [azurerm_windows_virtual_machine](./r/azurerm_windows_virtual_machine.md)

- [azurerm_windows_virtual_machine_scale_set](./r/azurerm_windows_virtual_machine_scale_set.md)


[top](#index)

### Datasources


- [azurerm_advisor_recommendations](./d/azurerm_advisor_recommendations.md)

- [azurerm_api_management](./d/azurerm_api_management.md)

- [azurerm_api_management_api](./d/azurerm_api_management_api.md)

- [azurerm_api_management_api_version_set](./d/azurerm_api_management_api_version_set.md)

- [azurerm_api_management_group](./d/azurerm_api_management_group.md)

- [azurerm_api_management_product](./d/azurerm_api_management_product.md)

- [azurerm_api_management_user](./d/azurerm_api_management_user.md)

- [azurerm_app_configuration](./d/azurerm_app_configuration.md)

- [azurerm_app_service](./d/azurerm_app_service.md)

- [azurerm_app_service_certificate](./d/azurerm_app_service_certificate.md)

- [azurerm_app_service_certificate_order](./d/azurerm_app_service_certificate_order.md)

- [azurerm_app_service_environment](./d/azurerm_app_service_environment.md)

- [azurerm_app_service_plan](./d/azurerm_app_service_plan.md)

- [azurerm_application_gateway](./d/azurerm_application_gateway.md)

- [azurerm_application_insights](./d/azurerm_application_insights.md)

- [azurerm_application_security_group](./d/azurerm_application_security_group.md)

- [azurerm_attestation_provider](./d/azurerm_attestation_provider.md)

- [azurerm_automation_account](./d/azurerm_automation_account.md)

- [azurerm_automation_variable_bool](./d/azurerm_automation_variable_bool.md)

- [azurerm_automation_variable_datetime](./d/azurerm_automation_variable_datetime.md)

- [azurerm_automation_variable_int](./d/azurerm_automation_variable_int.md)

- [azurerm_automation_variable_string](./d/azurerm_automation_variable_string.md)

- [azurerm_availability_set](./d/azurerm_availability_set.md)

- [azurerm_backup_policy_vm](./d/azurerm_backup_policy_vm.md)

- [azurerm_batch_account](./d/azurerm_batch_account.md)

- [azurerm_batch_certificate](./d/azurerm_batch_certificate.md)

- [azurerm_batch_pool](./d/azurerm_batch_pool.md)

- [azurerm_billing_enrollment_account_scope](./d/azurerm_billing_enrollment_account_scope.md)

- [azurerm_billing_mca_account_scope](./d/azurerm_billing_mca_account_scope.md)

- [azurerm_blueprint_definition](./d/azurerm_blueprint_definition.md)

- [azurerm_blueprint_published_version](./d/azurerm_blueprint_published_version.md)

- [azurerm_cdn_profile](./d/azurerm_cdn_profile.md)

- [azurerm_client_config](./d/azurerm_client_config.md)

- [azurerm_cognitive_account](./d/azurerm_cognitive_account.md)

- [azurerm_container_registry](./d/azurerm_container_registry.md)

- [azurerm_cosmosdb_account](./d/azurerm_cosmosdb_account.md)

- [azurerm_data_factory](./d/azurerm_data_factory.md)

- [azurerm_data_lake_store](./d/azurerm_data_lake_store.md)

- [azurerm_data_share](./d/azurerm_data_share.md)

- [azurerm_data_share_account](./d/azurerm_data_share_account.md)

- [azurerm_data_share_dataset_blob_storage](./d/azurerm_data_share_dataset_blob_storage.md)

- [azurerm_data_share_dataset_data_lake_gen1](./d/azurerm_data_share_dataset_data_lake_gen1.md)

- [azurerm_data_share_dataset_data_lake_gen2](./d/azurerm_data_share_dataset_data_lake_gen2.md)

- [azurerm_data_share_dataset_kusto_cluster](./d/azurerm_data_share_dataset_kusto_cluster.md)

- [azurerm_data_share_dataset_kusto_database](./d/azurerm_data_share_dataset_kusto_database.md)

- [azurerm_database_migration_project](./d/azurerm_database_migration_project.md)

- [azurerm_database_migration_service](./d/azurerm_database_migration_service.md)

- [azurerm_databricks_workspace](./d/azurerm_databricks_workspace.md)

- [azurerm_dedicated_host](./d/azurerm_dedicated_host.md)

- [azurerm_dedicated_host_group](./d/azurerm_dedicated_host_group.md)

- [azurerm_dev_test_lab](./d/azurerm_dev_test_lab.md)

- [azurerm_dev_test_virtual_network](./d/azurerm_dev_test_virtual_network.md)

- [azurerm_digital_twins_instance](./d/azurerm_digital_twins_instance.md)

- [azurerm_disk_access](./d/azurerm_disk_access.md)

- [azurerm_disk_encryption_set](./d/azurerm_disk_encryption_set.md)

- [azurerm_dns_zone](./d/azurerm_dns_zone.md)

- [azurerm_eventgrid_domain_topic](./d/azurerm_eventgrid_domain_topic.md)

- [azurerm_eventgrid_topic](./d/azurerm_eventgrid_topic.md)

- [azurerm_eventhub](./d/azurerm_eventhub.md)

- [azurerm_eventhub_authorization_rule](./d/azurerm_eventhub_authorization_rule.md)

- [azurerm_eventhub_consumer_group](./d/azurerm_eventhub_consumer_group.md)

- [azurerm_eventhub_namespace](./d/azurerm_eventhub_namespace.md)

- [azurerm_eventhub_namespace_authorization_rule](./d/azurerm_eventhub_namespace_authorization_rule.md)

- [azurerm_express_route_circuit](./d/azurerm_express_route_circuit.md)

- [azurerm_firewall](./d/azurerm_firewall.md)

- [azurerm_firewall_policy](./d/azurerm_firewall_policy.md)

- [azurerm_function_app](./d/azurerm_function_app.md)

- [azurerm_function_app_host_keys](./d/azurerm_function_app_host_keys.md)

- [azurerm_hdinsight_cluster](./d/azurerm_hdinsight_cluster.md)

- [azurerm_healthcare_service](./d/azurerm_healthcare_service.md)

- [azurerm_image](./d/azurerm_image.md)

- [azurerm_images](./d/azurerm_images.md)

- [azurerm_iothub](./d/azurerm_iothub.md)

- [azurerm_iothub_dps](./d/azurerm_iothub_dps.md)

- [azurerm_iothub_dps_shared_access_policy](./d/azurerm_iothub_dps_shared_access_policy.md)

- [azurerm_iothub_shared_access_policy](./d/azurerm_iothub_shared_access_policy.md)

- [azurerm_ip_group](./d/azurerm_ip_group.md)

- [azurerm_key_vault](./d/azurerm_key_vault.md)

- [azurerm_key_vault_access_policy](./d/azurerm_key_vault_access_policy.md)

- [azurerm_key_vault_certificate](./d/azurerm_key_vault_certificate.md)

- [azurerm_key_vault_certificate_data](./d/azurerm_key_vault_certificate_data.md)

- [azurerm_key_vault_certificate_issuer](./d/azurerm_key_vault_certificate_issuer.md)

- [azurerm_key_vault_key](./d/azurerm_key_vault_key.md)

- [azurerm_key_vault_secret](./d/azurerm_key_vault_secret.md)

- [azurerm_kubernetes_cluster](./d/azurerm_kubernetes_cluster.md)

- [azurerm_kubernetes_cluster_node_pool](./d/azurerm_kubernetes_cluster_node_pool.md)

- [azurerm_kubernetes_service_versions](./d/azurerm_kubernetes_service_versions.md)

- [azurerm_kusto_cluster](./d/azurerm_kusto_cluster.md)

- [azurerm_lb](./d/azurerm_lb.md)

- [azurerm_lb_backend_address_pool](./d/azurerm_lb_backend_address_pool.md)

- [azurerm_lb_rule](./d/azurerm_lb_rule.md)

- [azurerm_log_analytics_workspace](./d/azurerm_log_analytics_workspace.md)

- [azurerm_logic_app_integration_account](./d/azurerm_logic_app_integration_account.md)

- [azurerm_logic_app_workflow](./d/azurerm_logic_app_workflow.md)

- [azurerm_machine_learning_workspace](./d/azurerm_machine_learning_workspace.md)

- [azurerm_maintenance_configuration](./d/azurerm_maintenance_configuration.md)

- [azurerm_managed_application_definition](./d/azurerm_managed_application_definition.md)

- [azurerm_managed_disk](./d/azurerm_managed_disk.md)

- [azurerm_management_group](./d/azurerm_management_group.md)

- [azurerm_maps_account](./d/azurerm_maps_account.md)

- [azurerm_mariadb_server](./d/azurerm_mariadb_server.md)

- [azurerm_monitor_action_group](./d/azurerm_monitor_action_group.md)

- [azurerm_monitor_diagnostic_categories](./d/azurerm_monitor_diagnostic_categories.md)

- [azurerm_monitor_log_profile](./d/azurerm_monitor_log_profile.md)

- [azurerm_monitor_scheduled_query_rules_alert](./d/azurerm_monitor_scheduled_query_rules_alert.md)

- [azurerm_monitor_scheduled_query_rules_log](./d/azurerm_monitor_scheduled_query_rules_log.md)

- [azurerm_mssql_database](./d/azurerm_mssql_database.md)

- [azurerm_mssql_elasticpool](./d/azurerm_mssql_elasticpool.md)

- [azurerm_mssql_server](./d/azurerm_mssql_server.md)

- [azurerm_mysql_server](./d/azurerm_mysql_server.md)

- [azurerm_nat_gateway](./d/azurerm_nat_gateway.md)

- [azurerm_netapp_account](./d/azurerm_netapp_account.md)

- [azurerm_netapp_pool](./d/azurerm_netapp_pool.md)

- [azurerm_netapp_snapshot](./d/azurerm_netapp_snapshot.md)

- [azurerm_netapp_volume](./d/azurerm_netapp_volume.md)

- [azurerm_network_ddos_protection_plan](./d/azurerm_network_ddos_protection_plan.md)

- [azurerm_network_interface](./d/azurerm_network_interface.md)

- [azurerm_network_security_group](./d/azurerm_network_security_group.md)

- [azurerm_network_service_tags](./d/azurerm_network_service_tags.md)

- [azurerm_network_watcher](./d/azurerm_network_watcher.md)

- [azurerm_notification_hub](./d/azurerm_notification_hub.md)

- [azurerm_notification_hub_namespace](./d/azurerm_notification_hub_namespace.md)

- [azurerm_platform_image](./d/azurerm_platform_image.md)

- [azurerm_policy_definition](./d/azurerm_policy_definition.md)

- [azurerm_policy_set_definition](./d/azurerm_policy_set_definition.md)

- [azurerm_postgresql_server](./d/azurerm_postgresql_server.md)

- [azurerm_private_dns_zone](./d/azurerm_private_dns_zone.md)

- [azurerm_private_endpoint_connection](./d/azurerm_private_endpoint_connection.md)

- [azurerm_private_link_service](./d/azurerm_private_link_service.md)

- [azurerm_private_link_service_endpoint_connections](./d/azurerm_private_link_service_endpoint_connections.md)

- [azurerm_proximity_placement_group](./d/azurerm_proximity_placement_group.md)

- [azurerm_public_ip](./d/azurerm_public_ip.md)

- [azurerm_public_ip_prefix](./d/azurerm_public_ip_prefix.md)

- [azurerm_public_ips](./d/azurerm_public_ips.md)

- [azurerm_recovery_services_vault](./d/azurerm_recovery_services_vault.md)

- [azurerm_redis_cache](./d/azurerm_redis_cache.md)

- [azurerm_resource_group](./d/azurerm_resource_group.md)

- [azurerm_resources](./d/azurerm_resources.md)

- [azurerm_role_definition](./d/azurerm_role_definition.md)

- [azurerm_route_filter](./d/azurerm_route_filter.md)

- [azurerm_route_table](./d/azurerm_route_table.md)

- [azurerm_search_service](./d/azurerm_search_service.md)

- [azurerm_sentinel_alert_rule](./d/azurerm_sentinel_alert_rule.md)

- [azurerm_sentinel_alert_rule_template](./d/azurerm_sentinel_alert_rule_template.md)

- [azurerm_servicebus_namespace](./d/azurerm_servicebus_namespace.md)

- [azurerm_servicebus_namespace_authorization_rule](./d/azurerm_servicebus_namespace_authorization_rule.md)

- [azurerm_servicebus_queue](./d/azurerm_servicebus_queue.md)

- [azurerm_servicebus_queue_authorization_rule](./d/azurerm_servicebus_queue_authorization_rule.md)

- [azurerm_servicebus_subscription](./d/azurerm_servicebus_subscription.md)

- [azurerm_servicebus_topic](./d/azurerm_servicebus_topic.md)

- [azurerm_servicebus_topic_authorization_rule](./d/azurerm_servicebus_topic_authorization_rule.md)

- [azurerm_shared_image](./d/azurerm_shared_image.md)

- [azurerm_shared_image_gallery](./d/azurerm_shared_image_gallery.md)

- [azurerm_shared_image_version](./d/azurerm_shared_image_version.md)

- [azurerm_shared_image_versions](./d/azurerm_shared_image_versions.md)

- [azurerm_signalr_service](./d/azurerm_signalr_service.md)

- [azurerm_snapshot](./d/azurerm_snapshot.md)

- [azurerm_spring_cloud_app](./d/azurerm_spring_cloud_app.md)

- [azurerm_spring_cloud_service](./d/azurerm_spring_cloud_service.md)

- [azurerm_sql_database](./d/azurerm_sql_database.md)

- [azurerm_sql_server](./d/azurerm_sql_server.md)

- [azurerm_ssh_public_key](./d/azurerm_ssh_public_key.md)

- [azurerm_storage_account](./d/azurerm_storage_account.md)

- [azurerm_storage_account_blob_container_sas](./d/azurerm_storage_account_blob_container_sas.md)

- [azurerm_storage_account_sas](./d/azurerm_storage_account_sas.md)

- [azurerm_storage_container](./d/azurerm_storage_container.md)

- [azurerm_storage_encryption_scope](./d/azurerm_storage_encryption_scope.md)

- [azurerm_storage_management_policy](./d/azurerm_storage_management_policy.md)

- [azurerm_storage_sync](./d/azurerm_storage_sync.md)

- [azurerm_storage_sync_group](./d/azurerm_storage_sync_group.md)

- [azurerm_stream_analytics_job](./d/azurerm_stream_analytics_job.md)

- [azurerm_subnet](./d/azurerm_subnet.md)

- [azurerm_subscription](./d/azurerm_subscription.md)

- [azurerm_subscriptions](./d/azurerm_subscriptions.md)

- [azurerm_synapse_workspace](./d/azurerm_synapse_workspace.md)

- [azurerm_template_spec_version](./d/azurerm_template_spec_version.md)

- [azurerm_traffic_manager_geographical_location](./d/azurerm_traffic_manager_geographical_location.md)

- [azurerm_traffic_manager_profile](./d/azurerm_traffic_manager_profile.md)

- [azurerm_user_assigned_identity](./d/azurerm_user_assigned_identity.md)

- [azurerm_virtual_hub](./d/azurerm_virtual_hub.md)

- [azurerm_virtual_machine](./d/azurerm_virtual_machine.md)

- [azurerm_virtual_machine_scale_set](./d/azurerm_virtual_machine_scale_set.md)

- [azurerm_virtual_network](./d/azurerm_virtual_network.md)

- [azurerm_virtual_network_gateway](./d/azurerm_virtual_network_gateway.md)

- [azurerm_virtual_network_gateway_connection](./d/azurerm_virtual_network_gateway_connection.md)

- [azurerm_virtual_wan](./d/azurerm_virtual_wan.md)

- [azurerm_vmware_private_cloud](./d/azurerm_vmware_private_cloud.md)

- [azurerm_web_application_firewall_policy](./d/azurerm_web_application_firewall_policy.md)


[top](#index)