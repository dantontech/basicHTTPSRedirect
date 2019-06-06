# Basic Maintenance Page

This is a basic HTTPS redirect service for when you need to point one domain to another domain.

## Acknowledgements

* [abiosoft/caddy](https://hub.docker.com/r/abiosoft/caddy/)
* [Docker](https://www.docker.com/)


## Requirements

* A server running Docker that can bind to port 80 and 443
* [A valid domain that meets the following criteria.](https://caddyserver.com/docs/automatic-https)

## Instructions

### Clone this repository:

```
git clone https://github.com/dantontech/basicHTTPSRedirect.git
```

### Switch to the respository directory:

```
cd basicHTTPSRedirect
```

### Switch to the cfg directory:

```
cd cfg
```

Using your preferred editior, change the following information in Caddyfile.

+  Change line 1 to be your new domain.
+  Change line 2 to be your email address after tls.
+  Change line 3 to be the domain you want to redirect to.

### Switch back to the root of the git repository:

```
cd ..
```

### Run the following command:

```
docker run --name basicHTTPSRedirect -d -e ACME_AGREE=true -v $(pwd)/cfg/Caddyfile:/etc/Caddyfile -p 80:80 -p 443:443 abiosoft/caddy
```

If all is well you should be redirected when you visit your new domain.
