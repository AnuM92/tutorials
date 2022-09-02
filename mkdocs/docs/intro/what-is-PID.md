# Polygon ID: An Introduction

Based on the principles of Self-Sovereign Identity (SSI) and cryptography, Polygon ID a decentralised and permissionless identity management system for web 2 and web 3 applications.The SSI framework  lets the identity holders own and control their identities unlike the other frameworks where ID are issued and controlled by a single person or central authority. 

Polygon ID or PID, with the help of zero-knowledge proofs, lets users prove their idenity without the need of exposing their private information. This ensures both the **Freedom of Expression** to anyone (who intends to use Polygon ID solution) and **Privacy by Default** (User's identities are secured by the zero-knowldege technology).

## What Constitutes Polygon ID?

Polygon ID platform is based on several building blocks that are inherenet to its successful execution. Following is the list of what all constitutes the SSI-based POlygon ID solution:

- Verifiable Credential(VC)
- Identity Holder, Issure, and Verifier (together they form a triangle of trust so that the communication between the three players is seamless)
- Decentralized Identity (DID)
- Digital Wallet

Let us go through these one by one in the sections to come.

### Verifiable Credentials (VC)
A credential is a claim about an entity; an entity presents a claim either about itself or about some other entity. In the simplest terms, a credential resresents  any type of information related to an individual/enterprise/object. The credential could be as simple as the age of the entity or highest degreee hold by it. It could be  membership certifcate issued by a DAO. The claims are issued by a trusted authority called issuer.  The entity that keeps the issued credentails in its wallet is called Identity Holder.  

A Verifiable Credential means that the claim must be verifed by another trusted entity called Verifier, i.e. a Verifier must be able to verify that the claim is genuine and has not been tampered with. You would read more about a Verifier in the sections to come. You will learn about Identity Holder, Issuer and Verifier in the section on `Tringle of Trust`. 

**Structure of a Verifiable Credential**
 A credential is stored in the form of JSON-LD format. 
 ***Note***: JSON-LD  stands for JSON Linked Data. The Linked Data is used for publishing data on a website in a format that can easily be used by the other websites. 

 The structure of a VC can be broadly divided into:
 - Id: It represents the unique identifier of the credential.
 - credentialSubject: It is the core content of the credential. For example, a credentail can attest that an ind=dividual identified by  **id** `113TCVw5KMeMp99Qdvub9Mssfz7krL9jWNvbdB7Fd2` has his/her **birthday** on 1996-04-24.
 -credentialSchema: It identifies the schema or the data structure that the credential must follow. To achieve credential portability, it is important to use the schema consistently to represent the same type of information.
 -proof: It is a cryptographic proof that the credentials was issued by a specific issuer. 

### Identity Holder, Issuer and Verifier (Triangle of Trust)

The Identity Holder, Issuer, and Verifier together form what we call a `trianlge of trust`. 

1. **Identity Holder**: An entity that holds the Verifiable Credentails in its wallet. The VCs, as mentioned above, are issued by an Issuer to the Holder. The Identity/wallet holder creates the zero-knowledge proofs of the claims issued and presents these proofs to the Verifie (that verifies the correctness and authenticity of the claim). An identity Holder can create proofs for more than one VC. A Holder is also called Prover as it needs to prove to the Verifier that the credential it holds is authentic. 

2. **Issuer**: An entity (person, orgainzation, or thing) that issues the Verifiable Credentials to the Holders. The VCs are cryptographically signed by the Issuer. Every Verifiable Credential comes from an Issuer. 

3. **Verifier**: A Verifier verifies the claims presented by a Holder. It requests the Holder to send proof of the claim issued from an Issuer and on receiving the zero-knowledge proofs from Holder, verifies it. The verification process includes checking the veracity of teh signature of the Issuer. The simplest real-world examples of a Verifies can be a recruiter that verifies your educational background or a voting platform that verifies your age. 

**Checks Made by a Verifier**

A Verifier, during the process of credential verification, needs to perform the following checks:

- Who is the Issuer of the credential
- The subject that holds the credential is indded the owner of that credential
- Post issuance of the credential by the Issuer, the credential has not been tampered with
- Credential has not expired or revoked. 
 

### Decentralized Identifiers (DID)

A DID is a unique identifier with the help of which an entity can prove that it is the owner of that identifier. This is proved using cryptographic techniques that are based on use of private-public key pairs. A Verifier can check the authenticity of the zero-knowledge proof presented by Identity Holder in this way: The owner of the private key (i.e. Identity Holder) uses this key to sign a content or signture. The Verifier can verify that  the signature was performed by the Identity Holder using the corresponding public key. 

Issuers use the private keys to sign the content it issues to the Holder. Using this signature along with the credential that it has received form that Issuer, Identity Holder can prove that teh credential is authentic. 

In the world of Verifiable Identoties, we require:

- A subject must have a private key
- That subject to be iodentified with the public key associated with that subject
- A public registry (blockchain) where anyone can lookup the public key of the subject. 

In context of Polygon ID, this transaltes to:

- A subject holding the Baby Jubjub  provate key
- The subject is identified with an ID that is detereministcally derived from subject's private key
-Polygon chain is used as a public registry  to register IDs

**Note**: A DID identifies an identity or a DID subject (person, organization, or thing). The data realted to a DID subject is defined in a DID document, which also defines the emchanisms by which a DID subject can prove its identity using public keys.  

### Digital Wallets

Digital wallets are used by the Identity Holders to store their credentials. Every wallet is supported by a digital agent that forms a decnetralised and secure peer-to-peer connection with other digital agents. This connection set up by digittal agents lets Identuty Holders credentails stored in their wallets. 

## Features of Polygon ID

1. **Privacy using Zero-Knowledge Proofs** An Identity Holder, using zero-knowldeg proofs, remains provy to his/her personal data. Dusring the process of claim verification , s/he just needs to show that he is the owner of that claim without letting teh Verifier know of teh actual claim. For example, IDentity Holder can prove to a Verifier authority that s/he is above 18 years of age by presenting the proof that s/he is above 18 without revelaing his/her actual age. This ensures minimum data exposure and g=hence ensures safety of sensitive data. 
Another aspect of privacy comes from the fact that Issuer would not be able to track  an individual's credential once it has been issued. 
2. **On-Chain Verification**: Verification of proofs is done via Smart Contracts (software that run on blokchain after certain conditions are met). 
3. **Universal Identity**: Polygon ID provides a scalable model for open and permissionless identities in addition to providing low-cost claims. 

4. **Self-Soveriegnity**: POlygon ID renders self-sovereignity in the hands of the user. The user is the only custodian of his/her private keys; user-controlled data can be controlled with third parties without taking any permission from the Isuuer that has issued the credentail to the user. This is possible due to the use of undeerlying cryptography protocol for verifying data. 

5. **Transitive Trust**: A transitive trust between the players of an SSI system (Holder, Issuer, and Verifier) means that the trust between two entities in one domain or context can be easily extended to other domains or contexts. For instance, the information generated by an Issuer can be conveniemtly used by more than one Verifier. On the similar lines, an Identity Hodler can  can built up his/her trust by collecting multiple credentials from different Issuers in one digital wallet. In terms of Polygon ID, this clearly means that data shared will no longer be a thing for competitive moat to be used by centralized authorities. 




