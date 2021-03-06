# Tutorial: Configuring Workload Management \(WLM\) Queues to Improve Query Processing<a name="tutorial-configuring-workload-management"></a>

## Overview<a name="tutorial-wlm-overview"></a>

This tutorial walks you through the process of configuring workload management \(WLM\) in Amazon Redshift\. By configuring WLM, you can improve query performance and resource allocation in your cluster\. 

Amazon Redshift routes user queries to queues for processing\. WLM defines how those queries are routed to the queues\. By default, Amazon Redshift has two queues available for queries: one for superusers, and one for users\. The superuser queue cannot be configured and can only process one query at a time\. You should reserve this queue for troubleshooting purposes only\. The user queue can process up to five queries at a time, but you can configure this by changing the concurrency level of the queue if needed\. 

When you have several users running queries against the database, you might find another configuration to be more efficient\. For example, if some users run resource\-intensive operations, such as VACUUM, these might have a negative impact on less\-intensive queries, such as reports\. You might consider adding additional queues and configuring them for different workloads\. 

**Estimated time:** 75 minutes

**Estimated cost:** 50 cents

### Prerequisites<a name="tutorial-wlm-prereq"></a>

You will need an Amazon Redshift cluster, the sample TICKIT database, and the psql client tool\. If you do not already have these set up, go to [Amazon Redshift Getting Started](https://docs.aws.amazon.com/redshift/latest/gsg/getting-started.html) and [Connect to Your Cluster by Using the psql Tool](https://docs.aws.amazon.com/redshift/latest/mgmt/connecting-from-psql.html)\. 

### Sections<a name="tutorial-wlm-steps"></a>
+ [Section 1: Understanding the Default Queue Processing Behavior](tutorial-wlm-understanding-default-processing.md)
+ [Section 2: Modifying the WLM Query Queue Configuration](tutorial-wlm-modifying-wlm-configuration.md)
+ [Section 3: Routing Queries to Queues Based on User Groups and Query Groups](tutorial-wlm-routing-queries-to-queues.md)
+ [Section 4: Using wlm\_query\_slot\_count to Temporarily Override Concurrency Level in a Queue](tutorial-wlm-query-slot-count.md)
+ [Section 5: Cleaning Up Your Resources](tutorial-wlm-cleaning-up-resources.md)