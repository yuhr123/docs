==========
Monitoring
==========

.. default-domain:: minio

.. contents:: Table of Contents
   :local:
   :depth: 1

Metrics and Alerts
------------------

MinIO provides cluster and node-level metrics through `Prometheus
<https://prometheus.io/>`__-compatible scraping endpoints. Prometheus is an
Open-Source systems and service monitoring system which supports analyzing and
alerting based on collected metrics. The Prometheus ecosystem includes multiple
:prometheus-docs:`integrations <operating/integrations/>`, allowing wide
latitude in processing and storing collected metrics. You can alternatively use
any other Prometheus-compatible metrics scraping software.

- See :ref:`minio-metrics-and-alerts` for more complete documentation on 
  MinIO Metrics and Alerts.

- See :ref:`minio-metrics-collect-using-prometheus` for a tutorial on 
  configuring Prometheus for monitoring a MinIO deployment. 

Logging
-------

MinIO supports publishing both regular operational logs and audit logs to any
generic HTTP endpoint. Operational logs are equivalent to the console logs
produced by :mc:`minio` processes. Audit logs are granular descriptions of
each operation on the MinIO deployment.

MinIO publishes logs as a JSON document as a ``PUT`` request to each configured
endpoint. The target HTTP webhook target is responsible for processing each
JSON document. 

See :ref:`minio-logging` for more complete documentation.

Healthchecks
------------

MinIO exposes unauthenticated endpoints for probing node uptime and 
cluster :ref:`high availability <minio-ec-parity>` for simple healthchecks.
These endpoints return only an HTTP status code. See 
:ref:`` for more information.

Bucket Notifications
--------------------

MinIO supports publishing bucket or object events to the following supported 
targets on certain supported events. 

- :ref:`minio-bucket-notifications-publish-amqp`
- :ref:`minio-bucket-notifications-publish-mqtt`
- :ref:`minio-bucket-notifications-publish-nats`
- :ref:`minio-bucket-notifications-publish-nsq`
- :ref:`minio-bucket-notifications-publish-elasticsearch`
- :ref:`minio-bucket-notifications-publish-kafka`
- :ref:`minio-bucket-notifications-publish-mysql`
- :ref:`minio-bucket-notifications-publish-postgresql`
- :ref:`minio-bucket-notifications-publish-redis`
- :ref:`minio-bucket-notifications-publish-webhook` 

See :ref:`minio-bucket-notifications`
for more complete documentation on MinIO Bucket Notifications.


.. toctree::
   :titlesonly:
   :hidden:

   /monitoring/metrics-alerts/minio-metrics-and-alerts
   /monitoring/logging/minio-logging
   /monitoring/healthcheck-probe
   /monitoring/bucket-notifications/bucket-notifications