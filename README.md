# Monitoring Elastic Beanstalk .NET applications with CloudWatch and Grafana

<a href="https://aws.amazon.com/elasticbeanstalk/">AWS Elastic Beanstalk</a> simplifies deployments by handling many of the architectural complexities involved with managing highly available applications. Elastic Beanstalk provides a monitoring console that displays your environment's status and application health. However, in large deployments with complex application servers, this often requires supplemental, finer grained monitoring and dynamic dashboards in order to achieve the desired operational insights. <a href="https://aws.amazon.com/cloudwatch/">Amazon CloudWatch</a> can be utilized to supplement the Elastic Beanstalk enhanced health monitoring, while <a href="https://aws.amazon.com/grafana/">Amazon Managed Grafana</a> can provide dynamic visualizations for metrics and logs. Amazon Managed Grafana lets you analyze your metrics, logs, and traces without having to provision servers, configure and update software, or do the heavy lifting involved in securing and scaling Grafana in production.

This post provides step-by-step instructions for monitoring your Elastic Beanstalk resources. The solution uses a combination of the <a href="https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/health-enhanced.html#health-enhanced-agent">Elastic Beanstalk health agent</a>, for enhanced health metrics and common log files, and the CloudWatch agent, for system and process level metrics and custom log files. We also provide instructions for creating Grafana dashboards. For setting up your Amazon Managed Grafana environment in this blog post, check <a href="https://aws.amazon.com/blogs/mt/amazon-managed-grafana-getting-started/">Amazon Managed Grafana – Getting Started</a>.

### Overview of solution
Elastic Beanstalk monitors environments by using a built-in health agent and autoscaling health checks. When an application is unhealthy, the instance can be shut down and autoscaling can create a new one. But some complex .NET application servers require lengthy startup times. In addition, many .NET application servers run with multiple application pools on a single instance and require additional monitoring. The CloudWatch agent lets you monitor instance level metrics, such as memory and active server page metrics, as well as process level metrics important for determining application pool health.

Applications may also be deployed across many Elastic Beanstalk environments in order to serve differing customer bases. This, coupled with the ephemeral nature of most Elastic Beanstalk components, means that dynamic dashboards are essential for providing views into the application and environment health. Integrating CloudWatch metrics into Amazon Managed Grafana lets you create custom dashboards that instantly reflect the quickly changing Elastic Beanstalk environments and their resources.

Details of solution and implementation steps can be found in this blog post [insert link].

## Security

See [CONTRIBUTING](CONTRIBUTING.md#security-issue-notifications) for more information.

## License

This library is licensed under the MIT-0 License. See the LICENSE file.

