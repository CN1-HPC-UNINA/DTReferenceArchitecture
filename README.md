# CN1-HPC-Spoke9 DT Reference Architecture
Although the concept of DT has been around for nearly twenty years, industrial and academic interest in this field has only recently developed, and little effort has been devoted to the identification of a commonly accepted definition, as well as of an architectural and functional characterization of DTs. 
To bridge this gap, the partners of the **Spoke 9 - Digital Society and Smart Cities** have been working toward the definition of a reference DT conceptual architecture that could be applied to any DT independently of the specific application domain. This activity led to the identification of functional and non functional requirements fundamental to the smart city domain and to the definition of a high-level reference architecture. 

Identified functional requirements encompass the major architectural aspects that define what a DT must or should do. Clearly, the following listing is not intended to be exhaustive, but it aims at representing the most recurring FRs related to digital twins. 

- **R01**	Digital Representation	The DT must digitally replicate the Physical Twin (PT) it represents, capturing all essential aspects of its behavior and characteristics in a digital format.

- **R02**	Standardized representation of Data	The DT should utilize a standardized data structure and format to store and process information related to the PT. 

- **R03**	Synchronization between DT and PT	The DT must maintain real-time or near real-time  synchronization with its PT to ensure that the digital representation reflects its current state and behavior. 

- **R04**	Actionable functional output	The DT must be able to generate actionable outputs that can include simple recommendations to mitigate potential risks or failures or alerts to be further handled by human operators or commands directly executed in the PT. 

- **R05**	Real-time physical state monitoring	The DT must continuously monitor and capture physical states and conditions of the PT at time intervals. This enables timely detection of changes, trends or abnormalities in the PT behavior. 

- **R06**	Anomaly detection monitoring	The DT should possess the capability to detect anomalies (in a broad sense) or deviations from normal operating conditions in the PT. Upon detection, the DT can raise alerts to stakeholders.

- **R07**	Remote control of the PT	A DT should have the ability to remotely control certain aspects or functions of the PT by sending commands or instructions based on physical data analysis. This enables operators or automated systems to intervene, adjust settings or perform actions without direct physical access to the PT.

- **R08**	Prediction of future physical states	A DT can forecast and predict future states, behaviors or conditions of the PT based on historical data, real-time inputs and predictive analytics. These predictions can support proactive decision-making, resource allocation, planning for optimal performance. 


Just like functional requirements, quality attributes or so-called non-functional requirements (NFRs) such as data interoperability, maintainability, performance and so on can have a significant impact on the architecture design and thus on the resulting reference architecture of digital twins. In fact, neglecting NFRs can lead to DT systems that are inefficient, insecure or unable to meet performance expectations, compromising their utility and reliability. 
Among possible NFRs, data interoperability and data sovereignty are of particular interest for contexts such as smart cities. 

*Data interoperability* refers to the capability of software systems or their components to exchange and effectively utilize shared information. Without interoperability, different systems within a city but also different departments and stakeholders (transportation, energy, waste management) wouldn't be able to communicate with one another, hindering the overall effectiveness of the smart city ecosystem. 

*Data sovereignty* is based on multiple aspects: i) data portability representing the possibility to move data from one system to another; ii) data usage with consent; iii) transparency about what happens with data; iv) data ownership. Data sovereignty implies that each organization (and every citizen) within a city has control over their data and that data collected by sensors and other devices are properly stored and controlled according to city regulations and citizen privacy rights, and this clearly affects also the virtual city counterparts.

In light of the above considerations, we identified the following additional requirements (see Table x.y):
- **R09**	Data Interoperability	The DT must facilitate seamless exchange of data between different service providers (the respective PT or other DTs) without impacting on the interoperability of data.

- **R10**	Data Storage	The DT must allow data owners  to choose where their data are host or stored, avoiding vendor lock-in. Data owners can freely move their data between different systems or providers without losing data integrity or functionality. 

- **R11**	Data Usage Consent Management	The DT must include mechanisms for data owners to manage and control access permissions, in order to specify who can access data and for what purposes. 

- **R12**	Data Access Control and Monitoring	The DT must provide tools for data owners to monitor and audit access to their data, ensuring transparency and accountability. Data owners should have full control over their data, including the ability to define who can access, modify or use the data and under what conditions.
R13	Data Ownership 	The DT must implement measures to protect data ownerships rights, safeguarding data owners against unauthorized use or misuse of their data.


Starting from previous results, we enhanced the reference DT architecture as follows:


![The Reference DT Architecture](https://github.com/CN1-HPC-UNINA/DTReferenceArchitecture/arch.png)


The Physical Subsystem is responsible for handling data collection from multiple and heterogeneous data sources related to the physical system to be digital replicated. A Third Party data providers element has been added to model the presence of possible additional data sources that are not part of the Physical Twin, but provide required data useful for DT services. 

The Data Ingestion Subsystem is responsible for raw data ingestion and homogenization.

The Modeling Subsystem is in charge of the digital modeling functionalities. This is important to realize a proper Digital Twin system. 

The Processing Subsystem deals with big data or low latency data processing, distinguishing the well-known batch and stream processing. 

The Visualization Subsystem allows to present data and model in dashboards or through augmented reality to external operators/stakeholders.

Finally the Service Subsystem is responsible for implementing all the services built upon the modeling and data processing subsystems. These services can be exposed by means of APIs (e.g., REST). 

Moreover, we added three vertical layers to model functionality that will be of interest for all the vertical ones. Firstly, the Communication Subsystem involve lightweight and not brokers to allows the communication among multiple data producers and multiple data consumers, e.g., the Physical Twin with its respective Digital Twin and/or a Digital Twin of a physical system with the virtual replica of another physical twin. A Security Subsystem to prevent the exploitation of system’s vulnerabilities has been added. As discussed in the previous deliverable, the Storage Subsystem (R10) is responsible for preserving data circulating in a Digital Twin environment, such as real world data, domain expert knowledge, outcomes from models simulation or service execution.
Finally an Interoperability and Sovereignty Management Subsystem (R9, R11, R13) has been added to satisfy requirements related to data sovereignty and interoperability, together with the Security Subsystem (R12).
