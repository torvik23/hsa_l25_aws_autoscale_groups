# HSA L25: AWS autoscale groups

## Task
* Create an auto-scale group that will contain one on-demand instance and will scale on spot instances
* Set up scaling policy based on AVG CPU usage
* Set up scaling policy based on request amount that allows non-linear growth

## Getting Started

#### 1. Create AMI Image
![AMI Image](./resources/aws_ami_image.png)

#### 2. Create Launch Template
![Launch Template](./resources/aws_launch_template.png)

#### 3. Create Auto Scaling Group
Details:
![Auto Scaling Group Details](./resources/aws_autoscale_group_details.png)

Instance Purchase Options:
![Instance Purchase Options](./resources/aws_autoscale_instance_purchase_options.png)

Dynamic Scaling Options:
![Dynamic Scaling Options](./resources/aws_autoscale_dynamic_scaling_options.png)

## Tests
### Check auto-scaling. Run the benchmark load test:
```bash
$ siege -b -c1000 -t10m hsa-lb-autoscale-1876688932.eu-central-1.elb.amazonaws.com
```

CloudWatch CPU Utilization Alarm:
![CloudWatch CPU Utilization](./resources/aws_cpu_utilization.png)

CloudWatch High RPS Alarm:
![CloudWatch High RPS Alarm](./resources/aws_high_rps_alarm.png)

Auto-scaling group activity history:
![Auto-scaling group activity history](./resources/aws_autoscale_activity_history.png)

Auto-scaling running instances:
![Auto-scaling running instances](./resources/aws_running_instances.png)