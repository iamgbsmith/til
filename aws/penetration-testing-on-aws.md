# Penetration Testing On AWS

__Category: AWS__

AWS have very specific requirements for performing penetration testing on their platform. You may not as part of penetration testing do any of the following: 

* DNS zone walking via Amazon Route 53 Hosted Zones
* DoS attacks
* DDoS attacks
* Port Flooding
* Protocol Flooding or Request Flooding (login request flooding, API request flooding)

You can perform security assessments or penetration tests against AWS infrastructure without prior approval for the following 8 "Permitted Services":

* Amazon EC2 instances, NAT Gateways, and Elastic Load Balancers
* Amazon RDS
* Amazon CloudFront
* Amazon Aurora
* Amazon API Gateways
* AWS Lambda and Lambda Edge functions
* Amazon Lightsail resources
* Amazon Elastic Beanstalk environments

See [AWS Customer Support Policy for Penetration Testing](https://aws.amazon.com/security/penetration-testing/) for more details.
