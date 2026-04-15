# Cloud Computing & Web Services - April 2024 Answers

## Q1

**a) Explain the structure of SOAP message.**

A SOAP message is an XML document consisting of the following elements:
- **Envelope:** The root element that encapsulates the entire SOAP message. It defines the XML document as a SOAP message.
- **Header:** An optional element that contains application-specific information (metadata) about the SOAP message, such as authentication, payment, or routing information. If the Header element is present, it must be the first child element of the Envelope element.
- **Body:** A mandatory element that contains the actual message content intended for the recipient. This could be a request to a web service or the response from it. The Body element must be a direct child of the Envelope element.
- **Fault:** An optional element within the Body that is used for reporting errors. If a Fault element is present, it must appear as a child element of the Body element.

**b) Write a web service method that accepts two numbers as parameters and returns the largest of those numbers using JAX-WS. (Write only the Webservice method block)**

```java
import javax.jws.WebService;
import javax.jws.WebMethod;
import javax.jws.WebParam;

@WebService
public class NumberService {

    @WebMethod
    public int getLargest(@WebParam(name = "num1") int num1, @WebParam(name = "num2") int num2) {
        return Math.max(num1, num2);
    }
}
```

**c) Differentiate between Parallel Computing and Distributed Computing.**

| Feature | Parallel Computing | Distributed Computing |
| :--- | :--- | :--- |
| **Memory** | Multiple processors share the same memory (tightly coupled). | Each processor has its own private memory (loosely coupled). |
| **Communication** | Processors communicate with each other via the shared memory. | Processors communicate with each other via message passing over a network. |
| **Synchronization** | A single clock usually provides synchronization. | There is no global clock; synchronization is more complex. |
| **Goal** | To increase performance by running a single task faster. | To share resources and improve reliability and scalability. |
| **Example** | A multi-core processor running a computationally intensive simulation. | A network of computers working together on a large-scale data processing task. |

**d) List and explain the various HTTP methods required for creating RESTful Web Services.**

- **GET:** Retrieves a representation of a resource. It is a safe and idempotent method, meaning multiple identical requests will have the same effect as a single request and it does not alter the state of the resource.
- **POST:** Creates a new resource. It is not safe or idempotent. Submitting the same POST request multiple times will likely result in the creation of multiple new resources.
- **PUT:** Updates an existing resource or creates it if it does not exist. It is idempotent; multiple identical PUT requests will have the same effect as a single one.
- **DELETE:** Deletes a resource. It is idempotent; multiple DELETE requests for the same resource will result in the resource being deleted, and subsequent requests will likely return a "Not Found" status, but the state of the system remains consistent.
- **PATCH:** Applies partial modifications to a resource. It is not idempotent.

**e) Explain the different characteristics of a Virtualized environment.**

- **Isolation:** Virtual machines are isolated from each other and from the host machine. A failure or security breach in one VM does not affect others.
- **Encapsulation:** The entire state of a virtual machine can be saved to a file, making it easy to move, copy, and restore.
- **Hardware Independence:** Virtual machines are independent of the underlying physical hardware, allowing them to be migrated between different physical servers (portability).
- **Partitioning:** A single physical machine can be partitioned into multiple independent virtual machines, each running its own operating system and applications.
- **Resource Sharing:** Physical resources of the host machine (CPU, memory, storage, network) are shared among the virtual machines.

**f) Explain virtualization using KVM.**

KVM (Kernel-based Virtual Machine) is a full virtualization solution for Linux on x86 hardware containing virtualization extensions (Intel VT or AMD-V). It consists of a loadable kernel module, `kvm.ko`, that provides the core virtualization infrastructure and a processor specific module, `kvm-intel.ko` or `kvm-amd.ko`.

Using KVM, one can run multiple virtual machines running unmodified Linux or Windows images. Each virtual machine has private virtualized hardware: a network card, disk, graphics adapter, etc. KVM is part of mainline Linux and is therefore very stable and well-supported. It leverages the Linux kernel for many of its functions, such as the process scheduler, memory management, and device drivers.

## Q2

**a) Explain the advantages of Cloud Computing.**

- **Cost Savings:** Reduces capital expenditure on hardware and software. You pay for what you use (pay-as-you-go).
- **Scalability and Elasticity:** Easily scale resources up or down based on demand.
- **Flexibility and Accessibility:** Access your data and applications from anywhere with an internet connection.
- **High Availability and Reliability:** Cloud providers offer robust infrastructure with built-in redundancy, ensuring your services are always available.
- **Disaster Recovery:** Cloud services provide robust backup and disaster recovery solutions, making it easier and cheaper to recover from a disaster.

**b) Describe the Cloud Computing Reference Model in detail.**

The Cloud Computing Reference Model is a layered architecture that defines the different types of services offered by cloud computing. The three main layers are:

- **Infrastructure as a Service (IaaS):** This is the base layer and provides fundamental computing resources such as virtual machines, storage, and networking. The user has control over the operating systems, storage, and deployed applications. Examples: Amazon Web Services (AWS) EC2, Google Compute Engine (GCE).
- **Platform as a Service (PaaS):** This layer provides a platform for developers to build, deploy, and manage applications without worrying about the underlying infrastructure. It includes tools and services like operating systems, databases, and web servers. Examples: Heroku, Google App Engine.
- **Software as a Service (SaaS):** This is the top layer and provides ready-to-use software applications over the internet. Users access the software via a web browser or an API. The provider manages the infrastructure, platform, and application. Examples: Google Workspace, Salesforce, Microsoft Office 365.

**c) Explain open challenges of Cloud Computing.**

- **Security and Privacy:** Ensuring data is secure and private is a major concern. Multi-tenancy and data breaches are significant risks.
- **Interoperability and Portability:** Lack of standardization makes it difficult to move applications and data between different cloud providers.
- **Performance and Reliability:** Performance can be unpredictable, and outages can have a significant impact on business operations.
- **Cost Management:** While cloud can be cost-effective, it can be challenging to manage and control costs, especially with complex pricing models.
- **Compliance and Legal Issues:** Adhering to various legal and regulatory requirements (like GDPR, HIPAA) can be complex in a cloud environment.

**d) Write about various Security Services of Cloud.**

- **Identity and Access Management (IAM):** Controls who can access your cloud resources and what they can do with them. It includes services for authentication and authorization.
- **Data Encryption:** Encrypts data at rest (stored data) and in transit (data moving over the network) to protect it from unauthorized access.
- **Network Security:** Includes services like firewalls, virtual private clouds (VPCs), and intrusion detection/prevention systems to protect the network.
- **Security Auditing and Monitoring:** Provides tools to log, monitor, and audit activity in your cloud environment to detect and respond to security threats.
- **Compliance:** Cloud providers offer services and tools to help customers meet various industry and government compliance standards.

**e) Explain the cloud security design principles.**

- **Shared Responsibility Model:** Security is a shared responsibility between the cloud provider and the customer. The provider is responsible for the security *of* the cloud, and the customer is responsible for security *in* the cloud.
- **Defense in Depth:** Implementing multiple layers of security controls to protect against a variety of threats.
- **Principle of Least Privilege:** Granting users and applications the minimum level of access required to perform their functions.
- **Secure by Design:** Building security into all layers of the cloud architecture from the ground up.
- **Automation:** Using automation to configure, monitor, and manage security controls to reduce human error and improve efficiency.

**f) Explain Cloud Security Policy Implementation.**

Implementing a cloud security policy involves several steps:
1.  **Define Security Goals and Requirements:** Identify the security objectives and the specific compliance requirements that need to be met.
2.  **Develop Security Policies:** Create a set of clear and comprehensive security policies that address all aspects of cloud security, including data protection, access control, and incident response.
3.  **Implement Security Controls:** Deploy and configure the necessary security controls, such as IAM, encryption, and network security measures.
4.  **Monitor and Audit:** Continuously monitor the cloud environment for security threats and vulnerabilities, and conduct regular security audits to ensure compliance with the security policies.
5.  **Incident Response:** Establish a clear plan for responding to security incidents, including steps for containment, investigation, and remediation.

## Q3

**a) Explain CloudSim architecture in detail. Also draw the necessary diagram for the same.**

CloudSim is a toolkit for modeling and simulating cloud computing environments. Its architecture is layered and consists of the following main components:

- **CloudSim Core Simulation Engine:** Provides the core functionalities for creating simulations, managing events, and communication between simulation entities.
- **Cloudlet:** Models the applications and their tasks. It contains information about the task, such as its length (in million instructions), file size, and output size.
- **Virtual Machine (VM):** Models a virtual machine. It has properties like MIPS (Million Instructions Per Second), memory, storage, and a scheduling policy for cloudlets.
- **Datacenter:** Models a datacenter. It consists of one or more hosts. It is responsible for managing the hosts and processing events.
- **Host:** Models a physical machine. It has properties like processing cores, memory, and storage. It is responsible for managing the VMs.
- **DatacenterBroker:** Represents a user or a broker that submits cloudlets to the datacenter for execution. It is responsible for creating VMs and submitting cloudlets to them.

![CloudSim Architecture](https://www.researchgate.net/profile/Rajiv-Ranjan-3/publication/224213038/figure/fig1/AS:393666068299778@1470868686646/The-layered-CloudSim-architecture.png)

**b) Explain different features of CloudSim.**

- **Support for large-scale cloud environments:** Can simulate large and complex cloud environments with thousands of machines.
- **Flexible and extensible:** Can be extended to model different types of cloud resources and policies.
- **Support for modeling and simulation of virtualized environments:** Can model virtual machines and their management.
- **Support for modeling federated clouds:** Can simulate scenarios with multiple collaborating datacenters.
- **No need for real hardware:** Allows for repeatable and controlled experiments without the need for physical infrastructure.

**c) Write about the working platform for CloudSim.**

CloudSim is a Java-based simulation library. Therefore, to use CloudSim, you need to have a Java Development Kit (JDK) installed on your system. It can be used on any platform that supports Java, including Windows, macOS, and Linux.

To create a CloudSim simulation, you write a Java program that uses the CloudSim library. The program defines the cloud environment (datacenters, hosts, VMs), the applications (cloudlets), and the policies (VM allocation, cloudlet scheduling). The CloudSim engine then runs the simulation and provides the results.

**d) Explain the key components of OpenStack.**

OpenStack is an open-source cloud computing platform. Its key components include:
- **Nova:** The primary compute engine of OpenStack. It is used to provision and manage large numbers of virtual machines.
- **Neutron:** Provides networking services for OpenStack. It allows users to create and manage virtual networks, subnets, routers, and load balancers.
- **Swift:** A scalable, redundant storage system. Objects and files are written to multiple disk drives spread throughout servers in the data center.
- **Cinder:** Provides persistent block storage to guest VMs.
- **Keystone:** Provides identity services for OpenStack. It is a central directory of users, mapped to the OpenStack services they can access.
- **Glance:** Provides image services for OpenStack. It is used to discover, register, and retrieve virtual machine images.

**e) What is DevStack? Explain the installation steps.**

DevStack is a series of extensible scripts used to quickly bring up a complete OpenStack environment for development purposes.

Installation Steps:
1.  **Download DevStack:** Clone the DevStack git repository: `git clone https://opendev.org/openstack/devstack`
2.  **Create a `local.conf` file:** This file is used to configure DevStack. At a minimum, it should contain the passwords for the various OpenStack services.
3.  **Run the installation script:** Navigate to the devstack directory and run `./stack.sh`. This script will download and install all the necessary OpenStack components.
4.  **Access the OpenStack dashboard:** Once the script finishes, you can access the OpenStack dashboard (Horizon) in your web browser.

**f) Explain Components and services of AWS.**

AWS (Amazon Web Services) is a comprehensive and broadly adopted cloud platform. Some of its core components and services are:
- **Compute:**
    - **EC2 (Elastic Compute Cloud):** Provides resizable compute capacity in the cloud (virtual machines).
- **Storage:**
    - **S3 (Simple Storage Service):** Scalable object storage for data backup, archiving, and analytics.
    - **EBS (Elastic Block Store):** Persistent block storage volumes for use with EC2 instances.
- **Networking:**
    - **VPC (Virtual Private Cloud):** A logically isolated section of the AWS Cloud where you can launch AWS resources in a virtual network that you define.
- **Database:**
    - **RDS (Relational Database Service):** A managed relational database service that makes it easy to set up, operate, and scale a relational database in the cloud.
    - **DynamoDB:** A fast and flexible NoSQL database service.
- **Management Tools:**
    - **CloudWatch:** A monitoring and observability service.
    - **IAM (Identity and Access Management):** Manages user access to AWS services and resources.

## Q4

**a) Write in short about JAX-WS.**

JAX-WS (Java API for XML Web Services) is a Java programming language API for creating web services, particularly SOAP-based ones. It is part of the Java EE platform. JAX-WS allows developers to write message-oriented as well as RPC-oriented web services. It simplifies the development of web services by providing a set of annotations that can be used to turn a regular Java class into a web service.

**b) What are the types of Cloud? Write in short about any one.**

There are three main types of cloud deployment models:
- **Public Cloud:** The cloud infrastructure is owned and operated by a third-party cloud provider and is available to the general public.
- **Private Cloud:** The cloud infrastructure is operated solely for a single organization. It can be managed internally or by a third party and can be hosted on-premise or off-premise.
- **Hybrid Cloud:** A combination of public and private clouds, bound together by technology that allows data and applications to be shared between them.

**Private Cloud:** A private cloud offers the benefits of cloud computing, such as scalability and self-service, but with greater control and security. It is a good option for organizations that have strict security and compliance requirements or that need to have more control over their data and infrastructure.

**c) Write short note on GridSim.**

GridSim is a Java-based toolkit for modeling and simulating Grid computing environments. It allows for the simulation of different Grid resources, users, applications, and scheduling policies. GridSim provides a comprehensive facility for the simulation of different models of parallel and distributed computing systems such as single-site, multi-site, and federated Grids. It has been used for research in areas such as resource management, scheduling, and application performance evaluation.

**d) Describe oVirt in short.**

oVirt is an open-source virtualization management platform. It was founded by Red Hat as a community project on which Red Hat Virtualization is based. It allows you to manage virtual machines, storage, and virtual networks. oVirt is a feature-rich, enterprise-grade virtualization platform that provides a web-based management interface for centrally managing your virtual environment. It uses KVM as its hypervisor.

**e) What are the security best practices for AWS.**

- **Use IAM to control access:** Follow the principle of least privilege and grant users and applications only the permissions they need.
- **Enable MFA (Multi-Factor Authentication):** Add an extra layer of security to your AWS account.
- **Encrypt data at rest and in transit:** Use services like KMS (Key Management Service) to manage encryption keys.
- **Use VPCs to isolate your resources:** Create isolated virtual networks to protect your resources from unauthorized access.
- **Monitor and log activity:** Use CloudTrail and CloudWatch to monitor activity in your AWS account and detect security threats.

**f) What is an OpenStack.**

OpenStack is a free and open-source software platform for cloud computing, mostly deployed as an infrastructure-as-a-service (IaaS). The software platform consists of interrelated components that control diverse, multi-vendor hardware pools of processing, storage, and networking resources throughout a data center. Users either manage it through a web-based dashboard, through command-line tools, or through a RESTful API. OpenStack is managed by the OpenStack Foundation, a non-profit corporate entity established in September 2012 to promote OpenStack software and its community.
