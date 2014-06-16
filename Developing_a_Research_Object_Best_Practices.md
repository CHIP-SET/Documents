#Developing a Research Object - Best Practice

###Q:  What is the purpose of the research object? (see determining the purpose of a research object using user stories.)  

There are a number of motivations for creating a research object, some examples include: 
- A paper publication with supporting material. 
- The record of experimental process.  
- Publication of Source Code.
- Data publication. 
- Software publication. 
- A simple aggregation of resources.   

We are establishing a process of determining the purpose of a research object through the elicitation of User Stories. User stories are a mechanism established in the Agile software development process, they are “short, simple description of a feature told from the perspective of the person who desires the new capability, usually a user or customer of the system.”

A user story typically follows the form: 

	As a <type of user>, I want to <some goal> so that <some reason>, 
for example:  

	As a software developer want to publish software tooling so that it can be reused by others in their analysis.

The User story above is broad in its scope, and stories like this are often referred to as “Epics”. We aim to use Epics to establish to overall purpose of the research object. The questions below are then used to break these down into actionable user stories.

User Stories are not necessarily restricted to user interaction and can instead take the Feature-Driven form
	\<action> \<result> \<object> 

for example:

	Assign a new DOI to the source code.  

There may also be more than one user story or feature associated with the purpose of the research object. 

The established purpose of the research object should be continually referred to when addressing each of the subsequent questions. 


### Q:  What resources do you need to share to support that purpose? Is there a minimum information checklist that defines the resources that are required? 

The resources that need to be shared should directly reflect that purpose of the research object. There may be a minimum information checklist that describes the resources that are required for this type of research object.

  
###Q:  Do those resources currently reside online or offline? 
 
There are three possible scenarios for the collection of resources that make up a research object 

1. All resources currently reside online somewhere, 
2.  All resources reside offline, or 
3.   Resources reside both online and offline. 

Where the resources live ...

Description: For (1) The research object can be simply an aggregation of links/references to those resources. It is then just the description of the aggregation that needs to be shared to effectively share the research object.

Bundle: For (2) and (3) offline resources can either be uploaded to an appropriate repository first, or the resources can be bundled together using some packaging mechanism.  

###Q:  What identity mechanism/s currently exist for those resources? 

An identity mechanism is required for resources that are aggregated in a research object for two reasons:

1. To be able to talk unambiguously about those resources.
2. To be able look up those resources. 

The recommendation is to use some form of Permanent Identifier (PIDs) or Permanent URL (PURLs) over standard URIs. If no PID or PURL mechanism exists for a resource and URLs are to be used, they should strive to be COOL [Berners-Lee 98].  A recent paper by [Van de Sompel et al. (2014)] from the Los Alamos National Laboratory describes the relative strengths of URL, PURL and PID identification systems for scholarly publishing. 

###Q: Do you need to share a specific version of that resource? 

If you need to share a specific version of a resource, then this may be impacted by the identity mechanism, or whether that resource is under your stewardship.

Consider for example what resource is identified by the URL for the json-ld specification: 

http://www.w3.org/TR/json-ld/

This URL will always resolve to latest version of the spec. Alternatively the following URL identifies a specific version of the specification: 

http://www.w3.org/TR/2014/REC-json-ld-20140116/

Another approach to versioned resources is through the use of [Momento](http://www.mementoweb.org/guide/quick-intro/)  which supports the retrival of previous versions of web resources, allowing for content negotiation based upon a time stamp. 

Alternative approaches may need to be taken when the resource is not under your stewardship, and there is no versioned URI scheme. 


###Q:  What are the licensing requirements/restrictions for each of those resources? 

The licensing of the resources will impact how they can be shared. Most importantly it may affect whether resources can be serialised as part of a research object bundle, or whether they can only be referenced as part of the research object manifest description.  
 
###Q:  Do you need to support the exchange and use of the Research Object’s resources offline?  

The ro bundle [Soiland-Reyes. (2013)] mechanism of serialisation is based upon a Zip archive that specialises the Adobe Universal Container Format. The ro bundle contains a manifest file that describes the aggregation. This manifest can refer to files that are part of the Zip archive, or simply refer to resources that are elsewhere via a URI.  

###Q:  Do you need to manage versioning of the Research Object itself? If so what constitutes a new version of your Research Object?

There are existing mechanisms for versioning of artefacts in different domains. Software versioning for example can be managed using a version control system such as git. 

There are also features from the Provenance and Versioning (PAV) ontology that can be introduced into the manifest to indicate versioning and lineage of a research object. 

###Q:  What additional metadata must / should / is optionally required to support the stated purpose of the research object?

As well as metadata relating to licensing, versioning, attribution etc. there may also be domain or purpose specific metadata.   

###Q:  What controlled vocabularies currently exist to support the recording of that metadata?  

One aim of research objects is to create a machine readable version of the data or investigation etc. As a result we encourage the use of machine readable vocabularies to create the annotations that describe metadata about the research object. 
The software ontology [SWO] for example is a structured vocabulary for describing many aspects of the description of software and software development. If the purpose of the research object is to advertise software for reuse then it might be useful to annotate the entry with terms from the SWO to aide discovery. 
 
##References 

**Van de Sompel et al. (2014)**  Persistent Identifiers for Scholarly Assets and the Web: The Need for an Unambiguous Mapping 

**Soiland-Reyes (2013)** Research Object Bundle Specification 

**Berners-Lee 1998** http://www.w3.org/Provider/Style/URI

**SWO** http://bioportal.bioontology.org/ontologies/SWO

**Provenance and Versioning (PAV) ontology**  https://code.google.com/p/pav-ontology/
