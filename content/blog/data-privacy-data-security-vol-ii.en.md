+++
lang="en-GB"
title="Data Privacy, Data Security, Vol. II"
date="2021-11-08"
author="Eugen Wypiór"
image="/blog/Data-Privacy-Security-NP-vol2-1.png"
tags=['ABC security','IT security', 'response&recovery']
+++

Data security is all the things you do and solutions you implement to
protect digital information from unauthorised access, corruption, or
theft throughout its entire lifecycle. I am sure the reader is well
aware of the various basic data protection tools available starting with
backing up the data, through secure passwords, 2FA, patching, before
moving on to the more sophisticated level of infrastructure hardening,
network segmentation, and the implementation of Zero Trust Architecture
and the Principle of Least Privilege and raising staff awareness. Why
the latter three? According to a study conducted in 2014 by IBM 95% of
all security incidents involved human error. In some cases, these
incidents are a result of deliberate malicious actions by the company's
employees. Some are caused unintentionally by insiders, such as in the
case of network administrators who configure wrongly the system they
oversee, poor patch management practices, or the use of default names
and passwords. Attackers also exploit the inherent human-interest
factor. In this case, curiosity wasn't the cat's doing but the human's
-- many attacks involve social engineering techniques to lure
individually targeted users into making mistakes. It is the belief of
many that for an enterprise to be successful it needs to focus on
people, processes, and technology in equal measure. If we were to
transfer it onto the plane of business' digital security technology can
provide automated safeguards and processes to aim at keeping the
infrastructure safe from intrusion and corruption. But even enterprises
with strong security practices are still vulnerable to human error.
That's why technology and processes must be accompanied in equal measure
by employees' ongoing digital security education to develop a culture of
digital security as an inherent part of the company's ecosystem. Digital
security must become a state of mind.

## DevSecOps - application development with security in mind{ .article-section }

DevOps emerged some years back in a technological environment different
to the one we live in nowadays when the necessity to keep things secure
in the digital domain becomes more and more pertinent. And just as
privacy shouldn't be an afterthought in the software and application
developing process, as discussed in last week's post, the same principle
applies to security and its role in application development. To stay one
step ahead of rogue actors it is time to upgrade the
application-development process from DevOps to DevSecOps.

#### So, what process must the traditional DevOps undergo to transform into the desired DevSecOps fit for the times we live in?

In a standard DevOps flow, the process is streamlined and fast.\
Developers release the code, and the application delivery pipeline
starts.\
Changes are tested with automated tests, a new version is built and
deployed to the test environment where more automated tests are run and
when everything works fine the new version can be released.\
This fast and optimised flow makes the application delivery fast with no
manual effort from developers or testers. And the new version of the
application is ready to be released into production. But not really. It
needs to be vetted for security. Especially if the application is a
banking app, social media app, or an e-commerce solution. One must make
sure there are no security holes in the application as it can be
detrimental to the business if the app gets hacked leaking private
customer data in the production environment.\
To ensure the application is safe for production the security team must
test the new version for any vulnerabilities and other security issues.
Depending on the complexity of the app this can take days or even weeks.
If the security team finds vulnerabilities or other security issues, it
will have to send the code to developers to fix the issues.\
However, as the DevOps cycle is an efficient one, several newer versions
might be created, and they will be all waiting in the queue for the
security audit.\
In this way, the security audit becomes a bottleneck in the otherwise
very efficient DevOps process.

#### Why can the security audit take so long?

The reason lies in the constant evolution of the applications over time
prompted by their quickly changing ecosystem. Microservices replaced the
monolithic application which exposes API to communicate. This creates
more attack surface. On top of that, there are other services that
microservices use such as databases, message brokers, and others. That
increases the attack surface. These can be run in containers that might
be located on a cloud platform which extends the attack surface even
further. Like this, there are many layers of infrastructure,
applications, and other components which need securing.\
Instead of thinking about security after a new feature is developed and
tested right before releasing it, security should be thought about right
at the beginning and solved right away when security issues arise.

#### How to fuse security in the DevOps process instead of it being a separate add-on step at the end of the development process?

Firstly, security must become the developer's responsibility too instead
of being the responsibility of dedicated professionals only.\
In this way, the security team becomes an adviser to the developers and
operations teams helping them understand and manage security rather than
being an added component at the end of the process hindering the speed
of the delivery process.

#### How can DevSecOps look in practice?

The security team develops security policies.\
It selects the appropriate automation tools and platforms for detecting
and identifying any security issues and vulnerabilities such as security
scans, code quality checks, automated security tests of the app.\
The security team then trains the developers and operations teams on how
to interpret the output of these tools so that they can identify and fix
the issues themselves.\
In this way, all the security tools and platforms are integrated into
the CI/CD pipeline and on every push to a feature branch or master
branch these tools run, and developers get automated output on their
application security status letting them know what issues and
vulnerabilities need to be fixed. If there are no issues the pipeline
will deploy and release the application.\
Like this, the manual work of the security professionals will be
automated and integrated into the application delivery pipeline making
the release process much faster. It will allow for a faster release of
the application and prevent the security issues from sliding into
production which can happen when the security is a component added at
the end of the development process.

## Do you require help with Secure Product Development or Security Review of your Code?{ .article-section }

SEQRED offers assistance in creating a secure product from scratch and
monitoring its entire production cycle: from the initial design stage,
through creation and testing, to a final audit completed with an
incident response plan.

SEQRED can also carry out comprehensive
security code reviews using modern static and dynamic analysis methods
to detect potential problems with the security of server software, web
applications, and embedded systems
firmware.

###### **About this guide**

The idea for this article was inspired mainly by a presentation by TechWorld with Nana which you canwatch [here.](https://www.youtube.com/watch?v=nrhxNNH5lt0)