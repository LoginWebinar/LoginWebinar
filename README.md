# LoginWebinar

A suite of services dedicated to live streaming and video playing that can create online gated communities

## Description

The LoginWebinar is an self-hosted platform designed to allow any AI service in order to build the webpages rather than a site builder.  The backend service allows the administator the abililty to upload digital assets
that are to be used on pages, define the pages and some functions and page flows.

The MCP WebApp is used to build the site pages that an administrator will perform. The administrator must have an program loaded locally such as Claude, ChatGPT that can consume a MCP service

The LoginWebinar application will host the pure html/javascript/css pages in a Production, QA, and DEV modes.

LoginWebinar itself does not contain any AI capability, the system itself can be viewed as a repository of the data, images that is to be used by the MCP WebApp.

An attendee will be able to Register, Login, Watch a live webinar/video.


## Getting Started

Basic - Fully self contained, supports up to 200 viewers depending on server details
Standard - Used if running a seperate Postgres database server, 500 - 5,000 attendees depending on server details
Enterprise - Each service is deployed on a different service - Greater and 5,000 attendees


### Dependencies

* Debian OS
* Docker
* NextJs
* Postgres
* Go Lang
* AI Service on local workstation


### Services

* APISERVICE_API - Does not need to be public facing. This service communicates to the Postgres database server. Developed in Go.
    -DEPENDENT:
        POSTGRES
* HEARTBEATSERVICE_WS - Public facing. This websocket service is used by attendees and adminstrators to create bi-communication channels. Develop in Go.
    - DEPENDENT:
        POSTGRES
* MAINWEB-APP - Public facing. This service is used by the administrator and attendees. Developed in Nextjs 15, React 19.
    - DEPENDENT:
        API-SERVICE
        HEARTBEATSERVICE_WS
* MCPWEB-APP - Does not need to be public facing, can reside inside a companies network. Administrator access only. Using X-API-KEYS for security. Developed in Nextjs 15, React 19.
    - DEPENDENT:
        API-SERVICE

### Installing

* How/where to download your program
* Any modifications needed to be made to files/folders

### Executing program

* How to run the program
* Step-by-step bullets


## Help

Any advise for common problems or issues.


## Authors

Contributors names and contact info

Rob Helmstetter email:rob@loginwebinar.com


## Version History

* 0.2
    * Various bug fixes and optimizations
    * See [commit change]() or See [release history]()
* 0.1
    * Initial Release

## License

This project is licensed under the NOT Licensed - see the LICENSE.md file for details

## Acknowledgments



