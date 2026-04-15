# Cloud Computing & Web Services - Answers

## Q1
a) **What is SOAP? Describe the SOAP Messaging Architecture with a suitable diagram.**

SOAP (Simple Object Access Protocol) is a messaging protocol for exchanging structured information in the implementation of web services. It uses XML for its message format and relies on application layer protocols, most notably HTTP and SMTP, for message negotiation and transmission.

**SOAP Messaging Architecture:**

A SOAP message is an XML document with the following elements:
*   **Envelope:** The root element that identifies the XML document as a SOAP message.
*   **Header:** An optional element that contains application-specific information, such as authentication or transaction details.
*   **Body:** A mandatory element that contains the call and response information.
*   **Fault:** An optional element used for reporting errors.

**Diagrammatic Representation:**
```
+------------------------------------+
|           SOAP Envelope            |
| +--------------------------------+ |
| |           SOAP Header          | |
| | (Optional Application-specific | |
| |          information)          | |
| +--------------------------------+ |
| +--------------------------------+ |
| |            SOAP Body           | |
| | (Contains actual message data) | |
| +--------------------------------+ |
| +--------------------------------+ |
| |           SOAP Fault           | |
| |   (Optional error details)     | |
| +--------------------------------+ |
+------------------------------------+
```

---
b) **List and discuss different types of virtualizations.**

Virtualization creates a virtual version of a computing resource. Key types include:

1.  **Full Virtualization:** The hypervisor completely emulates the underlying hardware, allowing an unmodified guest operating system to run in isolation. The guest OS is unaware it is being virtualized. Example: VirtualBox.
2.  **Paravirtualization:** The guest operating system is modified to be aware of the virtualization layer. This allows for direct communication between the guest and the hypervisor, improving performance. Example: Xen.
3.  **Hardware-assisted Virtualization:** This leverages CPU features (e.g., Intel VT-x, AMD-V) to offload virtualization tasks from the hypervisor to the hardware, resulting in better performance and security. Example: KVM.
4.  **OS-level Virtualization (Containerization):** The OS kernel allows multiple isolated user-space instances, known as containers. Containers share the host OS kernel, making them more lightweight and faster than traditional VMs. Example: Docker.
5.  **Network Virtualization:** Combines hardware and software network resources into a single, software-based administrative entity. This allows for the creation of virtual networks that are decoupled from the physical network.

---
c) **Write a web service method that accepts currency in rupees as a parameter and returns in dollar using JAX-WS.**

```java
import javax.jws.WebService;
import javax.jws.WebMethod;
import javax.jws.WebParam;

@WebService(serviceName = "CurrencyConverter")
public class CurrencyConverter {

    // Assuming a static conversion rate for this example.
    private static final double INR_TO_USD_RATE = 0.012;

    /**
     * Converts an amount from Indian Rupees (INR) to US Dollars (USD).
     * @param rupees The amount in Indian Rupees.
     * @return The equivalent amount in US Dollars.
     */
    @WebMethod(operationName = "rupeesToDollar")
    public double rupeesToDollar(@WebParam(name = "rupees") double rupees) {
        if (rupees < 0) {
            return 0.0;
        }
        return rupees * INR_TO_USD_RATE;
    }
}
```
**Explanation:**
*   `@WebService`: Annotates the `CurrencyConverter` class as a web service endpoint.
*   `@WebMethod`: Exposes the `rupeesToDollar` method as a web service operation.
*   `@WebParam`: Specifies the name of the input parameter in the WSDL and SOAP message.
The method takes a `double` representing the amount in rupees, converts it to dollars using a fixed rate, and returns the result.

---
d) **How does JAX-RS help in developing RESTful web services? Give an example.**

JAX-RS (Java API for RESTful Web Services) is a Java specification that provides a set of annotations and APIs to simplify the development of RESTful web services. It allows developers to map Plain Old Java Objects (POJOs) to web resources.

**Key features:**
*   **Annotations:** Uses annotations like `@Path`, `@GET`, `@POST`, `@Produces`, and `@Consumes` to define resource URIs, HTTP methods, and content types.
*   **Standardization:** Provides a standard, portable API for building RESTful services in Java.
*   **Integration:** Integrates with various frameworks like Jersey and RESTEasy.

**Example:**
```java
import javax.ws.rs.GET;
import javax.ws.rs.Path;
import javax.ws.rs.Produces;
import javax.ws.rs.core.MediaType;

@Path("/greeting")
public class GreetingResource {

    @GET
    @Produces(MediaType.TEXT_PLAIN)
    public String getGreeting() {
        return "Hello, RESTful World!";
    }
}
```
**Explanation:**
*   `@Path("/greeting")`: Maps the `GreetingResource` class to the URI path `/greeting`.
*   `@GET`: Specifies that the `getGreeting` method will handle HTTP GET requests.
*   `@Produces(MediaType.TEXT_PLAIN)`: Indicates that the method produces a plain text response.
A GET request to `/greeting` will return the string "Hello, RESTful World!".

---
e) **Explain the pros and cons of Virtualization.**

**Pros of Virtualization:**

1.  **Hardware Cost Reduction:** Fewer physical servers are needed, which lowers hardware acquisition and maintenance costs.
2.  **Efficient Resource Utilization:** Consolidates multiple workloads onto a single physical server, increasing its utilization rate.
3.  **Rapid Provisioning:** Virtual machines can be created and deployed in minutes, accelerating application and service delivery.
4.  **Improved Disaster Recovery:** VMs can be easily replicated and migrated, enabling robust backup and disaster recovery solutions.
5.  **Isolation:** Workloads are isolated in separate VMs, enhancing security and preventing conflicts between applications.

**Cons of Virtualization:**

1.  **Performance Overhead:** The hypervisor layer introduces a slight performance penalty compared to running on bare metal.
2.  **Single Point of Failure:** If the physical host fails, all virtual machines running on it will go down unless high-availability solutions are in place.
3.  **Management Complexity:** Managing a virtualized environment requires specialized skills and tools.
4.  **Security Risks:** A compromised hypervisor could potentially expose all the VMs running on it (a concept known as "hyperjacking").
5.  **Upfront Investment:** The initial cost of virtualization software, licenses, and potentially new hardware can be significant.

---
f) **Explain the role of oVirt as a management tool in virtualization environments.**

oVirt is an open-source, centralized virtualization management platform. It is built on the KVM hypervisor and provides a powerful web-based interface for managing an entire virtualization environment.

**Key Roles and Features:**

1.  **Centralized Management:** Provides a single console to manage hosts, virtual machines, storage, and networks.
2.  **High Availability:** Automatically detects host failures and restarts VMs on other available hosts in the cluster, minimizing downtime.
3.  **Live Migration:** Allows for the migration of running VMs from one host to another without service interruption, which is essential for load balancing and maintenance.
4.  **Storage Management:** Integrates with various storage backends like NFS, iSCSI, and Fibre Channel, allowing for flexible storage allocation and management.
5.  **Scalability:** Designed to manage large-scale environments with hundreds of hosts and thousands of virtual machines.

Essentially, oVirt acts as the brain of the virtualized data center, orchestrating resources to ensure performance, availability, and efficient administration.

## Q2
a) **Describe the essential characteristics of Cloud Computing.**

According to NIST, the five essential characteristics of cloud computing are:

1.  **On-Demand Self-Service:** Consumers can unilaterally provision computing capabilities, such as server time or network storage, as needed automatically without requiring human interaction with the service provider.
2.  **Broad Network Access:** Capabilities are available over the network and accessed through standard mechanisms (e.g., web browsers, mobile apps) on various client platforms like phones, laptops, and tablets.
3.  **Resource Pooling:** The provider's resources are pooled to serve multiple consumers (multi-tenancy), with resources dynamically assigned and reassigned according to demand. The customer generally has no control or knowledge over the exact location of the provided resources.
4.  **Rapid Elasticity:** Capabilities can be elastically and rapidly provisioned, in some cases automatically, to scale out, and rapidly released to scale in. To the consumer, the available capabilities often appear to be unlimited.
5.  **Measured Service:** Cloud systems automatically control and optimize resource use by leveraging a metering capability. Resource usage is monitored, controlled, and reported, providing transparency for both the provider and the consumer.

---
b) **Discuss the fundamental aspects of cloud computing security.**

Cloud computing security is a shared responsibility between the cloud provider and the customer. The fundamental aspects include:

1.  **Identity and Access Management (IAM):** This involves controlling who can access what resources. It includes strong authentication (e.g., MFA), authorization policies, and role-based access control (RBAC) to enforce the principle of least privilege.
2.  **Data Security:** Protecting data both at rest (in storage) and in transit (over the network). This is primarily achieved through encryption. Data loss prevention (DLP) strategies are also crucial.
3.  **Infrastructure and Network Security:** Securing the underlying virtual infrastructure. This includes configuring virtual private clouds (VPCs), network security groups (firewalls), and intrusion detection/prevention systems to protect against network-based threats.
4.  **Threat and Vulnerability Management:** Continuously monitoring the cloud environment for misconfigurations, vulnerabilities, and threats. This involves regular security assessments, patch management, and threat intelligence.
5.  **Compliance and Governance:** Ensuring that the cloud deployment adheres to relevant industry regulations (e.g., GDPR, HIPAA) and corporate policies. This involves logging, auditing, and maintaining a clear governance framework.

---
c) **Write a detailed explanation of IaaS along with an appropriate diagram.**

IaaS (Infrastructure as a Service) is a cloud computing model that provides virtualized computing resources over the internet. In this model, a cloud provider hosts the fundamental infrastructure components, including servers, storage, and networking hardware, as well as the virtualization layer.

The customer is responsible for managing the operating systems, middleware, and applications, while the provider manages the physical hardware and virtualization. IaaS offers the highest level of flexibility and management control over IT resources.

**Diagram of Responsibilities:**
```
+-------------------+
|      YOU MANAGE   |
|-------------------|
|    Applications   |
|       Data        |
|      Runtime      |
|     Middleware    |
|  Operating System |
+-------------------+
| PROVIDER MANAGES  |
|-------------------|
|   Virtualization  |
|      Servers      |
|      Storage      |
|     Networking    |
+-------------------+
```

**Key Characteristics:**
*   **Pay-as-you-go:** Users pay only for the resources they consume.
*   **Scalability:** Resources can be scaled up or down easily based on demand.
*   **Automation:** Infrastructure management tasks can be automated via APIs.
*   **Control:** Users have control over their infrastructure, including the choice of OS and software stack.

**Examples:** Amazon EC2, Google Compute Engine, Microsoft Azure Virtual Machines.

---
d) **Explain open challenges of cloud computing.**

1.  **Security and Privacy:** As data is stored on remote servers, protecting it from unauthorized access, breaches, and cyberattacks remains a top concern. Ensuring data privacy and sovereignty across different legal jurisdictions is also a significant challenge.
2.  **Cost Management and Optimization:** While the pay-as-you-go model is attractive, poor resource management can lead to "cloud sprawl" and unexpected high costs. Optimizing spend without impacting performance requires constant monitoring and expertise.
3.  **Lack of Expertise and Skills Gap:** Managing a cloud environment effectively requires specialized skills in areas like cloud architecture, security, and DevOps. Many organizations struggle to find or train personnel with the necessary expertise.
4.  **Interoperability and Vendor Lock-in:** Migrating applications and data between different cloud providers can be complex and costly due to differences in APIs, services, and data formats. This can lead to vendor lock-in, where a customer is dependent on a single provider.
5.  **Compliance and Governance:** Adhering to various industry and governmental regulations (like GDPR, HIPAA, PCI DSS) in a cloud environment can be complex. Organizations must ensure their cloud provider and their own configurations meet all compliance requirements.

---
e) **Explain the requirements for secure cloud software.**

Developing secure software for the cloud requires a "shift-left" approach, where security is integrated into every phase of the development lifecycle.

1.  **Secure Design and Threat Modeling:** Before writing code, identify potential threats and design security controls to mitigate them. This includes planning for secure authentication, authorization, and data handling.
2.  **Secure Coding Practices:** Developers must follow best practices to avoid common vulnerabilities like SQL injection, cross-site scripting (XSS), and insecure direct object references. This includes input validation and output encoding.
3.  **Dependency and Vulnerability Management:** Modern applications rely on many third-party libraries. It is crucial to scan these dependencies for known vulnerabilities (using tools like SCA) and apply patches promptly.
4.  **Robust Identity and Access Management (IAM):** The software must implement strong authentication (MFA), enforce the principle of least privilege, and have a clear separation of roles and permissions.
5.  **Comprehensive Logging and Monitoring:** The application should generate detailed logs for security-relevant events (e.g., logins, access attempts, administrative changes). This enables continuous monitoring for suspicious activity and facilitates incident response.

---
f) **Write about the fundamental design principles of cloud security.**

1.  **Shared Responsibility Model:** This is the cornerstone of cloud security. The cloud provider is responsible for the security *of* the cloud (infrastructure, hardware), while the customer is responsible for security *in* the cloud (data, configuration, access). Understanding this division is critical.
2.  **Defense in Depth:** This principle involves implementing multiple layers of security controls. If one layer fails, another is in place to protect the assets. This includes a combination of network controls, IAM policies, encryption, and endpoint security.
3.  **Principle of Least Privilege:** Grant users, applications, and services only the minimum permissions they need to perform their functions. This minimizes the potential damage from a compromised account or service.
4.  **Automation:** Automate security processes wherever possible. This includes automated compliance checks, vulnerability scanning, and incident response. Automation reduces the risk of human error and allows for faster reaction to threats.
5.  **Traceability and Auditing:** Implement comprehensive logging and monitoring to track all activities within the cloud environment. This ensures that actions can be traced back to a specific identity, which is essential for auditing, forensics, and compliance.

## Q3
a) **Write about the Operations on OpenStack in detail.**

OpenStack operations revolve around managing a cloud infrastructure through its various core services. Key operations include:

1.  **Compute (Nova):**
    *   **Instance Management:** Launching (creating), stopping, pausing, rebooting, and terminating virtual machine instances.
    *   **Flavor Management:** Defining and managing VM templates (flavors) that specify vCPUs, RAM, and disk size.
    *   **Live/Cold Migration:** Moving instances between physical hosts, either while running (live) or powered off (cold).

2.  **Storage (Cinder for Block, Swift for Object):**
    *   **Volume Management (Cinder):** Creating, deleting, attaching, and detaching persistent block storage volumes to instances.
    *   **Snapshot Management (Cinder):** Creating snapshots of volumes for backup and recovery.
    *   **Object Management (Swift):** Storing and retrieving unstructured data objects (e.g., files, images) in a highly scalable and redundant manner.

3.  **Networking (Neutron):**
    *   **Network Management:** Creating and managing virtual networks, subnets, and routers.
    *   **IP Address Management:** Allocating fixed and floating IP addresses to instances.
    *   **Security Group Management:** Defining firewall rules to control traffic to and from instances.

4.  **Identity (Keystone):**
    *   **User and Project Management:** Creating and managing users, projects (tenants), and assigning users to projects.
    *   **Role Management:** Defining roles and assigning them to user-project pairs to control access rights.
    *   **Authentication:** Authenticating users and issuing tokens for accessing other OpenStack services.

5.  **Image (Glance):**
    *   **Image Management:** Uploading, storing, and managing virtual machine images (e.g., qcow2, raw) that are used to launch instances.

---
b) **Explain the concept of QUOTAS in OpenStack.**

In OpenStack, quotas are administrative limits placed on the amount of resources a project (tenant) can consume. They are a fundamental tool for cloud operators to manage resource allocation and prevent any single project from monopolizing the cloud's capacity.

**Purpose of Quotas:**
*   **Resource Control:** Prevents projects from consuming unlimited resources, ensuring fair usage and availability for all tenants.
*   **Capacity Management:** Helps cloud administrators plan and manage the overall capacity of the cloud infrastructure.
*   **Billing and Metering:** Can be used as a basis for billing, where tenants pay for a certain allocation of resources.

**Types of Quotas:**
Quotas can be set for nearly every type of resource in OpenStack, including:
*   **Compute (Nova):** Number of instances, vCPUs, RAM (in MB), key pairs, and server groups.
*   **Storage (Cinder):** Number of volumes, total size of volumes (in GB), and number of snapshots.
*   **Networking (Neutron):** Number of networks, subnets, routers, floating IPs, and security groups.

Quotas are defined per-project and can be adjusted by a cloud administrator.

---
c) **Discuss the working environment and platform used for CloudSim.**

CloudSim is a simulation toolkit that enables the modeling, simulation, and experimentation of cloud computing infrastructures and services.

**Working Environment:**

*   **Programming Language:** CloudSim is written entirely in **Java**. Therefore, the primary requirement is a **Java Development Kit (JDK)**, typically version 1.6 or higher.
*   **Development Tools:** While it can be used with a simple text editor and command-line compilation, it is most effectively used within a Java **Integrated Development Environment (IDE)** such as **Eclipse**, **IntelliJ IDEA**, or **NetBeans**. An IDE simplifies project management, coding, and debugging.
*   **Dependencies:** The core CloudSim library is self-contained and does not have external dependencies, making it easy to set up.

**Platform:**

CloudSim is a **platform-independent framework**. Because it is based on Java, it can run on any operating system that supports a Java Virtual Machine (JVM), including:
*   **Windows**
*   **Linux**
*   **macOS**

The user's code interacts with the CloudSim library to define the cloud environment (data centers, hosts), user requirements (cloudlets), and policies (VM allocation, scheduling). The simulation then runs, and the results can be collected and analyzed to evaluate the performance of different strategies or configurations.

---
d) **Describe the various features of CloudSim in detail.**

CloudSim offers a rich set of features for conducting research in cloud computing:

1.  **Modeling of Large-Scale Cloud Environments:** Supports the creation of complex cloud infrastructures, including multiple data centers, each with its own set of physical hosts.
2.  **Virtualization Engine:** Provides a detailed virtualization layer for modeling the creation and management of virtual machines (VMs) on hosts. This includes managing the execution of multiple, co-hosted VMs and simulating the overhead of virtualization.
3.  **Flexible Resource Provisioning:** Supports modeling of different policies for allocating host resources (CPU cores, memory, bandwidth) to virtual machines.
4.  **Support for Federation and Energy-Awareness:** Allows for the simulation of federated clouds (inter-cloud communication) and modeling of power consumption by data center components, enabling research into green computing.
5.  **Customizable Policies:** One of its most powerful features is the ability to easily implement and test custom policies for VM allocation, VM scheduling, and cloudlet (task) scheduling. This allows researchers to evaluate the performance of their own algorithms.
6.  **Network Simulation:** Includes a network layer for modeling communication and data transfer delays between different components of the simulated environment.

---
e) **Explain Heat Orchestration in OpenStack.**

Heat is the primary orchestration service in OpenStack. Its purpose is to automate the deployment and management of cloud applications by treating infrastructure as code. Heat allows users to define a collection of OpenStack resources and their dependencies in a text-based template.

**Key Concepts:**

1.  **Template:** A file written in **HOT (Heat Orchestration Template)** format, which is typically expressed in **YAML**. The template declaratively defines all the resources needed for an application (e.g., servers, networks, storage volumes, security groups).
2.  **Stack:** A running instance of an application created from a Heat template. A stack is the collection of OpenStack resources that Heat creates and manages as a single unit.
3.  **Resource:** Any OpenStack object that can be created and managed by Heat, such as a Nova instance, a Neutron network, or a Cinder volume.

**Workflow:**
1.  A user writes a Heat template defining the application's infrastructure.
2.  The user uploads the template to Heat and instructs it to create a stack.
3.  Heat parses the template, resolves dependencies between resources, and makes the appropriate API calls to other OpenStack services (Nova, Neutron, etc.) to create the resources in the correct order.
4.  Heat then manages the lifecycle of the stack, allowing for updates or deletion of the entire application infrastructure with a single command.

---
f) **Write a note on Architecture on AWS.**

The AWS global infrastructure is designed for high availability, scalability, and fault tolerance. It is built around two core concepts: **Regions** and **Availability Zones (AZs)**.

*   **Regions:** A Region is a distinct geographical area in the world (e.g., `us-east-1` in North Virginia, `eu-west-2` in London). Each AWS Region is designed to be completely isolated from the other Regions. This achieves the greatest possible fault tolerance and stability. When you launch resources, you choose a Region to host them in.

*   **Availability Zones (AZs):** An AZ consists of one or more discrete data centers, each with redundant power, networking, and connectivity, housed in separate facilities. AZs within a Region are interconnected with high-bandwidth, low-latency networking. By deploying applications across multiple AZs, you can protect them from the failure of a single data center. If one AZ fails, the application can failover to another AZ without interruption.

This architecture enables customers to build highly available and resilient applications. For example, a web application might have its servers running in two different AZs, with a load balancer distributing traffic between them. If one AZ goes offline, the load balancer will automatically redirect all traffic to the healthy AZ.

## Q4
a) **Write a short note on WSDL.**

WSDL, or **Web Services Description Language**, is an XML-based language used to describe the functionality of a SOAP-based web service. It serves as a contract between the service provider and the service consumer.

A WSDL file provides a machine-readable description of how the service works, including:
*   **Operations:** What functions the service provides.
*   **Data Types:** The data types of the messages to be exchanged.
*   **Message Format:** The structure of the request and response messages.
*   **Binding:** The protocol (e.g., HTTP) to be used for communication.
*   **Endpoint:** The URL where the service can be accessed.

Client applications can use WSDL files to automatically generate proxy code (stubs) for accessing the web service, simplifying the development process.

---
b) **What are the types of Cloud? Write in short about any one.**

The main deployment models for cloud computing are:

1.  **Public Cloud:** Resources are owned and operated by a third-party cloud provider and shared by multiple organizations over the internet.
2.  **Private Cloud:** The cloud infrastructure is provisioned for exclusive use by a single organization. It can be located on-premises or hosted by a third-party.
3.  **Hybrid Cloud:** A composition of two or more clouds (private or public) that remain unique entities but are bound together, offering the benefits of multiple deployment models.

**Private Cloud in detail:**
A private cloud offers an environment where the computing infrastructure is dedicated to a single organization. This provides the highest level of control and security. The organization is responsible for managing the cloud, or they can outsource it to a third party. While it offers enhanced security and control, it is typically more expensive than a public cloud due to the costs of hardware and maintenance. It is often chosen by organizations with strict security and compliance requirements, such as financial institutions and government agencies.

---
c) **Write about the DevStack in short.**

DevStack is a set of extensible scripts and tools used to quickly deploy a complete OpenStack development environment. It is not a deployment tool for production clouds but is intended for developers, operators, and enthusiasts who want to interact with the latest OpenStack releases.

**Key Purposes:**
*   **Development:** Allows OpenStack developers to quickly set up an environment to build and test their code.
*   **Prototyping:** Provides a simple way to prototype and test OpenStack features.
*   **Learning:** Acts as a sandbox for individuals who want to learn how OpenStack works.

DevStack downloads the master branch of all OpenStack projects from their Git repositories and configures them to run on a single machine (or multiple nodes). It provides a repeatable and consistent way to stand up an OpenStack cloud in minutes.

---
d) **Discuss KVM in short.**

KVM, or **Kernel-based Virtual Machine**, is an open-source virtualization technology built into the Linux kernel. It allows the kernel to function as a hypervisor.

**Key Characteristics:**
*   **Type-1 Hypervisor:** KVM transforms the Linux kernel into a "bare-metal" hypervisor.
*   **Hardware-assisted:** It requires a processor with hardware virtualization extensions, such as Intel VT-x or AMD-V.
*   **Performance:** By leveraging the underlying Linux kernel's scheduler and memory management, KVM can achieve near-native performance for virtual machines.
*   **Ecosystem:** It is the default hypervisor for many cloud platforms, including OpenStack, and is widely used in enterprise virtualization.

Instead of being a self-contained hypervisor, KVM is a kernel module that provides the core virtualization capabilities, while user-space tools like QEMU are used to emulate hardware and manage the VMs.

---
e) **List different types of cloud platforms and their purposes.**

The primary cloud service models are:

1.  **IaaS (Infrastructure as a Service):**
    *   **Purpose:** To provide fundamental computing infrastructure (virtual machines, storage, networking) on demand. It offers the most flexibility for users to build their own custom environments.
    *   **Example:** Amazon EC2, Google Compute Engine.

2.  **PaaS (Platform as a Service):**
    *   **Purpose:** To provide a platform where developers can build, deploy, and manage applications without worrying about the underlying infrastructure. It includes the OS, runtime, and middleware.
    *   **Example:** Heroku, Google App Engine.

3.  **SaaS (Software as a Service):**
    *   **Purpose:** To deliver ready-to-use software applications over the internet on a subscription basis. The provider manages the entire stack, from hardware to the application itself.
    *   **Example:** Salesforce, Google Workspace, Microsoft 365.

4.  **FaaS (Function as a Service) / Serverless:**
    *   **Purpose:** To allow developers to run code in response to events without managing any servers. The platform automatically handles the provisioning and scaling of resources.
    *   **Example:** AWS Lambda, Google Cloud Functions.

---
f) **Write a brief overview of Nova in OpenStack.**

Nova is the **compute service** of OpenStack and one of its most fundamental components. Its primary role is to manage the lifecycle of virtual machines (instances) within an OpenStack cloud.

**Key Responsibilities:**
*   **Instance Lifecycle Management:** Handles creating (spawning), running, stopping, and terminating virtual machines.
*   **Scheduling:** The Nova scheduler determines which physical host (hypervisor node) a new instance should be launched on, based on resource availability and scheduling rules.
*   **API:** Provides a RESTful API for users and other OpenStack services to manage compute resources.
*   **Integration:** Works closely with other OpenStack services: it gets images from **Glance**, network connectivity from **Neutron**, and authentication from **Keystone**.

Nova itself does not include virtualization capabilities; instead, it uses hypervisors like KVM, VMware, or Hyper-V to run the virtual machines. It acts as the orchestration engine for compute resources in the cloud.
