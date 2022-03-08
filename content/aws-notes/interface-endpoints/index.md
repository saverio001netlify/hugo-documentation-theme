---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "AWS VPC Interface and Gateway Endpoints"
subtitle: ""
summary: 
  "Interface and Gateway VPC Endpoints allow private access to public VPC services without crossing the public Internet"
authors: []
tags: []
categories: []
date: 2022-03-08T17:36:59+01:00
lastmod: 2022-03-08T17:36:59+01:00
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []
---


VPC Endpoints allow access to public AWS services 
without transiting the public Internet.


When you configure an interface endpoint, you are asked
to specify the subnet (and consequently the AZ) where
the endpoint should be created.

At creation, an AZ-specific DNS entry is created, and your
app can use that to access the local endpoint.

On top of this, also a regional entry DNS entry for the service
is created; this means that:

1- All applications can keep on working just as before using
the DNS for the regional public endpoint (now remapped).

2- If you have multiple endpoint in multiple AZs, then the
regional DNS endpoint entry will return all endpoints.
Your application may use the endpoint in a different AZ,
incurring into inter-AZ data transfer charges.


## A few notes on S3 gateway endpoints

### No cross-region requests

S3 endpoints do not support cross-region requests.\
From [https://docs.aws.amazon.com/vpc/latest/privatelink/vpc-endpoints-s3.html](https://docs.aws.amazon.com/vpc/latest/privatelink/vpc-endpoints-s3.html):

> Endpoints currently do not support cross-Region requests—ensure that you create your endpoint in the same Region as your bucket. 

### Endpoint policies

Endpoint policies behave like "filter": any operation
which is not explicitly allowes will be denied, 
regardless from permissions associated to the principal
or to the resource. 

## DNS endpoints

