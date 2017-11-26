---
comments: true
title: Realtime streaming aws cloudwatch on terminal
categories:
  - CLI
tags:
  - aws
  - cli
  - cloudwatch
---

Sometime when we deploy our app on ElasticBeanstalk or testing our lambda function, we want to check the log for debugging.
Using [AWS CloudWatch](https://aws.amazon.com/cloudwatch/), we can download and see the logs from various AWS Service.
However, sometime we want to check the logs realtime on our terminal.
Luckily, there is a CLI app for that.

[awslogs](https://github.com/jorgebastida/awslogs) is a cli tool for querying and streaming from CloudWatch logs.

Installation
-----

`pip install awslogs`


Usage
-----

* ``awslogs groups``: List existing groups
* ``awslogs streams GROUP``: List existing streams withing ``GROUP``
* ``awslogs get GROUP [STREAM_EXPRESSION]``: Get logs matching ``STREAM_EXPRESSION`` in ``GROUP``.


Example
-----

`awslogs get /aws/lambda/aws-lambda-image  ALL --watch`

![awslogs in action]({{"assets/images/awslogs.png" | absolute_url}})
