# BailOnt
CCJJS Project Bail Ontology

## IS590OD - FA2017
#
Over the remainder of this case study / project I will be looking at the domain of bail and its connections to the data we have been given in the case study. A preliminary search of Wikipedia defines bail as, “[…] the practice of releasing suspects from custody before their hearing, on payment of money to the court which may be refunded if suspects return to court for their trial.” (“Bail in the United States”, Wikipedia, [https://en.wikipedia.org/wiki/Bail_in_the_United_States]). The domain fits in with the data from the case study, but I am unfamiliar with the overarching topic and this domain specifically. I will need to do research into IL, and Champaign County, specific practices. I will also need to dig in a research existing vocabularies for structures similar to what I am trying to describe.

Resources on Bail as a topic will range from the general legal resources, to the location specific (municipal documents). There is some good information on "Pretrial Justice" in the full Champaign County report. Federal, State, and County, bail schedules and rules are available online and will be excellent resources. Sometimes the document is referred to as a Bail Schedule and other times it is referred to as a Bond Schedule. I will need to look into the differences between the two. There is quite a bit of literature on the push for bail reform. Bail and income/employment will be a good place for us to make connections. The initial domain resources I will be looking at are:
- Clarke, Stevens H., Freeman, Jean L.Koch, Gary G.The Effectiveness Of Bail Systems: An Analysis Of Failure To Appear In Court And Rearrest While On Bail. [Chapel Hill, N.C.] : Institute Of Government, University Of North Carolina At Chapel Hill, [1976]. Print.
- Parker, Alison,Haas, Danielle,eds. "Not In It For Justice": How California's Pretrial Detention And Bail System Unfairly Punishes Poor People. : . Print.
- Illinois Bail Schedule - [http://www.illinoiscourts.gov/SupremeCourt/Rules/Art_V/ArtV.htm]
- Champaign Bond Schedule - [http://www.champaigncountymunicipalcourt.com/images/pdfs/2017_CRTR_BOND.pdf]

In addition to domain/topic resources I will need to evaluate existing ontologies for their use or inspiration. Participating in linked data is about receiving as well as sharing. The vocabularies I am currently looking at are:
- FOAF - [http://xmlns.com/foaf/spec/]
   For person data, unless it is better for me to connect to a classmate’s definition of the jacket number as an agent.
- Event Ontology or Simple Event Model Ontology
   [http://motools.sourceforge.net/event/event.html]
   [http://semanticweb.cs.vu.nl/2009/11/sem/]
   The SEM ontology already includes “event type” classes and properties that I could use.
- SKOS - [https://www.w3.org/TR/2009/REC-skos-reference-20090818/]
   We are all highly likely to use properties from SKOS.
- Schema.org - [http://schema.org/docs/full.html]
   I have a need to represent the action of attending a hearing. This vocabulary could provide me with those structures. It also has structures for government offices (as organizations) and government buildings (as places). Below is an example of how I might use the Schema.org structures for the domain of Bail.
> <http://example.com/HearingAttendance> a owl:Class ;   
>	rdfs:subClassOf schema:ArriveAction .

The idea is to describe the class “Hearing Attendance” as a sub-class of the schema.org:ArriveAction. ArriveAction would give me access to time and place properties. I could also use the property subjectOf with a range of an Event class. This would just be one of the classes I would look at describing.  Bail is complex and differs from one municipality to the next. It is my hope that the Classes and Properties I work with are general enough for our needs and could be used, and altered, for the needs of others.

The structures (Classes and Properties) I am looking to define for a Bail ontology could grow out of hand if I don’t try to limit myself. As the project moves on I’m sure I will have to cut back in some areas and add in other. My initial brainstorm for potential definitions looked at Bail and the Hearing. 
Using the idea of the AgencyRelationship that we work working on for booking I would work to define a class for the individual instance of a bail associated with the booking. Possibly as a sub-event to the Booking event. I think this would also make a Release a sub-event, and somehow make a bail payment a factor in both the Bail Class and a Release Class.
Using the SEM ontology properties and classes for event types I would look into defining a class for BailType. This would include defining a property with a range of bail amount. I would also need to define a property of hasBailType. Hearing Related structures would include:
- Class of Hearing, sub-class of Event
- Class of HearingAttendance (above) 
- A sub-property of schema:subjectOf with a domain of HearingAttendance and a range of the Hearing (event) class.
We would also need some way of defining a hearing non-attendance so that we can describe a bail being forfeited by a hearing non-attendance. There would also be several properties for describing the times related to these events. Examples of which are:
- bailClearedOn with the range of a time entity
- bailIssuedOn with a range of time
Ideas and structures will change as I do research and attempt to make things logical and provide for integrations with other domains.

When considering integrations with other domain in the case study (those that my colleagues are or could be describing), the areas I could see bail being directly related to are:
- The person / jacket number and demographic information, such as education, employment, and income data.
- The Booking with the Bail instance as a sub-event of a booking.
- The Release as some type of bail is generally a factor in being released.
- Crime codes connected to a Bail/Bond schedule.
As others in the class look into their own areas, I’m sure we will find interesting points of integration which could lead to insights for the county. Through the person integrations we could ask questions about demographics and bail forfeiture. We could look at types of bail, and how long the person spends in jail before release. Identifying trends could help predict resource needs.

Bail, in general, has come under criticism and other counties are working on their own versions of Bail reform. Collecting the data and being able to integrate it with other areas in the county could provide insight into the ways the Champaign county bail system works, and the ways in which it doesn’t. Bail isn’t just about the value of money, it is also an implied value judgement on the crime itself. Looking at how those values have an impact on court proceedings could be helpful in predicting what kinds of resources will be needed through the processing of a booking. An adjustment under a dollar amount could change how people view a case. Much like how people are more likely to buy a product at the price point of $19.99 than they are to spend $20. The domain of bail is worth looking at and could provide value to Champaign county.