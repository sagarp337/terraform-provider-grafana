---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "grafana_connections_metrics_endpoint_scrape_job Resource - terraform-provider-grafana"
subcategory: "Connections"
description: |-
  
---

# grafana_connections_metrics_endpoint_scrape_job (Resource)



## Example Usage

```terraform
resource "grafana_connections_metrics_endpoint_scrape_job" "test" {
  stack_id                      = "1"
  name                          = "my-scrape-job"
  enabled                       = true
  authentication_method         = "basic"
  authentication_basic_username = "my-username"
  authentication_basic_password = "my-password"
  url                           = "https://grafana.com/metrics"
  scrape_interval_seconds       = 120
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `authentication_method` (String) Method to pass authentication credentials: basic or bearer.
- `name` (String) The name of the metrics endpoint scrape job. Part of the Terraform Resource ID.
- `stack_id` (String) The Stack ID of the Grafana Cloud instance. Part of the Terraform Resource ID.
- `url` (String) The url to scrape metrics from; a valid HTTPs URL is required.

### Optional

- `authentication_basic_password` (String, Sensitive) Password for basic authentication, use if scrape job is using basic authentication method
- `authentication_basic_username` (String) Username for basic authentication, use if scrape job is using basic authentication method
- `authentication_bearer_token` (String, Sensitive) Bearer token used for authentication, use if scrape job is using bearer authentication method
- `enabled` (Boolean) Whether the metrics endpoint scrape job is enabled or not.
- `scrape_interval_seconds` (Number) Frequency for scraping the metrics endpoint: 30, 60, or 120 seconds.

### Read-Only

- `id` (String) The Terraform Resource ID. This has the format "{{ stack_id }}:{{ name }}".

## Import

Import is supported using the following syntax:

```shell
terraform import grafana_connections_metrics_endpoint_scrape_job.name "{{ stack_id }}:{{ name }}"
```