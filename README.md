# Ec2-memory-and-disk-monitoring-with-cloudwatch-and-ssmmanager. 

This is automation of EC2 CPU utilization monitoring. Saves time compared to when you have to configure manually.

Log on to the AWS Management console
Navigate to IAM. Create a new role for AWS service EC2. Attach 'CloudWatchFullAccess' and 'SSMManagerFullAccess' policies and create role.

Navigate to SSM Manager and under application management, click on parameter store.
Click on create paramater. Default standard. Choose a name 
Copy and paste the parameter policy (Available in this repository) in the Value box and create parameter.

Navigate to EC2 to create an instance.
The sure to assign the IAM role you created to the instance
Copy and paste the EC2user datascript. Ensure to edit the EC2 user datascript part between ssm:'.........'-s to the name of the parameter you created.
Launch the instance.
Click on instance connect. Run the EC2 cloudwatch status check command (Available in this repository)
It should show installed and running if properly configured.

Navigate to Cloudwatch. Click on all metrics. Click on CWAgent to view your metrics.

You can also set up alarm to notify you of high CPU useage. You can create an SNS topic to receive nofications on these cloudwatch metrics.
