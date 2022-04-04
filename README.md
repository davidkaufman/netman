# netman
Mange Local Development Environments

## SYNOPSIS

    netman create dev.myproject --db --api --gitlab myproject

### Output:

    Cloning ssh gitlab.com/myproject into ~/dev/myproject/ ... OK
    Starting on local IP 127.0.0.1 and high port 3001 ... OK
    Adding apache virtualhost dev.myproject.conf as reverse proxy ... OK
    Creating database from migrations ... OK
    Starting 1 mariadb, 1 nginx-ssl and 2 centos7 containers ... OK
    App running at: https://dev.myproject.local/
    API running at: https://db.myproject.local/
    DB running at: dbuser:s3c3rt@db.myproject.local:3360/myproject
    
    Use netman stop, restart, pause to control, netman help for more

## MOTIVATION

As a developer, I need a tool to easily create and manage numerous development environments on my laptop.  Every dev environment requires one or more public or privatte network endpoints, behind which may be web, api, database, or other services running inside containers.  Endpoints are also needed for more advanced services like reverse proxies, load balancers, SSL termination, even smtp, sms, sftp and ssh gateways.

Other than the code being developed itself, all of those other things, the endpoints and the services running behind them, can be created, configured, controlled and canceled (cleared, cut, closed, concluded, ceased, croaked? oofed?) automatically.

This tool implements an opinionated policy of how host names should be derived, how ip addresses and port numbers should be assigned, how services should be connected and chained together with one another so that new environments can be created, existing ones moved, modified, paused & archived easily.
