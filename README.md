# KEYSTAMP
## An open-source Proof-of-Compliance standard on the blockchain

by Francis Pouliot, Shayan Eskandari

Written during RegHackTO hackathon, November 27th 2016

With the collaboration of:

- Jean-Philippe Beaudet
- Arthur Gerbelot
- Patrick Poirier
- Philippe Chevry

Presented under the team Existence

## Abstract

We propose an new open-source standard, Keystamp, for integrating applied cryptography and blockchain technologies in existing workflows and commercial relationships such as compliance policy implementation and audit. Specifically, we design an innovative set of policies and procedures for using cryptographic signatures, cryptographic hash functions and the Bitcoin blockchain which allows financial services participants to generate and verify irrefutable proofs that specific indidividuals or organizations possessed information, performed actions or signed messages at a certain point in time. Keystamp is designed to be deployed within organizations and integrated in traditional workflows and business relationships. It aims to become a the standard framework for industry participants to prove the authenticity, validity and integrity of factual data.

Contextual data such as application logs, phone verification / biometrics, video recordings, emails are included in data bundles with signatures which are encrypted, signed, hashed and timestamped. Pseudonymous cryptographic keys are associated to legal identities in a refernece index, maintained in a centralized or distributed database. 

**Proof-of-Compliance** is the output of compliance-related data being processed by using the Keystamp standard. It is a digital trail of unforegable cryptographic signatures, immutable timestamps and encrypted contextual data. At each step of the compliance process, data is gathered, digitally signed, timestamed and encrypted. The decryption of the data, its the validation integrity, the authentification of tis signer and the timestamp's existence can be instantly performed for auditing purposes. 

### Technology overview

- Public key encryption using Bitcoin's Elliptic Curve Digital Signature Algorithm
- The Hierchical Deterministic Wallet extention to Bitcoin known as BIP32
- Cryprogric hash function SHA-256
- Timestamps using OP_RETURN Bitcoin transactions (Blockchain)
- (In development) Open-timestamp infrastructure

### Implementation

We specifically implement the Proof-of-Compliance use-case of Keystamp in the context of “know-your-customer” policies, or any other context where establishing that information was obtained by certain parties at a certain time is required. Proof-of-compliance provides a digital trail of unforgeable signatures and timestamps which consist of irrefutable evidence that someone had certain information, took action or participated in specific events at specific points in time. It is a protocol which turns data into tamper-proof legal evidence.  Keystamp was designed, as an application, to be used by organizations - specifically financial institutions, government institutions and large corporations. Heads of the hieararchy in the organization issue certificates to subordinates (and so on) which grant them the ability to sign and encrypt data.

Since issuance and revocation of contracts are enforced cryptographically and are publicly auditable, easy to authentificate and verify using graphical interfaces over complex cryptographic libraries, anybody can verify who they are talking to and where they derive their authority from in the context of a business relationship. It can be implemented by public bodies such as government and enforcement agencies, so as to limit fraud and foster public trust.

A functional API can integrate easily in any existing traditional workflow, with graphical easy-to-use tools to foster implementation. Since Keystamp aims to be a standard, adoption needs to be implemented voluntarily by a large number of firms in the economy to be successful. Users can also implement Keystamp in their workflow manually using a modern web application.

### Purpose and impact

Keystamp is a Proof-of-Knowledge institution for the digital economy, since this open-source system can be used by anyone, for free, to prove that he possessed any data at any time. The concept is designed to have a sophisticated aggregation of various blockchain-related technologies with an easy to use, graphical interface and a general-purpose open API. These incredibly powerful tools can be used by the public not only to take control of their identity but also to achieve complete trust through the auditable and self-validating nature of the technologies used. As the process of education the public, starting from penetration at the top level of the institutions which are the ultimate beficiairies within their firm of a Keystamp implementation.

It can be used for mediation in civil disputes (contracts) by the general public since proofs are easy to verify. The purpose is to foster trust through disruptive technologies. We aim to increase social cohesion in the digital economy, providing an entirely digital institutional framework of trust for the digital economy.

Keystamp has the potential to enormously decrease the costs of compliance and audit for financial institutions, technology providers, governments, and any institution that needs trust and hierarchical authorizations. It increases transparency and saves money to the taxpayers. Because Keybase operates independantly from any other system and rather connects via API or using the a web application, it is easy to implement in an existing production workflow without changing the system used, as long as the system used can communicate data to the Keystamp app or API.

## Context and use-case

Keystamp was designed during the RegHackTO hackathon organized by the Ontario Securities Commission. The task of Keystap was to respond to the following challenges:

- Ensure that know-your-customer policies have been implemented
- Ensure that investors have the proper knowledge they require
- Help investigators validate proper forms were filed, disclosures signed, etc.
- Remove ambiguity and deniability

Our use-case revolves around three types of financial relationships that are under the purview Ontario Securities Commission:

- The “know-your-customer” process initiated by financial advisors for assessing the risk profile of their investing clients.
- The delivery of data by the producers or sellers of investment products to financial advisors.
- The assessment of the risk profile of the investment products by financial advisors at time at which advice is given to investing clients.

We want to achieve the following goals:

- Issue license, permits, certifications or delegate authority in a hierarchy
- Provide proof that the KYC process was performed by financial advisors (e.g. risk assessment of clients)
- Provide proof of the risk assessment of a security, and the context of its recommendation to the client
- Provide proof that investors understand their risk assessment and the security they are purchasing
- Verify the integrity of data, detecting any tampering or forginc of signatures
- Associate data to individuals to provide "Proof-of-Knowledge"
- Encrypt data for reporting purposes

Compliance data consist of any data used to prove that certain compliance policies were followed. This includes KYC, due diligence, internal audits, release form, consent forms, contracts, etc. In many cases, procedures were followed in person or over the phone. We envision organizational processes where one's perception of events, as well as factual data, is presented to the relevant parties which can "sign-off" on the statement and evidence of the other party. 

### Internal / external compliance, monitoring and reporting with Keybstamp

![Keystamp implementation](https://github.com/existencelabs/keystamp-whitepaper/blob/master/Keystamp%20Implementation%20resized.png)

We identify 5 main actors in our specific use-case for compliance process:

1. The regulator: the entity which assigns keys to firms and which is responsible for monitoring the compliance processes of firms.
2. Firms: they employ financial advisors and report to regulators.
3. Issuers: they sell securities to financial advisors (can be brokers) and report to regulators.
4. Advisors: they recommend securites or purchase securities on behalf of their clients and report to both the firms and the regulators.
5. Investors: they employ financial advisors and ultimately purchase securities and can complain to firms and regulators.

In this specific use-case, we see that there is a hierchical relationship between the OSC and the advisory firms (because of the compliance requirements). The firm enjoys additional rights than its employees or subordinates (e.g. financial advisors, affiliated brokers), for which it generates additional sub certificates.

These sub-certificates are associated to the firm's identity in a public registry, which is common amongst financial regulatory regimes. For examples, numerous jurisdictions have Money Service Businesses and licensed Financial Advisor public registries. 

These firms can then derive child keys for individual, subordinate members of the organization, and so on, according to parameters that are defined by the issuer and/or according to parameters they set themselves, depending on the program design. These child keys are then used for signing data and encrypting data. 

Our two main use cases are:

**Financial advisors**

They will provide all the evidence of a KYC process and respect of certain policies to the investors that they are advising. For example, this can be a risk assemment form and the the conclusions drawn by the financial advisor. For instance, one can imagine a statement by the advisor declaring that he believes his client to be in a high risk profile, meaning that the securities he will recommed will be high risk, and that there is significant chances of financial loss. The advisor will include whatever process he used to come to this conslution (such as an audio recording or form), and the investor will acknowledge that this accurately reflects reality using a cryptographic signature. To remove some complexity, the acknowledgement can be done using traditional remote KYC methods. Proof of these KYC methods, such as the reference ID and applicaiton log of a SMS verification event by a trusted service provider, is included in the data bundle that later becomes the Proof-of-Compliance.

The data is then encrypted by the parties using the private key of the signature as encryption password. The encrypted data bundle is hashed and published on the Bitcoin blockchain.

**Financial product issuers and sellers**

They will digitally sign the information about the security they are issuing / selling to the buyer, in our scenario a broker or financial advisor working in a larger firm, which we will call the "Agent". The information may include a prospectus, disclosure, risk assessment, statement of intentions, disclaimer, etc. The agents will then sign this data along with a statement of acknowledgement that the information was received and understood. The data is then encrypted by the parties using the private key of the signature as encryption password. The encrypted data bundle is hashed and published on the Bitcoin blockchain. It is then easy to prove that certain information was shared and acknowledged by specific parties at a specific time, and the evidence is tamper-evident (meaning that any tampering of the data or signatures is detected instantly).

The information may include a prospectus, disclosure, risk assessment, statement of intentions, disclaimer, etc. The agents will then sign this data along with a statement of acknowledgement that the information was received and understood. The data is then encrypted by the parties using the private key of the signature as encryption password. The encrypted data bundle is hashed and published on the Bitcoin blockchain.

## Keystamp Process

### Generation and issuance of cryptographic keys

1. The issuing authority generates a master seed and derives its master key using the Bitcoin BIP32 standard. It is from this key that all subsequent keys in the infrastructure are derived.

*The issuer of a master has a complete overview of all the keys that are subsequently derived. The issuer can re-create any of the keys derived by its subordinates, and as such has access to all the private keys in the key hierarchy*

2. The issuing authority generates (derives) child keys for its master key, which are assigned by the issuer to each of the “subordinates” in the hierarchy. These keys can be also conceived as "certificates". 

*We recomend to use "hardened" derivation for all the child keys. This way, individual keys or certificates can be exported validated without necessarily exposing other keys.*

![BIP32](https://github.com/existencelabs/keystamp-whitepaper/blob/FrancisPouliot-patch-1/BIP32.png)

3. The child keys are associated to a "FirmID" in an index or registry, which is the responsibility and prerogative of the issuer.

3. The subkeys are derived using the BIP32 standard, and the reference derivation path would be:




3. This means that anybody can independently verify that a certain firm has been accredited by the regulatory authority, as long as the firm is using the Keystamp protocol.


### Customization: the issuing authority could decide not to derive hardened keys, which means that all the certificate holders would be aware of each other and thus track each other’s transactions on the blockchain and be able to verify each other’s signatures.


4. Each institution (or person) such as an advisory firm derives extended public keys, again hardened or not, for each other subordinate, such as individual employees and advisors of an advisory firm.


5. Each advisor uses a new key, derived from his extended key, to cryptographically sign documents and compliance data.


### Compliance data consist of any data used to prove that certain compliance policies were followed. This includes KYC, due diligence, internal audits, release form, consent forms, contracts, etc.


6. Every time an advisor engages in the “know-your-customer” process, the advisor presents evidence of the KYC process, risk assessment, disclosures and all relevant data to the end-user. Examples include:
- Risk assessment forms
- Recorded video and audio 
- Email and chat exchanges
- Disclosures, declarations, fee tables

7. The end user provides his consent that he agrees that the information presented by the advisor accurately reflects the KYC and disclosure process that was completed by the advisor by either digitally signing, validating with phone sms verification or any other traditional remote KYC methods.

8. A data bundle including the compliance data as well as the end-user’s consent proof (signature or SMS validation log) is hashed using SHA-256.

9. The hash is signed by the private key of the person that wishes to prove that he has knowledge of the data.

10. The data is encrypted with that same private key, and is stored securely for the right keyholders to access.

11. The data can be stored in distributed storage networks such as IPFS, maidsafe, or secure cloud storage.

12. The signed hash is stored in the Bitcoin blockchain using OP_RETURN.

13. This proves that at the same time the compliance data, the user consent and the advisor’s signature of that data and consent existed at a certain point in time.

14. If a single byte of data is changed in the compliance data or the user consent proof, the hash will be modified unpredictably. By comparing the compliance hash of the original document on the blockchain with the compliance hash that is presented, we can immediately prove that they are the same (or not), and so that it existed at the time of the block in which it was included.

## Process and data flow

1. The issuing authority generates a master seed using the Bitcoin BIP32 standard. It is from this key that all subsequent keys in the infrastructure are derived. In our example, the regulator would be the issuing authority. This key can be made public by the issuer.

2. The issuing authority generates (derives) sub-keys for its master key, which are assigned by the issuer to each of the “subordinates” in the hierarchy. These keys can be conceived as "certificates". 


3. This means that anybody can independently verify that a certain firm has been accredited by the regulatory authority, as long as the firm is using the Keystamp protocol.


### Customization: the issuing authority could decide not to derive hardened keys, which means that all the certificate holders would be aware of each other and thus track each other’s transactions on the blockchain and be able to verify each other’s signatures.


4. Each institution (or person) such as an advisory firm derives extended public keys, again hardened or not, for each other subordinate, such as individual employees and advisors of an advisory firm.


5. Each advisor uses a new key, derived from his extended key, to cryptographically sign documents and compliance data.


### Compliance data consist of any data used to prove that certain compliance policies were followed. This includes KYC, due diligence, internal audits, release form, consent forms, contracts, etc.


6. Every time an advisor engages in the “know-your-customer” process, the advisor presents evidence of the KYC process, risk assessment, disclosures and all relevant data to the end-user. Examples include:
- Risk assessment forms
- Recorded video and audio 
- Email and chat exchanges
- Disclosures, declarations, fee tables

7. The end user provides his consent that he agrees that the information presented by the advisor accurately reflects the KYC and disclosure process that was completed by the advisor by either digitally signing, validating with phone sms verification or any other traditional remote KYC methods.

8. A data bundle including the compliance data as well as the end-user’s consent proof (signature or SMS validation log) is hashed using SHA-256.

9. The hash is signed by the private key of the person that wishes to prove that he has knowledge of the data.

10. The data is encrypted with that same private key, and is stored securely for the right keyholders to access.

11. The data can be stored in distributed storage networks such as IPFS, maidsafe, or secure cloud storage.

12. The signed hash is stored in the Bitcoin blockchain using OP_RETURN.

13. This proves that at the same time the compliance data, the user consent and the advisor’s signature of that data and consent existed at a certain point in time.

14. If a single byte of data is changed in the compliance data or the user consent proof, the hash will be modified unpredictably. By comparing the compliance hash of the original document on the blockchain with the compliance hash that is presented, we can immediately prove that they are the same (or not), and so that it existed at the time of the block in which it was included.

### Design and architecture

The first step is to select the cryptographic functions that will be used in the Keystamp standard process. 

- Key generation: creating the certificate issuer's key (the master key)
- Key derivation: issuer creating subkeys for "subordonnates" in the key hierarchy

An application or system implementing the Keystamp process

### Crypto and blockchain

- Key generation using [Bitcoin BIP32 standard](https://github.com/bitcoin/bips/blob/master/bip-0032.mediawiki)
- Key derivation for issuing subkeys or certificates
- Hashing of data using cryptographic hash function [SHA-256](https://en.wikipedia.org/wiki/SHA-2)
- Signing of hashes (or of any data) using Elliptic Curve Digital Signature Algorithm (ECDSA)
- Notarize text to the Bitcoin blockchain using the OP_Return 
1. Creation of a Bitcoin transaction with the KEYSTAMP prefix and the hash of the data to notarize
2. Broadcast the transation to include the transaction, with our proofs (signatures, data), into the Bitcoin blockchain forever.
- A validation library which consists of
1. Retrieving a hash from a txid
2. Verifiying if a file (file URL) has the same hash

### Cryptographically-enforced permissions



We use BIP32 Bitcoin key architecture for cryptographically-enforced access permissions. The issuing authority generates a master private key which it uses to perform digital signatures. It derives sub-keys (hardened keys) that the authority can assign at will. That authority can also to the same, and assign keys at a lower level.


# Our innovations


## Hierarchical encryption and access control


We use private keys not only for signing data but also as encryption passwords for storing data. This means that when the lower sub-keys encrypt data, all the levels above can decrypt it. It’s a one way function. As such, only the issuing authority has access to all the data, and permissions are hierarchical, perfect for institutions such as financial regulators.


## Decentralized and trustless


The same private keys can be used to issue or receive any blockchain asset, from securities to obligations, gift cards, vouchers, etc. When those innovations become mainstream, the validation of transactions will be trustless perfectly synced with cryptographic identities.


All of these cryptographic identities can be linked to legal identities in a centralized government or institutional database. It is possible to use distributed storage networks like IPFS  to store data.That database acts as a reference index for pseudonymous keys.


## Timestamping


To prove that data existed at a certain time, we can hash the data, leaving a tiny fingerprint. That fingerprint is then signed by the holder of a key, along with a message providing context. If the key is associated to a legal identity, this is irrefutable proof that a person or organization said something or had some information.

##Technology stack

### Bitcoin blockchain thermodynamics

One of the main benefits of the blockchain is that it can provide independently auditable cryptographic proof that a certain set of data existed at a specific period in time. Because of the blockchain proof-of-work algorithm, data embedded in the blockchain is entirely immutable.This is what is referred to as “notarization”. The reason why this is useful is because of the work produced by the miners


We leverage the public key encryption algorithms on which the identity system of the Bitcoin blockchain is built, as well as the immutable and trustless nature of blockchain timestamps. 



In addition, public key encryption makes possible irrefutable digital signatures. By combining the two, we can prove that a set of data was “signed” by a person or organisation at a certain point in time. We can leverage those technologies in the context of compliance to increase trans



### Implementation

- [ An API for all the crypto functions](https://github.com/shayanb/keystamp-crypto)
- Abstraction layer for complex cryptographic libraries (ease of integration)
- Gateway connection to blockchain P2P network through full nodes
- Public key infrascture application
- Policies for generating and issuing keys
- Registry (centralized or decentralized) for associating keys to legal identity
- Traditional KYC methods for assessing user identity online 
- A graphical interface for internal and regulatory compliance showoing the map of all key trees








## Significance and innovation 


Keystamp if the first project to leverage the BIP32 key architecture of Bitcoin, invented by Gregory Maxwell, the CTO of Blockstream, not only for cryptographic signatures or the issuance of cryptographic certificates but also for cryptographically enforced access permission to certain data. This access takes the form of a novel use of BIP32 to achieved hierarchical public key encryption for messages. We achieve this by using the private keys as encryption passwords.


Since the higher level keys can derive the keys of the lower level keys:


- The regulator can decrypt all the data
- The firm can decrypt the data of all its subordinates
- Subordinates can encrypt data for reporting purposes





## Process and data flow

1. The issuing authority generates a master seed using the Bitcoin BIP32 standard. It is from this key that all subsequent keys in the infrastructure are derived. In our example, the regulator would be the issuing authority. This key can be made public by the issuer.

2. The issuing authority generates (derives) sub-keys for its master key, which are assigned by the issuer to each of the “subordinates” in the hierarchy. These keys can be conceived as "certificates". 


3. This means that anybody can independently verify that a certain firm has been accredited by the regulatory authority, as long as the firm is using the Keystamp protocol.


### Customization: the issuing authority could decide not to derive hardened keys, which means that all the certificate holders would be aware of each other and thus track each other’s transactions on the blockchain and be able to verify each other’s signatures.


4. Each institution (or person) such as an advisory firm derives extended public keys, again hardened or not, for each other subordinate, such as individual employees and advisors of an advisory firm.


5. Each advisor uses a new key, derived from his extended key, to cryptographically sign documents and compliance data.


### Compliance data consist of any data used to prove that certain compliance policies were followed. This includes KYC, due diligence, internal audits, release form, consent forms, contracts, etc.


6. Every time an advisor engages in the “know-your-customer” process, the advisor presents evidence of the KYC process, risk assessment, disclosures and all relevant data to the end-user. Examples include:
- Risk assessment forms
- Recorded video and audio 
- Email and chat exchanges
- Disclosures, declarations, fee tables

7. The end user provides his consent that he agrees that the information presented by the advisor accurately reflects the KYC and disclosure process that was completed by the advisor by either digitally signing, validating with phone sms verification or any other traditional remote KYC methods.

8. A data bundle including the compliance data as well as the end-user’s consent proof (signature or SMS validation log) is hashed using SHA-256.

9. The hash is signed by the private key of the person that wishes to prove that he has knowledge of the data.

10. The data is encrypted with that same private key, and is stored securely for the right keyholders to access.

11. The data can be stored in distributed storage networks such as IPFS, maidsafe, or secure cloud storage.

12. The signed hash is stored in the Bitcoin blockchain using OP_RETURN.

13. This proves that at the same time the compliance data, the user consent and the advisor’s signature of that data and consent existed at a certain point in time.

14. If a single byte of data is changed in the compliance data or the user consent proof, the hash will be modified unpredictably. By comparing the compliance hash of the original document on the blockchain with the compliance hash that is presented, we can immediately prove that they are the same (or not), and so that it existed at the time of the block in which it was included.

We return a blockchain receipt which includes
- The hash of compliance data
- The hash signature
- The advisor’s public key
- The blockchain txid
- Link to the encrypted original file

### Using the open-source tools we provide, anybody can verify the signatures and the timestamp thanks to the science of public key encryption and blockchain technology.

********************************************

## More Information and resources:

git: https://github.com/existencelabs/keystamp-client
git: https://github.com/existencelabs/keystamp-api


Fully Functional Backend API for Notarization and Validation of keystamps
git: https://github.com/shayanb/keystamp-crypto


whitepaper: https://github.com/existencelabs/keystamp-whitepaper.git


Contact
francis@existencelabs.com
phil@existencelabs.com
