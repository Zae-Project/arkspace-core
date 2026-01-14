# ArkSpace Reference Materials

**Document Type**: Reference Bibliography  
**Last Updated**: January 14, 2026  
**Scope**: Key research papers, technical standards, and regulatory documents

---

## Table of Contents

1. [Neuroscience & Consciousness Research](#neuroscience--consciousness-research)
2. [Spiking Neural Networks](#spiking-neural-networks)
3. [Brain-Computer Interfaces](#brain-computer-interfaces)
4. [Satellite Communications](#satellite-communications)
5. [Optical Inter-Satellite Links](#optical-inter-satellite-links)
6. [Regulatory & Standards Documents](#regulatory--standards-documents)
7. [Cybersecurity & Medical Device Security](#cybersecurity--medical-device-security)
8. [Technical Standards](#technical-standards)

---

## Neuroscience & Consciousness Research

### Foundational Papers

**Libet, B., et al. (1983)**  
"Time of conscious intention to act in relation to onset of cerebral activity (readiness-potential): The unconscious initiation of a freely voluntary act"  
*Brain*, 106(3), 623-642  
DOI: 10.1093/brain/106.3.623  
**Relevance**: Establishes ~350ms lag between neural events and conscious awareness (Libet buffer), critical for latency budget

**Sperry, R.W. (1968)**  
"Hemisphere deconnection and unity in conscious awareness"  
*American Psychologist*, 23(10), 723-733  
DOI: 10.1037/h0026839  
**Relevance**: Split-brain research foundational to corpus callosum interface approach

**Watanabe, M., et al. (2014)**  
"Interhemispheric transfer of visual information in split-brain patients"  
*Neuropsychologia*, 63, 133-142  
DOI: 10.1016/j.neuropsychologia.2014.08.025  
**Relevance**: Informs Uni-Hemispheric Subjective Test validation protocol

**Tononi, G. (2008)**  
"Consciousness as integrated information: a provisional manifesto"  
*Biological Bulletin*, 215(3), 216-242  
DOI: 10.2307/25470707  
**Relevance**: Integrated Information Theory (IIT) provides framework for consciousness measurement

**Schurger, A., et al. (2012)**  
"An accumulator model for spontaneous neural activity prior to self-initiated movement"  
*Proceedings of the National Academy of Sciences*, 109(42), E2904-E2913  
DOI: 10.1073/pnas.1210467109  
**Relevance**: Reinterprets Libet experiments, validates neural buffering concept

---

## Spiking Neural Networks

### SNN Theory & Implementation

**Maass, W. (1997)**  
"Networks of spiking neurons: The third generation of neural network models"  
*Neural Networks*, 10(9), 1659-1671  
DOI: 10.1016/S0893-6080(97)00011-7  
**Relevance**: Foundational paper on SNN computational power

**Gerstner, W., & Kistler, W.M. (2002)**  
*Spiking Neuron Models: Single Neurons, Populations, Plasticity*  
Cambridge University Press  
ISBN: 9780521890794  
**Relevance**: Comprehensive reference for LIF neuron models used in ArkSpace

**Eliasmith, C., et al. (2012)**  
"A large-scale model of the functioning brain"  
*Science*, 338(6111), 1202-1205  
DOI: 10.1126/science.1225266  
**Relevance**: Spaun model demonstrates large-scale SNN cognitive modeling (basis for Nengo framework)

**Davies, M., et al. (2018)**  
"Loihi: A neuromorphic manycore processor with on-chip learning"  
*IEEE Micro*, 38(1), 82-99  
DOI: 10.1109/MM.2018.112130359  
**Relevance**: Intel Loihi architecture used as reference for ArkSpace neuromorphic payload

**Bekolay, T., et al. (2014)**  
"Nengo: a Python tool for building large-scale functional brain models"  
*Frontiers in Neuroinformatics*, 7, 48  
DOI: 10.3389/fninf.2013.00048  
**Relevance**: Nengo framework used for SNN model development in Consciousness.ai

### Spike-Timing-Dependent Plasticity (STDP)

**Markram, H., et al. (1997)**  
"Regulation of synaptic efficacy by coincidence of postsynaptic APs and EPSPs"  
*Science*, 275(5297), 213-215  
DOI: 10.1126/science.275.5297.213  
**Relevance**: Original STDP discovery, basis for learning rules in ArkSpace SNNs

**Bi, G.Q., & Poo, M.M. (1998)**  
"Synaptic modifications in cultured hippocampal neurons: dependence on spike timing, synaptic strength, and postsynaptic cell type"  
*Journal of Neuroscience*, 18(24), 10464-10472  
DOI: 10.1523/JNEUROSCI.18-24-10464.1998  
**Relevance**: Characterizes temporal window for STDP (~20ms), informs learning implementation

---

## Brain-Computer Interfaces

### Invasive BCIs

**Hochberg, L.R., et al. (2012)**  
"Reach and grasp by people with tetraplegia using a neurally controlled robotic arm"  
*Nature*, 485(7398), 372-375  
DOI: 10.1038/nature11076  
**Relevance**: BrainGate system demonstrates feasibility of high-bandwidth neural control

**Oxley, T.J., et al. (2016)**  
"Minimally invasive endovascular stent-electrode array for high-fidelity, chronic recordings of cortical neural activity"  
*Nature Biotechnology*, 34(3), 320-327  
DOI: 10.1038/nbt.3428  
**Relevance**: Stentrode demonstrates less-invasive BCI approach, though corpus callosum interface requires surgical access

**Benabid, A.L., et al. (2019)**  
"An exoskeleton controlled by an epidural wireless brain–machine interface in a tetraplegic patient: a proof-of-concept demonstration"  
*The Lancet Neurology*, 18(12), 1112-1122  
DOI: 10.1016/S1474-4422(19)30321-7  
**Relevance**: Demonstrates long-term wireless BCI viability

### Corpus Callosum Anatomy

**Aboitiz, F., et al. (1992)**  
"Fiber composition of the human corpus callosum"  
*Brain Research*, 598(1-2), 143-153  
DOI: 10.1016/0006-8993(92)90178-C  
**Relevance**: ~200-250 million axons in corpus callosum, defines electrode array requirements

**Hofer, S., & Frahm, J. (2006)**  
"Topography of the human corpus callosum revisited—comprehensive fiber tractography using diffusion tensor magnetic resonance imaging"  
*NeuroImage*, 32(3), 989-994  
DOI: 10.1016/j.neuroimage.2006.05.044  
**Relevance**: DTI mapping of callosal fiber organization, informs electrode placement strategy

### Axonal Regeneration

**Silver, J., & Miller, J.H. (2004)**  
"Regeneration beyond the glial scar"  
*Nature Reviews Neuroscience*, 5(2), 146-156  
DOI: 10.1038/nrn1326  
**Relevance**: CNS regeneration challenges and strategies for electrode integration

**Filous, A.R., et al. (2014)**  
"Axon-astrocyte interactions during axonal regeneration"  
*Experimental Neurology*, 258, 105-118  
DOI: 10.1016/j.expneurol.2014.04.006  
**Relevance**: Biocompatible coatings to promote axonal growth onto CMOS array

---

## Satellite Communications

### LEO Constellation Design

**Walker, J.G. (1984)**  
"Satellite constellations"  
*Journal of the British Interplanetary Society*, 37, 559-572  
**Relevance**: Walker Delta pattern used for ArkSpace constellation topology

**Lutz, E., et al. (2000)**  
"The land mobile satellite communication channel—recording, statistics, and channel model"  
*IEEE Transactions on Vehicular Technology*, 49(2), 375-386  
DOI: 10.1109/25.832969  
**Relevance**: LEO channel characteristics for Ka-band

### Ka-Band Satellite Systems

**Ippolito, L.J. (2017)**  
*Satellite Communications Systems Engineering: Atmospheric Effects, Satellite Link Design and System Performance*  
Wiley, 2nd edition  
ISBN: 978-1119259374  
**Relevance**: Comprehensive reference for Ka-band link budget calculations

**Evans, B.G., et al. (2005)**  
"Integration of satellite and terrestrial systems in future multimedia communications"  
*IEEE Wireless Communications*, 12(5), 72-80  
DOI: 10.1109/MWC.2005.1522108  
**Relevance**: Hybrid satellite-terrestrial architecture similar to ArkSpace edge node model

---

## Optical Inter-Satellite Links

### OISL Technology

**Toyoshima, M., et al. (2005)**  
"Ground-to-satellite laser communication experiments"  
*IEEE Aerospace and Electronic Systems Magazine*, 23(8), 10-18  
DOI: 10.1109/MAES.2008.4607894  
**Relevance**: Validates optical link feasibility for space applications

**Jono, T., et al. (2006)**  
"OICETS on-orbit laser communication experiments"  
*Proceedings of SPIE*, 6105, 610503  
DOI: 10.1117/12.673751  
**Relevance**: OICETS mission demonstrates Gbps-class OISL in orbit

**Gregory, M., et al. (2011)**  
"Commercial optical inter-satellite communication at high data rates"  
*Optical Engineering*, 51(3), 031202  
DOI: 10.1117/1.OE.51.3.031202  
**Relevance**: Tesat LCT terminal heritage, 60+ Gbps demonstrated

**Carrasco-Casado, A., et al. (2019)**  
"LEO-to-ground optical communications using SOTA (Small Optical TrAnsponder)—Payload verification results and experiments on space quantum communications"  
*Acta Astronautica*, 164, 164-176  
DOI: 10.1016/j.actaastro.2019.07.030  
**Relevance**: CubeSat-scale optical terminals validate miniaturization for ArkSpace

---

## Regulatory & Standards Documents

### FCC Regulations

**FCC (2020)**  
"Mitigation of Orbital Debris in the New Space Age" (FCC 20-54)  
DA 20-1170  
Federal Communications Commission  
https://www.fcc.gov/document/fcc-adopts-new-rules-address-orbital-debris-mitigation  
**Relevance**: 25-year deorbit rule compliance required for ArkSpace

**FCC (2018)**  
"Processing Round for NGSO FSS Satellite Applications" (DA 18-313)  
Federal Communications Commission  
https://www.fcc.gov/document/fcc-establishes-processing-round-ngso-fss-applications  
**Relevance**: Competitive application process for NGSO FSS systems

**47 CFR § 25**  
"Satellite Communications"  
U.S. Code of Federal Regulations  
https://www.ecfr.gov/current/title-47/chapter-I/subchapter-B/part-25  
**Relevance**: Complete regulatory framework for FCC Part 25 licensing

### ITU Radio Regulations

**ITU (2020)**  
"Radio Regulations, Edition of 2020"  
International Telecommunication Union  
ISBN: 978-92-61-31601-2  
**Relevance**: Article 9 frequency coordination procedures, Ka-band allocations

**ITU-R Recommendation M.1643-0**  
"Interference protection criteria for spaceborne passive sensors from emissions of active space radiocommunication services"  
International Telecommunication Union  
**Relevance**: EPFD limits for NGSO FSS systems

### Export Control Regulations

**22 CFR § 120-130**  
"International Traffic in Arms Regulations (ITAR)"  
U.S. Department of State  
https://www.ecfr.gov/current/title-22/chapter-I/subchapter-M  
**Relevance**: ITAR Category XV satellite export control requirements

**15 CFR § 730-774**  
"Export Administration Regulations (EAR)"  
Bureau of Industry and Security  
https://www.bis.doc.gov/index.php/regulations/export-administration-regulations-ear  
**Relevance**: EAR classification for neuromorphic hardware and encryption

### NASA Standards

**NASA-STD-8719.14**  
"Process for Limiting Orbital Debris"  
NASA Technical Standards Program  
**Relevance**: Orbital debris mitigation best practices, NASA DAS software

**NASA-STD-3001**  
"Space Flight Human-System Standard"  
NASA Technical Standards Program  
**Relevance**: Human safety standards applicable to consciousness transfer systems

---

## Cybersecurity & Medical Device Security

### Medical Device Security

**Pycroft, L., et al. (2016)**  
"Brainjacking: Implant security issues in invasive neuromodulation"  
*World Neurosurgery*, 92, 454-462  
DOI: 10.1016/j.wneu.2016.05.010  
**Relevance**: Foundational threat model for BCI cybersecurity, coined "brainjacking" term

**FDA (2018)**  
"Content of Premarket Submissions for Management of Cybersecurity in Medical Devices"  
U.S. Food and Drug Administration  
https://www.fda.gov/regulatory-information/search-fda-guidance-documents/content-premarket-submissions-management-cybersecurity-medical-devices  
**Relevance**: FDA guidance for medical device cybersecurity submissions

**Burleson, W., et al. (2012)**  
"Design challenges for secure implantable medical devices"  
*Proceedings of the 49th Annual Design Automation Conference*, 12-17  
DOI: 10.1145/2228360.2228364  
**Relevance**: Security-by-design principles for implantable devices

### Cryptography

**NIST (2001)**  
"Advanced Encryption Standard (AES)" (FIPS PUB 197)  
National Institute of Standards and Technology  
https://csrc.nist.gov/publications/detail/fips/197/final  
**Relevance**: AES-256-GCM encryption standard used in ArkSpace

**Langley, A., et al. (2017)**  
"The QUIC Transport Protocol: Design and Internet-Scale Deployment"  
*Proceedings of the Conference of the ACM Special Interest Group on Data Communication*, 183-196  
DOI: 10.1145/3098822.3098842  
**Relevance**: Low-latency encrypted transport, potential future protocol

**NIST (2022)**  
"Post-Quantum Cryptography Standardization"  
National Institute of Standards and Technology  
https://csrc.nist.gov/Projects/post-quantum-cryptography  
**Relevance**: Kyber algorithm for post-quantum key exchange (future roadmap)

---

## Technical Standards

### Space Communications

**CCSDS 131.0-B-4**  
"TM Synchronization and Channel Coding"  
Consultative Committee for Space Data Systems  
https://public.ccsds.org/Pubs/131x0b4e1.pdf  
**Relevance**: Error correction coding for space communications

**CCSDS 141.0-B-1**  
"Optical Communications Coding and Synchronization"  
Consultative Committee for Space Data Systems  
https://public.ccsds.org/Pubs/141x0b1.pdf  
**Relevance**: OISL protocol standards

### CubeSat Standards

**CDS-R-CUB-16-A**  
"CubeSat Design Specification Rev. 13"  
California Polytechnic State University  
https://www.cubesat.org/resources  
**Relevance**: Mechanical and electrical interface standards for CubeSat deployment

### Network Protocols

**RFC 8446**  
"The Transport Layer Security (TLS) Protocol Version 1.3"  
Internet Engineering Task Force  
https://www.rfc-editor.org/rfc/rfc8446  
**Relevance**: TLS 1.3 used for control plane security

**IEEE 802.15.4z**  
"Low-Rate Wireless Networks—Amendment: Enhanced Ultra Wideband (UWB) Physical Layers and Associated Ranging Techniques"  
Institute of Electrical and Electronics Engineers  
**Relevance**: UWB standard for sub-cranial transceiver to edge node link

### Protobuf

**Google Protocol Buffers**  
"Protocol Buffers Documentation"  
Google LLC  
https://developers.google.com/protocol-buffers  
**Relevance**: Serialization format for all ArkSpace binary protocols

---

## Additional Resources

### Textbooks

**Gilmore, D.G. (2002)**  
*Spacecraft Thermal Control Handbook, Volume I: Fundamental Technologies*  
AIAA  
ISBN: 978-1884989117  
**Relevance**: Thermal design for neuromorphic payload

**Wertz, J.R., & Larson, W.J. (1999)**  
*Space Mission Analysis and Design, 3rd Edition*  
Microcosm Press and Springer  
ISBN: 978-1881883104  
**Relevance**: Systems engineering methodology for ArkSpace constellation

### Industry Reports

**SpaceX (2016)**  
"Starlink Non-Geostationary Satellite System, Attachment A Technical Information"  
FCC Filing SAT-LOI-20161115-00118  
**Relevance**: NGSO FSS constellation design precedent

**Amazon (2020)**  
"Kuiper System Description and Technical Information"  
FCC Filing SAT-LOA-20190704-00057  
**Relevance**: Ka-band spectrum coordination reference

---

## Document Maintenance

**Update Frequency**: Quarterly  
**Owner**: ArkSpace Research Team  
**Next Review**: April 14, 2026  
**Classification**: Internal Use Only

---

**End of Reference Materials**
