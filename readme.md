# TTAC + Exactly Labs Broadband Project: Technology Overview and Processes

This set of documentation shares details on the technology choices made, operations instructions, security, and internal process and practices of development.

## Components

This project is composed of several different components each of which make use of different technologies and architectures given the components requirements and constraints. The projects currently include:

* **Radar**: Web application and software for monitoring of network and internet quality at physically remote sites.
* **MLab-Processor**: Project which takes the raw source data from the Measurement Lab and puts it into easier to query formats. This project also adds metadata such as geographies a specific test was run in as well as information on the ISP the test was run using.
* **MLab-Mapping**: This project visualizes the results of the **MLab-Processor** project. This project is intended to be a public-facing website which allows anyone to better understand the broadband connectivity of locations of interest.

## Process

Each project follows a similar set of processes around project management and implementation. The exact day-to-day process will, however, depend on the phase of the project. For example, a project earlier in its lifetime will receive different treatment than a project later on.

## Operations

Each project has its own operational requirements. For each project, see its documentation:

* [Radar](./radar/index.md)
* [MLab-Processor](./mlab-processor/index.md)
* [MLab-Mapping](./mlab-mapping/index.md)

## Security

Security requirements differ per project. For example, Radar involves the connection of physical devices on mamy different local networks. As a result, its security requirements are much higher where as the MLab-Processor is intended for use offline with public input data as well as processed data which is not sensitive. For each project's specific security requirements see:

* [Radar](./radar/index.md)
* [MLab-Processor](./mlab-processor/index.md)
* [MLab-Mapping](./mlab-mapping/index.md)
