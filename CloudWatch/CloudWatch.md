#Service 

- Collects and manages operation data on the users behalf
- Metrics - AWS Products, Apps, on-prem systems
	- CPU usage
	- number of visitors per second to service
- CloudWatch Logs - AWS Products, Apps, on-prem systems
- CloudWatch Events - AWS Services & Schedules
	- ex. If an EC2 instance is started, CloudWatch creates an Event which could be used to do something else

# Namespace
- Container for monitoring data
- Way to separate data into different areas
- Services have a default Namespace in the form of `AWS/<ServiceName>`, for example, EC2 has AWS/EC2
### Metric
- Collection of related data points in a time or data structure
	- ex. CPU Usage, Network I/O, Disk I/O
	- Time ordered
- Metrics are not for a specific server

### Datapoint
- Say we have a [[#Metric|Metric]] called CPU Utilization
- Every time, for example, EC2 sends that metric to CloudWatch
	- This measurement is called a data point
	- Consists of
		- Timestamp
		- Value
- How do we separate these EC2 instances, for example?
	- Send a [[#Dimension|Dimension]]

### Dimension
- Dimensions **separate data points for different things or perspectives within the same metric**.
	- For example, AWS EC2 sends InstanceID as a dimension

# Alarm
- Alarms are tied to a specific metric
### OK State
- Everything is fine, hasn't triggered anything
### Alarm State
- Creates some action based on rules configured.
	- ex. Create a message and send it over SNS