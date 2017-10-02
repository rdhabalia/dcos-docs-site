---
layout: layout.pug
navigationTitle:  Marathon REST API
title: Marathon REST API
menuWeight: 40
excerpt:
featureMaturity:
enterprise: false
---

The Marathon API allows you to manage long-running containerized services (apps and pods).

The Marathon API is backed by the [Marathon component](/docs/1.10/overview/architecture/components/#marathon), which runs on the master nodes.

One of the Marathon instances is elected as leader, while the rest are hot backups in case of failure. All API requests must go through the Marathon leader. To enforce this, Admin Router proxies requests from any master node to the Marathon leader.

For more information about using Marathon, see [Deploying Services and Pods](/docs/1.10/deploying-services/).

## Routes

Access to the Marathon API is proxied through the Admin Router on each master node using the following route:

```
/service/marathon/
```

## Authentication (Enterprise Only)

Enterprise edition users must authenticate Marathon API requests.

To authenticate API requests, see [Obtaining an authentication token](/docs/1.10/security/ent/iam-api/#obtaining-an-authentication-token) and [Passing an authentication token](/docs/1.10/security/ent/iam-api/#passing-an-authentication-token).

The Marathon API also requires authorization via the following permissions:

| Route | Permission |
|-------|----------|
| `/service/marathon/` | `dcos:adminrouter:service:marathon` |

All routes may also be reached by users with the `dcos:superuser` permission.

To assign permissions to your account, see the [permissions reference](/docs/1.10/security/ent/perms-reference/).

## Resources

[api-explorer api='/docs/1.10/api/marathon.yaml']