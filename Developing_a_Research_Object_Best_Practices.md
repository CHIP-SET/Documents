#Developing a Research Object - Best Practices

###Q:  What is the purpose of the research object? (see determining the purpose of a research object using user stories.)  

There are a number of motivations for creating a research object, some examples include: 
- A paper publication with supporting material. 
- The record of experimental process.  
- Publication of Source Code.
- Data publication. 
- Software publication. 
- A simple aggregation of resources.   

We are establishing a process of determining the purpose of a research object through the elicitation of User Stories. User stories are a mechanism established in the Agile software development process, they are “a short, simple description of a feature told from the perspective of the person who desires the new capability, usually a user or customer of the system.”

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

The resources that need to be shared should directly reflect the purpose of the research object. For common types of publication there may be recommendations or a minimum information checklist that describes the resources that are required for this type of research object.

  
###Q:  Do those resources currently reside online or offline? 
 
Where the resources live can have an impact on other features of the research object such as identity, and the mechanism for serialising the research object for exchange. 

There are three possible scenarios for the collection of resources that make up a research object 

1. All resources currently reside online somewhere and can be referenced via a URI, 
2.  All resources reside offline, or 
3.   Resources reside both online and offline. 

For the purposes of exchange there are two main approaches, the exchange of a **Description** or **Bundle**

 - **Description**: For (1) The research object can be simply an aggregation of links/references to those resources. It is then just the description of the aggregation that needs to be shared to effectively share the research object.
 -  **Bundle**: For (2) and (3) offline resources can either be uploaded to an appropriate repository first, or the resources can be bundled together using some packaging mechanism.  

###Q:  What identity mechanism/s currently exist for those resources? 

An identity mechanism is required for resources that are aggregated in a research object for two reasons:

1. To be able to talk unambiguously about those resources.
2. To be able look up those resources. 

A previous study by [Duerr2011][#Duerr2011] that investigates the utility of identification schemes in  the earth sciences breaks these requirements down further into 4 separate issues: 

* A Unique Identifier: To uniquely and unambiguously identify a particular piece of data, no matter which copy a user has
* A Unique Locator: To locate an authoritative copy of the data no matter where they are currently held
* A Citable Locator: To identify cited data
* Scientifically Unique Identifier: To be able to tell that two data instances contain the same information even if the formats are different

The recommendation is to use some form of Permanent Identifier (PIDs) or Permanent URL (PURLs) over standard URIs. If no PID or PURL mechanism exists for a resource and URLs are to be used, they should strive to be COOL [#Berners-Lee].  A recent paper by *Van de Sompel et al.* [#Van de Sompel et al. (2014)] from the Los Alamos National Laboratory describes the relative strengths of URL, PURL and PID identification systems for scholarly publishing. The authors also highlight a further requirement for the identity scheme to support *content negotiation* so that we can retrieve a machine-readable representation of the artefact represented by the identifier.

###Q: Do you need to share a specific version of that resource? 

If you need to share a specific version of a resource, then this may be impacted by the identity mechanism, or whether that resource is under your stewardship.

Consider for example what resource is identified by the URL for the json-ld specification: 

http://www.w3.org/TR/json-ld/

This URL will always resolve to latest version of the spec. Alternatively the following URL identifies a specific version of the specification: 

http://www.w3.org/TR/2014/REC-json-ld-20140116/

Another approach to versioned resources is through the use of [Momento](http://www.mementoweb.org/guide/quick-intro/)  which supports the retrival of previous versions of web resources, allowing for content negotiation based upon a time stamp. 

Alternative approaches may need to be taken when the resource is not under your stewardship, and there is no versioned URI scheme. 


###Q:  What are the licensing requirements/restrictions for each of those resources? 

The licensing of the resources will impact how they can be shared. 

Most importantly it may affect whether resources can be serialised as part of a research object bundle, or whether they can only be referenced as part of the research object manifest description.  

Consider for example the inclusion of the article text of an existing publication, as is done in the [clinical codes research object](https://github.com/CHIP-SET/clinicalcodes.article5). The associated publication "Withdrawing performance indicators: retrospective analysis of general practice performance under UK Quality and Outcomes Framework" - (dx.doi.org/10.1136/bmj.g330) has been published as an open access article. We are therefore able to serialise the pdf itself as part of the research object bundle, and include it in the manifest as follows: 

	 "aggregates" : [
	 {
      "uri" : "http://dx.doi.org/10.1136/bmj.g330",
      "bundledAs" : {
        "filename"  : "/bmj.g330.pdf"
        "proxy" : "urn:uuid:83a3d644-b44a-42b2-b766-8cb269ec3f28"
      }
    },
    ...
 
If the article's copyright had instead been retained by the publisher, we would be restricted to only providing a URI pointing to the publication and not including the pdf. 
###Q:  Do you need to support the exchange and use of the Research Object’s resources offline?  

The ro bundle [#Soiland-Reyes] mechanism of serialisation is based upon a Zip archive that specialises the Adobe Universal Container Format. The ro bundle contains a manifest file that describes the aggregation. This manifest can refer to files that are part of the Zip archive, or simply refer to resources that are elsewhere via a URI.  

Consider as well any restrictions of authorisation, and whether certain parts of the research object are restricted, and should only be accessible to certain people. In this case then it would be prefereable for the resources to remain hosted in their original location - so that authentication and authorization remains with the original data provider.

###Q:  Do you need to manage versioning of the Research Object itself? If so what constitutes a new version of your Research Object?

There are existing mechanisms for versioning of artefacts in different domains. Software versioning for example can be managed using a version control system such as git. 

There are also features from the Provenance and Versioning (PAV) ontology[#Pav] that can be introduced into the manifest to indicate versioning and lineage of a research object. 

###Q:  What additional metadata must / should / is optionally required to support the stated purpose of the research object?

As well as metadata relating to licensing, versioning, attribution etc. there may also be domain or purpose specific metadata.   Once again there may be community standards or minimum information checklists for the minimum set of metatdata to provide when sharing a particular type of resources or experimental description. 

###Q:  What controlled vocabularies currently exist to support the recording of that metadata?  

One aim of research objects is to create a machine readable version of the data or investigation etc. As a result we encourage the use of machine readable vocabularies to create the annotations that describe metadata about the research object. 
The software ontology [#SWO] for example is a structured vocabulary for describing many aspects of the description of software and software development. If the purpose of the research object is to advertise software for reuse then it might be useful to annotate the entry with terms from the SWO to aide discovery. 


 
##References 

[#Van de Sompel et al. (2014)]: Van de Sompel et al., 2014, **Persistent Identifiers for Scholarly Assets and the Web: The Need for an Unambiguous Mapping** 

[#Soiland-Reyes]: Stian Soiland-Reyes **The Research Object Bundle Specification** *https://wf4ever.github.io/ro/bundle/*

[#Berners-Lee]: Tim Berners-Lee **COOL URIs**, 1998 *http://www.w3.org/Provider/Style/URI*

[#SWO]: **The Software Ontology.** *http://bioportal.bioontology.org/ontologies/SWO*

[#Pav]: The Provenance and Versioning (PAV) ontology  https://code.google.com/p/pav-ontology/

[#Duerr2011]:  Ruth E. Duerr et al., **On the utility of identification schemes for digital earth science data: an assessment and recommendations**
