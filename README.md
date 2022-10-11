<h1> CI/CD pipeline Deployment 3 - URL Shortner </h1>

<h3> Please download the documentation from : https://github.com/bikigrg11/kuralabs_deployment_3/blob/main/documentation.docx   </h3>
                                                                                                
<h3> Name: Biki Gurung <br>
</h3>

<h3>Version	Date</h3>
<table>
<tr>
<td> V 1.0 </td>
<td> 09/05/2022 </td>
</tr>
<tr>
<td> V 2.0 </td>
<td> 09/22/2022 </td>
</tr>
 <tr>
<td> V 3.0 </td>
<td> 10/08/2022 </td>
</tr>
</table>

<h3>Description:</h3>
<li> Create a VPC with Public and Private Subnet
<li> Deploy your Flask app into your VPC using Jenkins Agent
<li> Use NGINX and gUnicorn to Deploy your application
<li> Use Jenkins for CI / CD Pipeline - Build, Test and Deploy application 
<li>	Use Elastic Beanstalk to deploy application
<li>	Use AWS CloudWatch to Monitor
<li>	Use Cypress and JUnit Test 
  

<h3> Pre-requisites: </h3> 
<li>	AWS account
<li> CI tool of choice (Jenkins)
<li> GitHub repository you’d like to deploy

<h2>Tables of Contents: </h2>
<br>

<li> Install Jenkins on an EC2:	3
<li> Install Virtual Environment	5
<li> Activate the Jenkins user on the EC2	6
<li> Create a Jenkins user in your AWS account	7
<li> Install AWS CLI on the Jenkins EC2 and configure	9
<li> Configure AWS CLI for Jenkins (Sub User)	9
<li> Install EB CLI in the Jenkins EC2 user	9
<li> Connect GitHub to Jenkins Server	10
<li> Create an access token from GitHub	11
<li> How to setup Jenkins:	12
<li> Create a multibranch build	14
<li> Configure and connect a Jenkins agent to Jenkins:	19
<li> How to Deploy application in Elastic Beanstalk	23
<li> Deploy application using Elastic Beanstalk CLI and Jenkins:	23
<li> How to Manually Deploy to Elastic Beanstalk	25
<li> How to create an Elastic Beanstalk Env	27
<li> Continuous Deployment (CD) using Jenkins and Elastic Beanstalk	29
<li> How to Setup NGINX with GUNICORN:	31
<li> How to start GUnicorn with Jenkins:	32
<li> List of Issues and their solution	32
<li> Modifications & Improvements to Pipeline	38
<li> Add a way to Monitor and Notify you	38
<li> Add CloudWatch Agent to Monitor your Jenkins Server	38
<li> Use Cypress for testing	42
<li> Add a Linter	42
<li> Change something on the application front	43
<li> What Improvements can be made?	45
<li> What stack has been implemented?	46
<li> Explaining the Stack, we are using: LEJP	46
<li> How is the application running – Overview?	46
<li> CI/CD Pipeline Diagram 3:	49







CI/CD Pipeline Diagram: https://github.com/bikigrg11/kuralabs_deployment_3/blob/main/deploy3.jpg

<br>
<hr>
<img src="https://github.com/bikigrg11/kuralabs_deployment_3/blob/main/deploy3.jpg">
<hr>


