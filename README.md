Project 2 in the Udacity AWS Cloud Architect nanodegree

Plan, design, provision, and monitor infrastructure in AWS using industry-standard and open source tools. Practice the skills you have learned throughout the course to optimize infrastructure for cost and performance. Use Terraform to provision and configure AWS services in a global configuration.

Project files from [here](https://github.com/Marvinsky/aws_design_provision_monitor_infraestructure_scale).


<h3>Before you get started</h3>

*   [AWS CLI](https://aws.amazon.com/es/cli/).

*   [Terraform](https://www.terraform.io/).


You will also need user accounts for AWS and Terraform.

<h3>Permissions</h3>
The task carried out for this project should be carried out by a user logged in with the IAM role of Administrator with access to Billing information. You can learn more about setting up a user with the Admin role here: 

[Creaating Your First Admin User and Group](https://www.terraform.io/).

<h2>Task 1: Create AWS Architecture Schematics</h2>

<h5>Part 1</h5>

[`Udacity_Diagram_1.pdf`](resources/Udacity_Diagram_1.pdf)

<h5>Part 2</h5>

[`Udacity_Diagram_2.pdf`](resources/Udacity_Diagram_2.pdf)

<h2>Task 2: Calculate Infraestructure Costs</h2>

<ol>
<li>Estimate how much it will cost to run the services in your Part 1 diagram for one month.
<ul>
<li>Target a monthly estimate between $8,000-$10,000</li>
<li>Be mindful of AWS regions when you are estimating costs</li>
</ul>

[`Initial_Cost_Estimate.csv`](resources/Initial_Cost_Estimate.csv)
</li>
<li>Configure your estimates for the following scenarios:
<ul>
    <li>Your budget has been reduced from $8,000-$10,000 to a maximum of $6500. What services will you modify to meet this new budget?</li>

<h4>How I reduced the estimate to $6,500?</h4>
<ul>
    <li>Change the instance type for ec2 from t2.xlarge to t2.large ($1,378.88 -> $701.44) <b>Reason</b>: The performance can be reduced. However, we still can scale if we want to.</li>
    <li>Change model pricing from on-demand to reserved instances.<b>Reason</b>: Reserving instances for 1 year will reduce cost for the architecture. However, we lock the application platform to use the same infraestructure for one year. Nevertheless, more resources can be added.</li>
    <li>Scale down RDS instance from: db.m5.4xlarge to db.m5.2xlarge. <b>Reason</b>: We will have performance issue in the database. But, it can be bearable.
</ul>

[`Reduced_Cost_Estimate.csv`](resources/Reduced_Cost_Estimate.csv) 

<li>Your budget has been increased to $20,000. What resources will you add and why? Think about where to add redundancy and how to improve performance. Re-configure your estimate to a monthly invoice of $18K-$20k.
</li>

<h4>How I come up with an estimated cost of $20,000?</h4>

<ul>
    <li>Add more instances (Scale out) and load balancer. <b>Reason</b>: Provide high availability for the application. Even if Northern Virginia region is completely down, application will be up and running in Oregon Region.</li>
    <li>Add RDS database instance in Oregon Region. <b>Reason</b>: In order to reduce latency for end users accessing the application in other region. Read Replica can be in Oregon region.</li>
    <li>Add resources to RDS (Scale up) to database instance. <b>Reason</b>: Improve database performance and would be useful in case of huge traffic on application.</li>
</ul>


</ul>
</li>
<li>fgdfgf</li>
</ol>


