OriginTrail
==============

**Table of contents**

- [Glossary](#glossary)

Note: summarised up to https://docs.origintrail.io/dkg-v6-current-version/autonomous-ai-paranets

## Glossary <a id="glossary"></a>

* DKG SDK - client library (e.g. [dkg.js](https://docs.origintrail.io/dkg-v6-current-version/dkg-sdk/dkg-v6-js-client)) for apps to interact via APIs to connect to the OriginTrail DKG to enable creation and management of KAs through apps, and perform network queries (e.g. search SPARQL queries)
* Collaborative Knowledge Graphs
  * Built using DKG paranets
* Initial Paranet Offerings (IPO) - used to incentivise growth of DKG
* Knowledge Assets (KA) - core primative web resource identified by a Uniform Asset Locator (UAL) that is an extension of the traditional URL that is an ownable container of knowledge describing anything that lives in a DKG to be discoverable, where blockchain is used to support ownership and information integrity.
  * NFT - token representing ownership of KA enabling ower to perform all standardised NFT functionality, including transfer ownership, list on NFT marketplace, use in Web3 apps

  * AI Para-networks (Autonomous Paranets) - community paranet operators own these autonomously operated structures in the DKG, and inside these paranets are assemblies of KAs driving use-cases with associated paranet-specific AI services and an incentivization model to reward knowledge miners fueling its growth. 

  * Contents
    - off-chain
      - knowledge - in form of graph data (RDF) and vector embeddings stored on DKG
        - knowledge content - time series of knowledge content states (assertions) each independently verified for integrity, by recomputing its cryptographic fingerprint by verifier, and then checking if the computed result matches corresponding blockchain fingerprint record. 
          - assertions - represented using n-quads serialization and a cryptographic fingerprint used for assertion verification (n-quads graph Merkle root, stored immutably on the blockchain)
    - on-chain
      - cryptographic proofs - representing cryptographic digests of knowledge stored on-chain
      - Uniform Asset Locator (UAL) - unique URI with assigned ownership identifiers of DKG using blockchain accounts, implemented as an NFT record on blockchain, that follow the DID URL specification, used to identify and locate specific KAs within the OriginTrail DKG
        - e.g. `did:dkg:otp:2043/0x5cac41237127f94c2d21dae0b14bfefa99880630/318322#color`
        - did identifier predicate : dkg knowledge graph predicate : blockchain id (e.g. otp:2043 = OriginTrail NeuroWeb Mainnet) : blockchain addresss (e.g. address of asset NFT smart contract) : contract-specific identifier (e.g. id of NFT token) : query and fragment components (e.g. property inside knowledge graph)
      - public assertion data - replicated on the OriginTrail Decentralized Network and publicly available
      - private assertion data - contained within private domain of the asset owner (e.g. OriginTrail Node run by the asset owner, such as a person or company).
    - QUESTION - what is the semantic data record?
  * Querying
    * dkg.js SDK used to perform CRUT (create, read, update, transfer) operations with Knowledge Assets (KA)
  * State Finality
    * DKG applies replication mechanism to reach state consistency for KAs on the network, similar to distributed databases
      * state consistency is reconciled using the blockchain
      * blockchain hosts state proofs for KAs
      * blockchain hosts replication commit information from DKG nodes
      * creation of KAs and updates for existing KAs are accepted by nodes on the network, and can operate with all accepted states
  * State Phases of KAs
    * LATEST_FINALIZED: latest committed state, accepted by the network.
    * LATEST: KA state is pending for an update, awaiting commits from DKG nodes. Once commits are received, the state transitions to LATEST_FINALIZED.
    * HISTORICAL: any previously finalized state, identifiable by state hash.
  * Knowledge Mining
    * process of Knowledge Miners producing high quality, blockchain tracked knowledge for AI leveraging KAs (ownable containers for knowledge with inherent discoverability, connectivity and data provenance) and contributing that useful knowledge to the OriginTrail DKG to receive NEURO tokens as an incentive, where those Knowledge Mining incentives are enabled across multiple blockchains, to drive exponential growth of trusted knowledge in the OriginTrail DKG.
  
* QUES - is it the UAL hash or the Knowledge Graph State Proof that is a merkle proof of the network, where you can make data only sit on your node on your device, choose to only sell some anonymous knowledge data, not say that you are selling that publicly, set a fee for that. private knowledge assets sit on our device, then add only those Knowledge Graph triples from pieces of knowledge that you are selling without revealing the entire file, and can prove what you sold was part of the entire data set.

* Decentralised Retrieval Augmented Generation (dRAG) applications framework
  * Applications Framework that allows AI solutions to fetch the relevant facts dynamically from a hybrid mix of external sources (decentralised since organised in a DKG with verifiable sources) for GenAI models before the generation process, limiting the generation to re-working the retrieved inputs, to enhance accuracy and reliability of responses from GenAI models
    * External sources enabling the hybrid AI system mix include these methodologies:
      * neural networks AI (e.g. LLMs) based on vector embedding representations, which offer powerful learning and generalization capabilities of neural networks
      * symbolic AI (e.g. Knowledge Graph) approach enhances the hybrid AI system mix with its strength of Knowledge Graphs by introducing a basis in the symbolic representation, which offer precise, rule-based processing
    * Operates on two core components
      - (1) DKG paranets
      - (2) AI models
    * Compatible with existing techniques, tools, and RAG frameworks and supports all major data formats. 

* Resource Description Framework (RDF)
  * RDF is a W3C standardized model designed to represent data about physical objects and abstract concepts (resources) to express relations between entities using a graph format.
  * RDF (Directed) graph is composed of triple statements represented by the following data model, where each part can be identified by a Uniform Resource Identifier (URI):
    - (1) a node for the subject,
    - (2) an arc from subject to object, representing a predicate, and;
    - (3) a node for the object (object can be a literal value).
  * RDF 1.1 specification was adopted in 2004 (previously RDF 1.0 adopted as a W3C recommendation in 1999),
  * RDF Schema (RDFS), Web Ontology Language (OWL) and SHACL (Shapes Constraint Language) are ontology languages that are used to describe RDF data.
    * RDFS provide mechanisms for describing related resources and their relationships, similar to object-oriented programming (OOP) languages and differs in that it describes properties in terms of resource classes. RDF enables querying via the SPARQL query language.
  * SPARQL query language is the standard query language for RDF graphs

* Pipeline
  * Graph Build - https://graph.build
    * About
      * Knowledge Graph where data is inherent in the model
      * No code required to generate ontology model mind maps
    * Inputs
      * Kafka stream, test API or JSON
    * Outputs 
      * Knowledge Graph (Gremlin, OpenCypher, etc)
  * AWS Neptune
    * Inputs
      * Use Knowledge Graph as input to AWS Neptune
    * Features
      * Analytics

* Tools
  * Apache Jena / Fuseki (open-source)
  * Blazegraph (open-source, not actively maintained)
  * AWS Neptune (closed-source)
  * Graph Build
  * Graph ML Neo4j
  * Gemini + OriginTrail

* Bridge TRAC to Base - https://superbridge.app/

* Workshops - https://github.com/OriginTrail/dkgcon-workshops-2024

* UI - https://github.com/OriginTrail/edge-node-drag

* DPROD (Data Product Ontology) - open-source standard
  * ekgf.github.io
  * Data Modelling
  * edmcouncil.org
  * ODRL - rights and constraints for data use
  * goal to get more value and less risk from data, properly link assets
