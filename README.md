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


We propose an new open-source standard, Keystamp, which allows financial services participants to prove irrefutably the actions they took and knowledge they had at a specific point in time. Specifically, we design an innovative set of policies and procedures for using existing blockchain technologies, protocols and public-key encryption concepts to be integrated in traditional workflows and business relationships.

such as the authentification of parties and the notarization and validation of data such as compliance documentsproofs-of-knowledge (such as disclosures), statements of intentions (oaths) and contracts, activities or events logs, auditing the integrity of the data supplied. 

T provides an digital trail of unforegable signatures, immutable timestamps and encrypted contextual data that can be used to prove the participants' compliance to  external and internal requirements such as legislation, rules, guidelines, standards, codes, policies, procedures and controls.

Keystamp is the reference implementation of the "Proof-of-compliance" 

It also allows participants to cryptographically prove their identity in a private way by signing messages with their private keys. Private keys can used as encryption passwords for data. Since we use Bitcoin as the cryptography and blockchain platform, all the keys used in Keystamp can not only send and receive funds via Bitcoin but also issue and transfer blockchain-based assets representing any security or property title using Metaprotocols on the Bitcoin blockchain.





A Keybase implementation consists of a complete cryptographic key management infrastructure and allows for the seamless integration of blockchain technology in an easy-to-use workflow. A functional API can integrate easily in any existing traditional workflow, with graphical easy-to-use tools to foster implementation. Since Keystamp aims to be a standard, adoption needs to be implemented voluntarily by a large number of firms in the economy to be successful.

### Implementation

We specifically implement the Proof-of-Compliance use-case of Keystamp in the context of “know-your-customer” policies, or any other context where establishing that information was obtained by certain parties at a certain time is required. Proof-of-compliance provides a digital trail of unforgeable signatures and timestamps which consist of irrefutable evidence that someone had certain information, took action or participated in specific events at specific points in time.

It is intended to be used in the context of corporations, where heads of the hieararchy issue certificates to subordinates (and so on) that grant them the right to sign contracts, handle funds, issue other certificates, encrypt certain data, etc. Since issuance and revocation of contracts are enforced cryptographically and are publicly auditable, easy to authentificate and verify using graphical interfaces over complex cryptographic libraries, anybody can verify who they are talking to and where they derive their authority from in the context of a business relationship. It can be implemented by public bodies such as government and enforcement agencies, so as to limit fraud and foster public trust.

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

![Keystamp implementation](https://github.com/existencelabs/keystamp-whitepaper/blob/master/Keystamp%20Implementation%20resized.png)

## Technology

### Design and architecture

The first step is to select the cryptographic functions that will be used in the Keystamp standard process. 

- Key generation: creating the certificate issuer's key (the master key)
- Key derivation: issuer creating subkeys for "subordonnates" in the key hierarchy

An application or system implementing the Keystamp process


 
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

1. The issuing authority generates a master private key using the Bitcoin BIP32 standard. It is from this key that all subsequent keys in the infrastructure are derived. In our example, the regulator would be the issuing authority. This key can be made public by the issuer.

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

*********************************************

## More Information and resources:

git: https://github.com/existencelabs/keystamp-client
git: https://github.com/existencelabs/keystamp-api


Fully Functional Backend API for Notarization and Validation of keystamps
git: https://github.com/shayanb/keystamp-crypto


whitepaper: https://github.com/existencelabs/keystamp-whitepaper.git


Contact
francis@existencelabs.com
phil@existencelabs.com
