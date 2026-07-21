---
title: "Blog 2"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 3.2. </b> "
---

# AWS Compute Blog | Amazon EC2 Auto Scaling Group – What I learned about automatic scaling on AWS

Hello everyone,

While studying and working on AWS projects, I had the opportunity to explore many Amazon EC2 services. One of the services that impressed me most was **Amazon EC2 Auto Scaling Group (ASG)**.

At first, I thought Auto Scaling simply meant “automatically creating more EC2 instances.” After reading AWS documentation and articles, however, I realized that it not only scales a system but is also an important part of building highly available, stable cloud applications.

![System architecture using Amazon EC2 Auto Scaling Group](/images/sodo1.drawio.png)

## What I previously misunderstood about Auto Scaling Groups

When I first started learning AWS, I always wondered:

> “Isn't one EC2 instance enough to run a website? Why would we need multiple instances?”

A sufficiently powerful EC2 instance can indeed serve many users at once.

The real issue is not whether one instance can run the application, but what happens when traffic suddenly spikes or the server fails.

That is exactly why Auto Scaling Groups were designed.

## An Auto Scaling Group does more than add EC2 instances

What I found most interesting is that many people, including my former self, think Auto Scaling only creates more servers.

After learning more, I realized that an Auto Scaling Group actually manages the entire EC2 instance lifecycle.

It can:

- Automatically launch new EC2 instances when system load increases.
- Automatically reduce the number of instances when demand is low.
- Automatically replace failed instances.
- Always maintain the number of instances configured by the administrator.

This keeps the system stable without requiring administrators to monitor it continuously.

## Self-healing is the feature I value most

In my view, this is the most valuable capability of an Auto Scaling Group.

Suppose a system is running three EC2 instances. If one instance fails or does not pass its health check, the Auto Scaling Group automatically launches a replacement.

The entire process is nearly automatic. Users will hardly notice that a server failed behind the system.

This is also why production systems on AWS commonly combine an Auto Scaling Group with an Application Load Balancer.

## CloudWatch plays an important role

Another thing I learned is that an Auto Scaling Group does not “guess” when it should scale. It operates based on metrics provided by Amazon CloudWatch.

For example:

- CPU utilization exceeds 70%.
- The request volume rises significantly.
- Network traffic increases sharply.

CloudWatch sends a signal that allows the Auto Scaling Group to decide whether to launch additional EC2 instances.

Conversely, when demand decreases, the Auto Scaling Group can reduce the number of instances to save costs. This makes system scaling fully automatic.

## An Auto Scaling Group is not always necessary

I believe this is another point that many AWS beginners misunderstand.

If you are only building:

- A personal website.
- An internal website.
- A demo system.
- A small academic project.

then a single EC2 instance may be entirely sufficient. Adding an Auto Scaling Group can sometimes introduce unnecessary complexity and cost.

However, for systems serving many users or requiring high availability, an Auto Scaling Group is certainly worth considering.

## Personal perspective

After learning about Auto Scaling Groups, I realized that building a cloud system involves more than launching an EC2 instance and running an application.

More importantly, the system must be prepared to scale when user demand grows and recover automatically when a server fails.

To me, Auto Scaling Groups clearly demonstrate the AWS system-design philosophy: helping a system not only run, but remain ready for real-world change.

## Conclusion

For me, Amazon EC2 Auto Scaling Group is more than a service that automatically launches additional EC2 instances.

It is a solution that helps a system:

- Scale automatically with demand.
- Improve application availability.
- Reduce operational effort.
- Optimize costs as traffic changes.

If you are learning AWS or preparing to deploy a real cloud application, I believe Auto Scaling Group is a service well worth studying.

Thank you for taking the time to read my post. If you have deployed Auto Scaling Groups in practice, I would be very interested in hearing your experience and perspective.

**Reference:** [Introducing Instance Refresh for EC2 Auto Scaling](https://aws.amazon.com/blogs/compute/introducing-instance-refresh-for-ec2-auto-scaling/)
