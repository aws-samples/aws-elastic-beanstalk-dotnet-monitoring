# Monitoring Elastic Beanstalk .NET applications with CloudWatch and Grafana

<a href="https://aws.amazon.com/elasticbeanstalk/">AWS Elastic Beanstalk</a> simplifies deployments by handling much of the architectural complexities involved with managing highly available applications. However, in large deployments with complex application servers, it often requires supplemental, finer grained monitoring and dynamic dashboards to achieve desired operational insights. <a href="https://aws.amazon.com/cloudwatch/">Amazon CloudWatch</a> can be used to supplement the Elastic Beanstalk enhanced health monitoring, while <a href="https://aws.amazon.com/grafana/">Amazon Managed Service for Grafana (AMG)</a> can provide dynamic visualizations.

In this post, we provide step-by-step instructions to monitor your Elastic Beanstalk resources using a combination of the Elastic Beanstalk health agent, for enhanced health metrics and common log files, and the CloudWatch agent, for system and process level metrics and custom log files. We will also provide instructions for creating Grafana dashboards. Help for setting up your AMG environment can be found <a href="https://aws.amazon.com/blogs/mt/amazon-managed-grafana-getting-started/">here</a>.

Overview of solution
Elastic Beanstalk monitors environments using a built-in health agent and auto scaling health checks. When an application is unhealthy, it's possible to terminate the instance and let auto scaling create a new one, but some complex .NET application servers require lengthy startup times. In addition, many .NET application servers run with multiple application pools on a single instance that require additional monitoring. The CloudWatch agent provides the ability to monitor instance level metrics, such as memory and active server page metrics, and also process level metrics that are important in determining application pool health.
Applications may also be deployed across many Elastic Beanstalk environments to serve differing customer bases. This, coupled with the ephemeral nature of most Elastic Beanstalk components, means dynamic dashboards are essential to providing views into the health of the application and environment. Integrating CloudWatch metrics into AMG provides the ability to create custom dashboards that instantly reflect the quickly changing Elastic Beanstalk environments and their resources.

Details of solution and implementation steps can be found in this blog post [insert link].

## Security

See [CONTRIBUTING](CONTRIBUTING.md#security-issue-notifications) for more information.

## License

This library is licensed under the MIT-0 License. See the LICENSE file.

