# openshift-deployment
End to end walkthrough of deploying and using Reloader and Mosquitto in OpenShift


If you're reading this it's likely that you are just getting started with the Operate First team or you're getting started with Site Reliability Engineering concepts. A little about myself: as of writing this (Dec 2021), I have been with Red Hat for about 8 months where I started as an intern working on a Massachusetts Open Cloud security project. As of October 2021, I am a full time Site Reliability Engineer (SRE) working with the Operate First team. This means I work a lot with OpenShift, and in this walk-through I will take you through my first complete project deployment.  

What exactly is an SRE? Well it's a rather broad title but here is the definition of site reliability engineering from the Operate First website:
"SRE is a software engineering approach to manage operations for systems, applications and services. We use software as a tool to manage systems, solve problems, and automate operations tasks."
In the context of Operate First we deploy, manage and improve applications and resources in OpenShift cloud environments.

And what exactly is Operate First? I'll once again refer to a quote from the Operate First website: "Operate First is a concept where open source developers bring their projects to a production cloud during development where they can interact with a cloud provider’s operators and gain valuable feedback on the operational considerations of their project." 

For more info check out: [Operate First](https://next.redhat.com/project/operate-first/)

To see more of what it's like to be an a part of the Operate First/SRE team you should join the Operate First Slack: [OperateFirst slack](https://join.slack.com/t/operatefirst/shared_invite/zt-o2gn4wn8-O39g7sthTAuPCvaCNRnLww)
Additionally, check out the repositories here: [Operate First Github Repo](https://github.com/operate-first/), more specifically you can look at issues in the apps repo for instance: [apps repo issues](https://github.com/operate-first/apps/issues)

If you’re anything like me, the best way to actually learn this stuff is by jumping in headfirst and working with it. I’ll run you step by step through my own first successful complete deployment to the operate-first team. For this example we’ll be using Reloader as our case study.

Here is the link to the Reloader Github repository: [Reloader](https://github.com/stakater/Reloader)

First of all, what is Reloader and why is it useful to us? Reloader essentially allows us to monitor for when changes are made to configMap and secret manifests within our cluster. When changes are detected the Reloader Pod will trigger affected pods to be redeployed on a rolling basis. Makes sense right? If you're anything like me when I got started, the previous 2 sentences sound dreadfully confusing. For right now what Reloader does and all of the specifics are not super important, and first we need to set some things up so we can actually use it. As we set up we will cover all the necessary terminology and concepts we need to flesh all this out.

In the following sections I'm going to run through setting up an OpenShift cluster, deploying applications in said cluster, and everything that goes along with it. 

The final versions of each of the manifests we'll be using are in the manifests file and you'll find the walkthrough broken up into isses in the issues tab of the repository. Start with issue #1 and work your way up. 

If you have any questions or issues throughout you can contact me at dystewar@redhat.com. 

I hope this guide will help you get started on your journey with OpenShift and Operate First!

-Dylan
