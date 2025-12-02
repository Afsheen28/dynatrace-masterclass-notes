# dynatrace-masterclass-notes
## Section One and Two were walkthroughs.

## Section Three: Infrastructure Observability

### Host Performance Data:
* Dynatrace can monitor various issues, which include ten key resource events. These are:
  * Unexpected high traffic
  * CPU saturation
  * Memory saturation
  * Low disk space
  * Slow disk performance
  * Low number of nodes available
  * High network utilization
  * Long garbage collection times
  * IO command skew
  * Custom resource contention event
* Dynatrace monitors normal traffic patterns and alerts users when it detects an unusual spike. Note that this alerting feature must be manually enabled in the settings.
* There are specific thresholds set for CPU and memory usage that trigger alerts:
  * For Windows systems: alerts when CPU usage exceeds 95% and memory usage surpasses 90%.

### Host Problems Monitoring
* Talks about his problems and certain features in the User Interface on how to find out information about the problem using graphs that give numeric information.

### Types of Dynatrace Problems monitoring
* Alerts for CPU and memory usage are triggered when:
  * CPU exceeds 95% utilization
  * Memory utilization surpasses 90% on Windows systems
* The importance of being aware of these features is emphasized. Users are encouraged to refer to the official Dynatrace guide for detailed information and to customize their monitoring setup based on specific needs.
* https://docs.dynatrace.com/docs/discover-dynatrace/platform/davis-ai/root-cause-analysis/concepts/events/event-types/resource-events
* This website shows the detection and analysis of problems that could come up.

### Host Availability
* Host availability refers to the status of a host in relation to whether it's online and accessible. Monitoring host availability helps in assessing the stability and uptime of applications and services.
* Dynatrace provides tools to continuously monitor the availability of hosts. This includes checking if hosts are reachable and how they respond to requests.
* Users can set up alerts to be notified if a host goes down or becomes unavailable, enabling quick responses to potential system failures.
* Continuous monitoring of host availability is critical for ensuring system reliability. It helps prevent downtimes that could disrupt business operations and user experience.
* Users can drill down to get more detailed information about host availability, including specific metrics related to performance and accessibility.

### Host Processes Monitoring
* Users can navigate to the Dynatrace interface to access host information by clicking on "Infrastructure" and then "Hosts." This provides an overview of all hosts where Dynatrace is deployed.
* Once Dynatrace is set up, it collects various metrics over time, allowing users to observe current performance data. Metrics include:
  * CPU usage (e.g., current CPU usage at 33%)
  * Memory usage (e.g., memory usage at 79%)
  * Historical usage data, giving insights over time.
* Introduces the processes section on the hosts page, where users can view all running processes.
* Users can expand the view to see a complete list of processes.
* Example process: Google Chrome.
* Access detailed metrics and properties related to the selected process.
* Real-time metrics reflect the current state, noting that metrics can change dynamically (e.g., increased traffic while streaming).
* Users can analyze how resource usage has changed over time for each process.
* Discusses responsiveness, memory worker processes, and input/output (IO) metrics essential for understanding overall performance.
* Users are urged to look for unfamiliar processes that may consume unnecessary resources.
* Encourages optimizing and cleaning the host environment.

### Host Events
* Explanation of what qualifies as an event in the context of hosts and their significance.
* Can find this in the `Afsheen` deployment tab on the bottom.
* Overview of different types of events that can be monitored, such as system alerts, warnings, and informational messages.
* Guidance on viewing and accessing event logs to understand historical data and event trends.
* Emphasis on the importance of these logs for troubleshooting and optimizing host performance
* Discusses metrics associated with events that are critical for assessing host health, including CPU usage and network performance.
* Tips on identifying patterns or recurring issues based on the events logged, which can help in preemptive troubleshooting.
* Recommendations for actions to take based on the types of events recorded, such as optimizing configurations or addressing hardware limitations.

### Host Logs
* Host logs provide crucial insights into the activity and performance of hosts over time, aiding in troubleshooting and performance optimization.
* Different types of logs can be collected from hosts, such as system events, application events, and security logs.
* Users learn how to access and navigate through log data within Dynatrace for analysis.
* Filters can be applied to narrow down logs by attributes such as tags or process groups, making it easier to correlate logs with specific applications.
* The importance of setting up log ingest rules to efficiently collect and manage logs based on defined patterns or attributes is emphasized.
* Tagging processes and hosts can greatly enhance the organization and retrieval of logs, helping to relate them directly to specific applications.
* Users can extract custom attributes from logs during ingestion, which can facilitate better analysis and filtering.
* PurePath tracing is highlighted as a valuable feature that allows linking logs directly to user sessions or transactions, enhancing the context for alerting and troubleshooting.

### Quick tip on the Timeframe selector
* The timeframe selector allows users to define the period for which they want to view data, enabling the analysis of events and metrics over specific intervals.
* Users can see an interactive timeline that visually represents when events occurred within the specified timeframe, making it easy to track changes and issues.
* Users are encouraged to adjust the timeframe to analyze different periods, from the last hours to days, providing flexibility in monitoring events.
* For instance, switching from "Last 2 Hours" to "Today" to see a broader range of events.
* By selecting different timeframes, users can uncover patterns and recurring issues. This visibility helps to identify events like system downtimes or performance bottlenecks that may not be apparent over shorter periods.
* Users can click on specific events in the timeline to access detailed information about incidents, such as duration and impact.

### Full Stack vs Infrastructure Only Monitoring
* Full Stack Monitoring encompasses tracking all components of the application stack, from the user interface to servers, including application performance and infrastructure metrics.
* It provides a comprehensive view of the application’s performance and user experience, integrating data from various sources.
* Infrastructure Only Monitoring:
  * This type focuses solely on the underlying infrastructure, such as servers, networks, databases, and hardware components, without considering application-level performance.
  * It is primarily concerned with the health and performance of hardware and services that support applications.
* Full Stack Monitoring is ideal for teams needing insights into user interactions, application behavior, and system performance to ensure optimal user experiences.
* Infrastructure Only Monitoring is suitable for operations and IT teams that need to oversee backend health and resolve system-level issues.
* Full Stack Monitoring helps in pinpointing performance issues at both the application and infrastructure levels, allowing for faster troubleshooting and enhanced user satisfaction.
* Infrastructure Only Monitoring simplifies the focus on hardware and backend processes, making it easier to manage server performance and service availability.
* Organizations may benefit from a combination of both approaches depending on their needs, infrastructure complexity, and application architecture.
  
### Frequent Issues feature
* Purpose of the Frequent Issues Feature:
  * This feature helps in identifying issues that occur frequently within an application, such as errors or performance problems, and suppresses alerts for these recurring issues, allowing teams to focus on new or critical matters.
* Alert Management:
  * Users can configure their alert settings for frequent issues. By default, alerts for these issues might be suppressed to prevent notification overload.
  * Some users may prefer to receive alerts for all problems, including frequent ones, and can turn off the suppression feature by navigating to settings.
* Adjusting Settings:
  * To modify the settings, go to Settings -> Anomaly Detection -> Frequent Issue Detection. Here, users can enable or disable the feature for applications, transactions, services, or infrastructure.
* Impact of Changes:
  * Once the suppression feature is turned off, users will start receiving alerts for issues that were previously categorized as frequent, allowing for awareness of recurring problems.
* Analysis of Issues:
  * Users can leverage the Dynatrace API to obtain a list of request issues detected and alerts suppressed by the frequent issues feature. This includes using the problems API to fetch relevant data.

### Renaming your host
* You can customize host names, which can be useful for better organization and identification. When a new custom name is assigned, it will overwrite the default role name associated with the host.
* To rename a host, you navigate to the settings of the specific host. If you choose to reset the hostname, the system will use the custom role name you've created instead of reverting to the DNS name.
* To rename multiple hosts automatically, you can create rules for host naming.
* Access this feature via Settings → Monitoring → Host Naming.
* You can define the hostname format using placeholders, such as CPU cores, and specify conditions like host groups or specific technologies.
* After configuring a naming rule, you can use the preview option to see how the new names will appear for the matching hosts before applying the changes.

### Exclude specific Disks and Network traffic from monitoring
* By default, Dynatrace monitors all disks and network traffic on your host. Excluding specific disks or network traffic can help streamline monitoring and reduce alert noise.
* To exclude a disk, navigate to the host page in Dynatrace and click on Settings.
* From the settings menu, locate the Disk Options section, where you can find the option to exclude disks.
* You can add a disk exclusion rule, specifying the operating system and the disk path you want to exclude (e.g., "C:").
* You can similarly exclude specific network traffic by accessing the appropriate settings in the monitoring configuration.
* Ensure that you adequately specify the parameters to correctly identify which traffic should not be monitored.

### Network Monitoring
* Dynatrace provides a comprehensive interface for monitoring network performance across your applications and infrastructure. This allows for easy identification of network-related problems.
* Users can click on specific processes to access detailed insights about individual network performance. This feature makes troubleshooting more straightforward and efficient.
* It’s recommended to explore the various options available within the network monitoring section to become familiar with the functionality. Regular exploration can help to spot potential issues before they escalate.
* While the course provides an overview of many functionalities, setting up specific alerting profiles and creating custom alerts related to network performance might not be covered in detail. Understanding the monitoring capabilities can help inform when and how to set alerts.
* If you experience problems such as "no network data" being shown (e.g., getting zero for traffic, packets, or connectivity), common troubleshooting steps may include:
  * Agent Deployment: Ensure the Dynatrace OneAgent is correctly deployed and running on the host.
  * Firewall Settings: Check firewall or security software to ensure there are no blocks preventing data communication.
  * Network Connectivity: Confirm that there is active network connectivity on the machine.