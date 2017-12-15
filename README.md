# Abstract

Reproducibility of data is crucial to science. Ease of reproducibility has numerous advantages and there are two very useful tools to aid with this. Galaxy is a workflow manager that ties together and manages the tools and scripts you use to process and analyse data. Docker is a powerful tool that you can use to encapsulate and isolate the runtime environments of your tools from the varied system environments they may face. With the ever growing scale of the datasets being processed, utilising large scale cloud computing is an economical option to generate results faster. Here we will discuss the various features of these tools and how to integrate them together on Amazon Cloud computing systems. We will also demonstrate how to integrate any tool or script that is not already available through Galaxy.

# Preamble

Reproducibility is a core tenet of science. If others are not able to reproduce your findings then it invalidates any conclusions you may have made. This holds true in computational biology where the transformation of raw data into something analysable can be difficult to reproduce. A wide variation in computing environments and runtime parameters needs to be documented or constrained to ensure that any of these factors can be reproduced when transforming the data. To add to the complexity of this task, biological data is relatively large and requires a significant amount of computing power to process the data in a reasonable amount of time. Luckily there are numerous services available that allow you to rent large clusters of computers and set them to your own tasks. The systems that make up these clusters can significantly vary and steps need to be taken to insulate your work from them. 
Utilising tools that make reproducibility easier does more than bolster the credibility of your work, it also makes it easier for others to utilise your work for their own purposes. The next person that want to use your work will also most likely be your future self. If after you have finalised publication and set the work aside forgetting about it, coming back to it later with a new purpose will be significantly easier if you take steps now to ensure ease of reproducibility. Even your current self will be rewarded by the extra effort taken. If erroneous results come up after a significant amount of time and effort was spent, then it will be much easier to iterate on the data while troubleshooting. 
If you have any experience in the data sciences then you will know the tribulations of trying to install and configure all the necessary tools to process data. This is especially true when trying to follow a publication’s vague description of how they generated their results. Wouldn’t it have been nice if the authors had published their entire computing environment? With all the software nicely compiled and all the configuration options already set up? This is entirely possible with a couple pieces of software that we will now discuss.

# Workflow Managers

Let's begin with the idea of a workflow. A workflow is a series of tools and dataset actions that run in sequence to transform data into a useful form. It usually involves data conversion, filtration, transformation, aggregation, segmentation, processing, and visualisation. They can include a mixture of custom scripts, 3rd party software, and manual curation. A workflow manager is a piece of software that keeps track of and executes each step. The two most critical pieces of information that a workflow manager should keep track of is the software version of the tools and the input parameters.
Here is a non-comprehensive list of workflow managers available from [wikipedia](https://en.wikipedia.org/wiki/Bioinformatics_workflow_management_system):
  * Galaxy: Web based graphical workflow manager
  * GenePattern: Web based workflow manager
  * BioBIKE: Web-based, programmable, integrated biological knowledge base.
  * Anduril: Workflow is described in a proprietary scripting language, AndurilScript.

When deciding on a workflow manager, there is a number of secondary qualities you should consider: ease of use, community support, extensibility, and extensive support for available tools. While BioBIKE may meet some specific use cases, it is not well suited for general tasks compared to the other options. Anduril has a steep learning curve and dependency on third party tools to get started. GenePattern and Galaxy are the two main contenders for general use. The defining quality that sets Galaxy apart from GenePattern is its graphical visualisation of the workflow. This makes it very easy and intuitive to get started with Galaxy with minimal training.

<a href="images/welcometogalaxy.png"><img src="images/welcometogalaxy.png" class="screenshot" /></a>

<a href="images/HIV_workflow.png"><img src="images/HIV_workflow.png" class="screenshot" /></a>

<a href="images/AWS/AWS1.jpg"><img src="images/AWS/AWS1.jpg" class="screenshot" /></a>
<a href="images/AWS/AWS2.jpg"><img src="images/AWS/AWS2.jpg" class="screenshot" /></a>
<a href="images/AWS/AWS3.jpg"><img src="images/AWS/AWS3.jpg" class="screenshot" /></a>
<a href="images/AWS/AWS4.jpg"><img src="images/AWS/AWS4.jpg" class="screenshot" /></a>
<a href="images/AWS/AWS5.jpg"><img src="images/AWS/AWS5.jpg" class="screenshot" /></a>
<a href="images/AWS/AWS6.jpg"><img src="images/AWS/AWS6.jpg" class="screenshot" /></a>
<a href="images/AWS/AWS7.jpg"><img src="images/AWS/AWS7.jpg" class="screenshot" /></a>
<a href="images/AWS/AWS8.jpg"><img src="images/AWS/AWS8.jpg" class="screenshot" /></a>
<a href="images/AWS/AWS9.jpg"><img src="images/AWS/AWS9.jpg" class="screenshot" /></a>
<a href="images/AWS/AWS10.jpg"><img src="images/AWS/AWS10.jpg" class="screenshot" /></a>
<a href="images/AWS/AWS11.jpg"><img src="images/AWS/AWS11.jpg" class="screenshot" /></a>
<a href="images/AWS/AWS12.jpg"><img src="images/AWS/AWS12.jpg" class="screenshot" /></a>
<a href="images/AWS/AWS13.jpg"><img src="images/AWS/AWS13.jpg" class="screenshot" /></a>
<a href="images/AWS/AWS14.jpg"><img src="images/AWS/AWS14.jpg" class="screenshot" /></a>
<a href="images/AWS/AWS15.jpg"><img src="images/AWS/AWS15.jpg" class="screenshot" /></a>
<a href="images/AWS/AWS16.jpg"><img src="images/AWS/AWS16.jpg" class="screenshot" /></a>
<a href="images/AWS/AWS17.jpg"><img src="images/AWS/AWS17.jpg" class="screenshot" /></a>
<a href="images/AWS/AWS18.jpg"><img src="images/AWS/AWS18.jpg" class="screenshot" /></a>
<a href="images/AWS/AWS19.jpg"><img src="images/AWS/AWS19.jpg" class="screenshot" /></a>
<a href="images/AWS/AWS20.jpg"><img src="images/AWS/AWS20.jpg" class="screenshot" /></a>
<a href="images/AWS/AWS21.jpg"><img src="images/AWS/AWS21.jpg" class="screenshot" /></a>
<a href="images/AWS/AWS22.jpg"><img src="images/AWS/AWS22.jpg" class="screenshot" /></a>
<a href="images/AWS/AWS23.jpg"><img src="images/AWS/AWS23.jpg" class="screenshot" /></a>
