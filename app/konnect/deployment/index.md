---
title: Deployment Overview
no_version: true
---
## Architecture

The {{site.konnect_product_name}} platform provides a SaaS control plane (CP),
which manages all Service configurations. It propagates those configurations to
all runtime nodes, which use in-memory storage. These nodes can be installed
anywhere, on-premise or in the cloud.

Runtime nodes, acting as data planes, listen for traffic on the proxy port 443
by default. The {{site.konnect_short_name}} SaaS control plane evaluates
incoming client API requests and routes them to the appropriate backend APIs.
While routing requests and providing responses, policies can be applied with
plugins as necessary.

![Konnect SaaS Architecture](/assets/images/docs/konnect/Konnect-architecture-wide.png)

For example, before routing a request, the client might be required to
authenticate. This delivers several benefits, including:

* The Service doesn’t need its own authentication logic since the data plane is
handling authentication.
* The Service only receives valid requests and therefore cycles are not wasted
processing invalid requests.
* All requests are logged for central visibility of traffic.

## Compatibility

### Supported Browsers

|                                  | IE | Edge | Firefox | Chrome | Safari |
|----------------------------------|:--:|:----:|:-------:|:------:|:------:|
| {{site.konnect_short_name}} SaaS |  <i class="fa fa-times"></i> | <i class="fa fa-check"></i> |  <i class="fa fa-check"></i> |  <i class="fa fa-check"></i> | <i class="fa fa-check"></i> |

### Runtime Compatibility

<div class="alert alert-ee blue">
<b>Note:</b> Currently, the only supported runtime type in
{{site.konnect_short_name}} SaaS is a
<a href="/enterprise/latest/introduction">{{site.ee_gateway_name}}</a>
data plane.
</div>

|                                   | {{site.konnect_short_name}} SaaS |
|-----------------------------------|:--------------------------------:|
| {{site.ee_product_name}} 2.3.x    | <i class="fa fa-check"></i>      |
| {{site.ee_product_name}} 2.2.x or earlier | <i class="fa fa-times"></i>      |