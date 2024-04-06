
# Installing the CloudWatch agent on EC2 instances

Installing the CloudWatch agent on EC2 instances allows seamless integration with Amazon CloudWatch, enabling collection and transmission of system metrics, logs, and events for comprehensive monitoring and analysis.



## Run Command

#install the agent

```bash
  wget https://s3.amazonaws.com/amazoncloudwatch-agent/amazon_linux/amd64/latest/amazon-cloudwatch-agent.rpm 
```

```bash
  sudo rpm -U ./amazon-cloudwatch-agent.rpm
```

#run the wizard

```bash
  sudo /opt/aws/amazon-cloudwatch-agent/bin/amazon-cloudwatch-agent-config-wizard
```

#create some missing files

```bash
  sudo mkdir -p /usr/share/collectd
```
```bash
  sudo touch /usr/share/collectd/types.db
```

#options:

```bash
  sudo /opt/aws/amazon-cloudwatch-agent/bin/amazon-cloudwatch-agent-ctl -a fetch-config -m ec2 -c ssm:AmazonCloudWatch-linux -s
```

```bash
 sudo /opt/aws/amazon-cloudwatch-agent/bin/amazon-cloudwatch-agent-ctl -a fetch-config -m ec2 -c file:/opt/aws/amazon-cloudwatch-agent/bin/config.json -s
```

## Screenshots

![App Screenshot](https://s3.amazonaws.com/mejba.me/installing-the-cloudwatch-agent-on-ec2-instances.png)

