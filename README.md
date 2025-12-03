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

## Section Four: Cloud Automation

### Cloud Automation Intro
* Various cloud platforms available, including Kubernetes, Cloud Foundry, Amazon, Azure, Google Cloud Platform (GCP), and VMware. Understanding these options helps in selecting the right cloud environment for automation.
* This component is crucial for monitoring applications across different services such as frontend (web/mobile), databases, and distributed traces. The section emphasizes understanding user interactions with applications to improve experiences.
* The course will delve into security measures and analytics, process automation to identify vulnerabilities, and protection within your applications.
* This aspect focuses on analyzing user interactions to enhance digital engagement with the application, emphasizing the importance of user experience.
* Cloud Automation is positioned to provide insights into releases, service level objectives, and how to effectively use Dynatrace in a cloud setting. The demo mode activated by Dynatrace allows users to see the functionalities without a step-by-step implementation.

### Releases
* Dynatrace provides a built-in release analysis solution that allows you to track and validate software releases throughout your DevOps pipeline. This includes understanding the stages of the different deployed versions, identifying known bugs, and assessing risks associated with each release.
* The release inventory feature displays all detected releases, grouped by release and build versions, stages, and products. Each entry represents a process, and you'll find valuable insights such as the latest validation results irrespective of the time frame selected.
* When examining a specific release, you will see essential information including the release name, version, stage, product name, and associated technologies. It also shows the number of deployments, traffic routed to the release, and any potential third-party vulnerabilities that are important for making informed decisions about deploying the release.
* This feature lists the validations associated with the selected release, ensuring that you can track how each release is performing compared to past versions. You can also see related events, such as process restarts.

### Service-Level Objectives
* SLOs are measurable goals that define the expected performance and reliability of a service. They are critical for managing user expectations and maintaining service quality.
* You can define SLOs based on various metrics such as response time, error rates, availability, and throughput. By establishing clear metrics, you can ensure that your applications meet predefined performance standards.
* Dynatrace enables real-time monitoring of SLOs, allowing you to track whether your services meet the established objectives. If an SLO is breached, alerts can be configured to notify you of potential issues that could affect users.
* When deploying new software releases, Dynatrace allows you to assess how the changes impact your SLOs. This is essential for understanding if a new version improves or deteriorates performance compared to prior versions.
* By analyzing the data collected against your SLOs, you can identify trends and make data-driven decisions to enhance application performance and user satisfaction over time.
* SLOs can be applied in various scenarios, such as monitoring customer-facing applications or backend services, aligning operations with business goals, and ensuring that critical services remain available during peak times.

### Creating a new SLO
* Start by navigating to the service level objectives section in Dynatrace. Click on "Create New SLO" which is usually located at the top right corner of the page.
* You have several options to choose from based on what aspect you want to measure:
  * Service Level Availability: Measured by dividing the number of successful service codes by the total number of service codes.
  * Service Method Availability: Measured by dividing the successful key requests by the total key requests for that service.
  * Service Performance: This is a metric expression that represents the ratio between "good minutes" (where the response latency is below a certain threshold) and total minutes.
* For monitoring client-side objectives, you can set an SLO for user experience, which reflects the percentage of users who report satisfaction with the service.
* Once you've selected the desired SLO type, you'll need to define specific service level indicators (SLIs) that will be used to measure the success of the service. You'll also specify targets and the evaluation period for assessing performance.
* After providing all necessary details, save your new SLO. This will allow Dynatrace to begin monitoring the defined objectives and alert you if the service performance does not meet the established targets.


