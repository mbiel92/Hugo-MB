+++
lang="en-GB"
title="Cloud computing security - identity and access management comparison for GCP and AWS"
date="2020-05-10"
author="Michał Kwiatkowski"
image="/blog/seqred-bezpieczenstwo-w-chmurze-zarzadzanie-tozsamoscia.jpg"
+++

Cloud computing is the foundation of many digital transformation
projects. Currently, enterprises see progressively more value in the
ability to scale the cloud environment, being able to transfer part of
the responsibility for reliability onto a cloud service provider as well
as the accessibility of data for employees working remotely. However,
the ease of access to data creates the need for rigorous identity
management: specifying exactly who, in what situation and to what level
can access the data stored in the cloud.

**Each leading provider of IaaS cloud computing solutions: Google (GCP),
Amazon (AWS) and Microsoft (Azure) assists in this process by granting
access to Identity and Access Management tools.** In spite of fairly
similar scopes of functionality, the companies' approaches to the design
and defining policy of permissions and security, as well as user
management and even the meaning of the same vocabulary can vary
depending on the service provider.

**In this article, you will find out about:**\
**[1.]** identity management in IAM systems,\
**[2.]** different approaches to the structures
used for access management within an organisation,\
**[3.]** the differences between IaaS providers.

![](/blog/seqred-bezpieczenstwo-w-chmurze-zarzadzanie-tozsamoscia.jpg)

## Identity management in IAM systems

Generally speaking, **IAM systems** are used to define and manage
access. Online user identity management as well as a system of access
control for IT infrastructure components are the most important elements
of this system, allowing for them to grant the correct access level to
the right infrastructure and under specific circumstances for individual
persons.

## User identification in the cloud

Every leading cloud computing services provider approaches the topic of
user identification in their infrastructure differently.

### GCP: the use of products offered by Google

For user identification, GCP uses other products offered by Google in.
For example, we can gain access to the infrastructure through a Google
account or an account from a G Suite domain. Google Cloud Identity can
also be used for user management in a way resembling G Suite, but
without access to office suite. Thanks to the separation of identity
verification from IaaS, the user can access infrastructure belonging to
different organisations through one account.

### Fedareted identity management

Both providers, Amazon and Google allow for extension of mechanisms'
abilities through the incorporation of federated identity management
based on SAML 2.0.

If properly set up, this functionality allows for the use of external
services such as Microsoft Active Directory or an external provider such
as Facebook, in which case AWS and GCP authentication processes are
conducted based on user accounts from outside solutions and credentials
is not stored using cloud services. This solution allows for the use of
the same credentials for all configured services despite them being
sourced from different organisations or different IaaS providers.

Additionally, this solution is often used alongside SSO (single sign-on)
mechanisms, particularly for companies using IaaS services delivered by
a number of providers, and is designed to help the user in navigating
between them.

Adequate identity management in the cloud is the foundation of security
and access management. Another crucial part of the process is **defining
different permission levels for each user,** in which case IAM tools
used can be quite different from one another.

## Access management structures

Access management is usually implemented in order to allow users to
perform operations needed for their assigned duties and limit user
access level to areas necessary for each user.

### The simplicity of AWS solutions

In the process of designing AWS structures, Amazon prioritised
simplicity and granularity. In order to configure access policy, it is
necessary first to specify the actions (mapped directly to API and AWS
methods) and objects the policy applies to.

Each resource is given a unique ARN (Amazon Resource Name) ID when it is
created.

For example:\
arn:aws:cloudwatch:us-west-2:123456789012:alarm:suspiciousActivity\
arn:aws:iam::123456789012:server-certificate/division_abc/subdivision_xyz/ProdServerCert

During policy access configuration we target an object using its ARN.
Due to the fact that each, even very specific objects, can be treated as
resources, this solution allows for granting access with great accuracy,
e.g. even to a single alarm in an AWS Cloud Watch or a Topic in SNS.

We can further specify access using wildcard characters.

The majority of ARN contain a path to a resource. Using an asterisk we
can end the path on any chosen level, to refer to each object contained
in a resource before the wildcard. For example, by granting a service
access to arn:aws:iam::123456789012:user/\*, we are giving it access to
all user accounts.

Moreover, AWS can be used to create user accounts which do not have
administrative access to infrastructure and are only granted access to
API and CLI tools.

### Access control hierarchy in GCP

Google has created a more complex access management solution based on
resource hierarchy. In this solution, the Project is the foundation for
creating an operational structure. All resources used in a Project have
a basic level of access set by default. Thanks to this solution, e.g.
App Engines are automatically granted access to all storage buckets
created within a Project.

On account of the use of resource hierarchy, access can be granted not
only to individual resources or users, but also to more general
containers.

These containers can be:

-   The previously mentioned Projects, containing resources related to a
    specific venture,
-   Folders, which can store Projects as well as other Folders used to
    group resources,
-   Organisations -- the top of a resource hierarchy, containing all
    other objects.

**How are permissions inherited in this structure?**\
For example by granting developer access on a Folder to specific a user,
we are giving the user a similar role and the level of access that comes
along with it for all Projects stored in that Folder and all resources
contained within the Projects (as shown on the diagram below):

![](/blog/obraz-chmura.png)

Source: [GCP Doccumentation](https://cloud.google.com/resource-manager/docs/cloud-platform-resource-hierarchy)
license: [Creative Commons 4.0](https://creativecommons.org/licenses/by/4.0/)

Although the structure of access in AWS might seem more intuitive, often
subsequently to configuration, particularly of larger environments, we
can encounter policies with permissions of wider reach than what is
usually recommended, in order to facilitate management and speed up
configuration. In these instances we can often encounter general
definitions being applied to all of a certain type of resources
(arn:aws:s3:::\*) instead of specified resources.

On the other hand, in some instances GCP can lack the level of detail in
defining access permissions, in which cases we have to circumvent the
issue with more general permissions related to projects.

## Different functions under the same name

In addition to different approaches to access management, when comparing
GCP and AWS we have to overcome the issue of discrepancies in
terminology used in the two solutions. Functions and objects under the
same name work differently in GCP and AWS and often apply in different
circumstances.

The most noticeable discrepancies exist in terminology related to Policy
and Roles.

### Policy in GCP and AWS

**In AWS the Policy is a collection of individual permissions.** We use
it to group permissions granting access to a specific functionality. For
example, one of the policies delivered and managed by Amazon
"AmazonEC2ReadOnlyAccess" contain permissions to read status and
configuration of services:

-   EC2
-   EC2 Auto Scaling

as well as to read correlated services configurations e.g. EC2

Policies defined in this way can be attached to Roles, user groups or
directly to a user or resource to determine their permissions. The
closest equivalent to this solution in GCP is a Role.

**Policy in Google cloud services describes the access to a specific
resource** (e.g. Project or Folder). Policy includes principles
allocating Roles to specific users (so-called bindings). With a Policy
attached to a Project, we can automatically check whether a user trying
to access the data has a Role with a required access level.
Additionally, Policy allows to add additional requirements the user has
to meet to gain access (e.g. a specific timeframe to complete a task).

### Role in GCP and AWS

The previously mentioned Role in GCP in many ways corresponds to Policy
in AWS. It is a collection of individual permissions granting access to
specific functionalities.

In AWS, a Role is a different solution- In a way, it can be seen as a
user without a specified identity attached. The Role is not attributed
to a specific person, and access to it is configured similarly to a
regular user. Other users and resources can be granted temporary access
to it in order to perform operations using the Role's permissions. The
solution is used mainly in identity federation, but also when apps need
to download data or make changes in AWS structures.

The list of discrepancies between the two solutions could be much
longer, in order to analyse them in more detail we recommend looking
into GCP documentation comparing similarly named functionalities
presented below:

| Concept | AWS |Google Cloud |
|---------|-----|-------------|
| Programmatic identity | [IAM role](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_use_switch-role-ec2.html) and instance profile | [Cloud IAM service account](https://cloud.google.com/iam/docs/service-accounts#what_are_service_accounts) |
| User identity | Managed in IAM. Identity federated to external identitymanagement system | Managed outside Cloud IAM. Identity federated to external identity management system |
| Policy | A document that explicitly lists permissions | A list of bindings. A binding binds a list of members to a role |
| Policy attachment | Policy attached to an IAM user or group or a resource | Policy attached to resource |
| Policy evaluation | Deny by default | Deny by default |
| Permission collection | Policy | Role |
| Predefined set of permissions | Managed policies | Predefined roles |
| Auditing IAM calls | AWS CloudTrail | Audit logging |
| Versioning | Yes | No |

Source: [GCP Documentation](https://cloud.google.com/docs/compare/aws/management) 
license: Creative Commons 4.0

### Conclusion

With the growing popularity of cloud computing services, there is a
growing number of organisations using the services of more than one
provider. In multi cloud environments functionalities such as identity
federation as well as an in-depth knowledge of features specific to
particular solutions created by providers is incredibly valuable.

Although they were designed in a completely different way, IAM systems
in both GCP and AWS serve a similar purpose. Despite many differences
between the tools, the number of similar functionalities in GCP and AWS
has grown with their development over the years. Currently, both
solutions allow for the implementation of similar security policies,
even though they do so using different methods. Due to this, the choice
between the providers is often determined by different aspects of their
services.

**Sources:**

-   [Google Cloud Platform documentation for AWS
    Professionals](https://cloud.google.com/docs/compare)
-   [AWS
    documentation](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html)
-   [GCP documentation](https://cloud.google.com/iam/docs)