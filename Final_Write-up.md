
# Bail Ontology Final Write-up

### 1. The Bail Ontology (BailOnt) is current, includes the appropriate prefixes, and doesn’t include imports.: 

http://purl.org/lis590OD/Fall17/BailOnt


### 2. Links: BailOnt has been updated to include the following integrations to classmates' ontologies:

BailOnt to Crime Charge Ontology
- Equivalencies for Defendant / Charged Person and Judge / Judge
- Bail Type influenced by Charge
- Justice System Events has factor of Charge

BailOnt to Employment Ontology
- Defendant agent of Work Relationship


### 3. Integration to the Agency relationship / Org Rel Ontology: 

BailOnt to Organization Relationship
- Court Branch has agency in Bail Events
- Defendants are clients in Bail Events


### 4. Testing the imported vocabularies and Inferences:

The State of Affairs -
* The situation illustrated is a case where a bail has been set for a person named Smith on November 24th. A JusticeSystem_Event exists and should be interpreted as being a BailEvent. This event has an interval BailTime (time), and a CaseDefendant (factor).

What is being Asserted -
* Instance of class type JusticeSystem_Event, “Bail_Smith_1110”, has the following property assertions:
* “Bail_Smith_1110” :hasBailTime “BailSet_2017_11_24”
* “Bail_Smith_1110” :hasCaseDefendant “CaseDef_Smith_1110”

What is being Inferred -
* It is being inferred that the JusticeSystem_Event “Bail_Smith_1110” is of the subclass type BailEvent.
 
How the restrictions work  -
* The inference works because the class BailEvent is defined as a subclass of JusticeSystem_event and the subclass of an anonymous class of things with an owl:Restriction of:

- owl:onProperty :hasBailTime ; owl:someValuesFrom :BailTime
- owl:onProperty :hasCaseDefendant  ; owl:someValuesFrom :CaseDefendant

* Therefore when I assert that the JusticeSystem_Event is in those object property relationships the reasoner infers that the individual “Bail_Smith_1110” is a BailEvent.
* This changed from the way I approached Assignment 5. After A:5 we, as a class, established a different way of handling the OrgRel Event time.
* The new instances took that into consideration.
