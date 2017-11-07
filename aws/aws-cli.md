AWS Elastic Cloud Compute (EC2)
====

You get a server! And you get a server! And you get a server! Everyone gets a server!

Creating a new instance
----

Using the AWS management console:
http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EC2_GetStarted.html

Using the AWS CLI: 
http://docs.aws.amazon.com/cli/latest/userguide/tutorial-ec2-ubuntu.html

Security Groups
----

A security group acts as a virtual firewall that controls the traffic for one or more instances. When you launch an 
instance, you associate one or more security groups with the instance. You add rules to each security group that allow 
traffic to or from its associated instances. You can modify the rules for a security group at any time; the new rules are 
automatically applied to all instances that are associated with the security group. When we decide whether to allow traffic 
to reach an instance, we evaluate all the rules from all the security groups that are associated with the instance.

Each of your instances is part of a security group. Keep you security groups as closed as possible.
You only want to open the absolutely required ports to the absolutely required IP adresses.

More info: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-network-security.html

Creating Images (backups) of your instances
----

Images are just what they sound like. An image of your server at a given point in time. I image my servers pretty regularly
and only keep the most recent 2 or 3 around. (This process has saved me many times from catastrophic failure.) 
You can launch a new EC2 instance from an image at any time and it will boot
up in the exact state as the image your created the image from, at the time you created the image.

To create an image of your server:
> * select your instance from your list of instances 
> * click on "Actions" dropdown
> * hover over "Image" 
> * select "Create Image"
> * follow instructions

Elastic IPs
----

If you need a persistant IP address (one that does not change every time you shutdown and restart your computer) or you 
are working on a more sophisticated application, using load balancers and more, you'll need to use a static IP address.

To use a static IP:
> * select "Elastic IPs" from left navigation of EC2 page
> * click "Allocate new address"
> * associate your new Elastic IP with a running EC2 instance you have running

Now your EC2 instance will be tied to that Elastic IP until you release it.

Load Balancing
----

Elastic Load Balancing automatically distributes incoming application traffic across multiple Amazon EC2 instances. It 
enables you to achieve fault tolerance in your applications, seamlessly providing the required amount of load balancing 
capacity needed to route application traffic.

Using load balancers:
> * Create an account and sign into the console
> * Create a load balancer
> * Specify a unique name and a network
> * Create listeners for your load balancer (HTTP, HTTPS, TCP, or SSL)
> * Configure health checks for your load balancer

Do one of the following:
> * Manually register EC2 instances to your load balancer
> * Associate your load balancer with an Auto Scaling group