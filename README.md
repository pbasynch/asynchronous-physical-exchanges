                                          Asynchronous Physical Exchanges
				                          p.b/Bitcoin.Talk.org/08mars2026
				                                   Introduction


Today, technologies based on blockchain make it possible to carry out digital exchanges without a trusted third party, relying on cryptography and decentralized systems such as Bitcoin.
However, as soon as an exchange involves a physical good, trust becomes necessary again because the digital world and the material world cannot be directly merged.
This document proposes a reflection around a conceptual process aimed at reducing certain risks related to asynchronous physical exchanges, that is to say exchanges of material goods between distant parties, not simultaneously present and not knowing each other, without claiming to resolve all existing issues.

1. Definition of the problem

1.1 General context

The exchange of physical goods at a distance is today largely facilitated by digital networks. However, when two parties do not know each other and are not present at the same time, these exchanges still rely largely on mechanisms of human trust, intermediation, or centralized institutions.

1.2 Asynchronism as the main source of risk

The fundamental problem appears when the exchange is not simultaneous. The buyer and the seller interact neither in the same place nor at the same moment. This absence of simultaneity creates an asymmetry of risk that cannot be eliminated by a simple agreement between the parties. Asynchronism transforms a simple exchange into a problem of coordination and trust.

1.3 Risk perceived by the seller

From the seller’s point of view, the main risk is to relinquish a physical good without a certain guarantee of receiving the corresponding payment. Once the object is shipped, the seller loses all control over it. In the absence of irreversible payment or a guarantee mechanism, the seller is exposed to a definitive loss.

1.4 Risk perceived by the buyer

From the buyer’s point of view, the risks are multiple. The first is to never receive the object after having made the payment. The second is to receive an object that does not correspond to the expected description. Finally, even in the case of effective reception, the buyer may fear that the object is defective, unusable, or altered, without having an immediate and objective means to prove it.

1.5 Limits of current solutions

The solutions currently used rely either on centralized institutions, or on platforms playing the role of a trusted intermediary. These approaches may reduce certain risks, but introduce other constraints: dependence on a third party, loss of anonymity, arbitrary procedures, delays, or asymmetry of power.

1.6 Boundary between the digital world and the physical world

The core of the problem lies in the difficulty of making the digital world and the physical world interact reliably. A payment can be verified cryptographically, but a physical object cannot be entirely digitized nor guaranteed by purely mathematical proof. There is no perfect cryptographic proof of the state of a physical object.

1.7 Framework and intention of the proposed process

The process described in the following sections does not claim to resolve all these issues. Its objective is more modest: to reduce certain asymmetries of risk during asynchronous physical exchanges, relying on observable physical data and on cryptographic mechanisms, while preserving the anonymity of the parties.
This process must be understood as a line of reflection and not as a definitive solution.

2. Conceptual framework

2.1 Actors, role of the process

Three main actors are considered:

A (Buyer): wishes to acquire a physical good without being present at the same moment and in the same place as the seller. A seeks to reduce the risk of paying without receiving.
V (Seller): wishes to sell a physical good without being present at the same moment and in the same place as the buyer. V seeks to reduce the risk of shipping without being paid.
L (Logistics): ensures the physical transport between two points. L is not considered as a trusted arbitral third party regarding the content of the exchange, but as an operator subject to operational constraints and potentially economic responsibility in the case of non‑delivery or anomaly detected upon arrival.
The process relies on a deposit/withdrawal infrastructure (lockers) allowing observable physical characteristics to be recorded during deposit and compared upon reception.

3. Overview of the process

3.1 General principle

This section presents an overall view of the sequence of an asynchronous physical exchange as envisaged by the proposed process. The objective is to describe the general sequence of events, without yet going into the specific technical details.
The process relies on two distinct but complementary layers:

· A settlement layer (Layer A), ensured by a truly decentralized and censorship-resistant blockchain, such as Bitcoin (BTC), used exclusively for irreversible payments.

· A state and coordination layer (Layer B), ensured by a distributed cryptographic infrastructure linked to physical lockers, making it possible to manage deposits, validations, delays and withdrawals, while preserving the anonymity of the parties.

3.2 Initiation of the exchange

An exchange begins when a buyer (A) and a seller (V) agree on the sale of a physical good, without being simultaneously present and without knowing each other. This agreement is carried out via a software interface (for example an application or a dedicated service), closely linked to the infrastructure of Layer B, in order to guarantee consistency between the digital exchange and the physical lockers.

At this stage:

-No payment is made.

-No object is transferred.

An exchange identifier is created, serving as a common cryptographic reference between the buyer, the seller and the object concerned, without revealing their civil identities.

3.3 Deposit of the object by the seller

The seller goes to a physical locker assigned to them by the system.
During the deposit:
1. A deposit session is opened using the exchange identifier.
2. The seller places the object in the locker.
3. The locker automatically records observable physical characteristics.
4. These data are cryptographically associated with the session and broadcast via Layer B.

The locker then locks in a non-final state (“red” state):

· The object is immobilized.

· No payment is triggered.

· The seller retains the possibility of recovering their good in the event of refusal or expiration.

A cryptographic signature by the seller is required only in the event of recovery of the object, in order to prove that the depositor is indeed the legitimate entity associated with the exchange session and to prevent any attempt at impersonation or fraudulent recovery.

3.4 Transmission and analysis by the buyer

The physical data recorded during the deposit are transmitted to the buyer via Layer B.

The buyer may then:

· Examine these data.

· Compare them with what they expect to receive.

· Decide to accept or refuse the exchange.

A maximum time limit is deliberately introduced in order to avoid any hostage-taking of the process by one of the parties.

3.5 Validation by the buyer and definitive locking

When opening the exchange session in the state layer (layer B), the seller registers the public Bitcoin address to which the payment is to be sent. 

After examining and accepting the physical characteristics observed at the time of deposit, the buyer proceeds with payment on the settlement layer (layer A) by sending the agreed amount to this address. Once the transaction has been broadcast on the Bitcoin network, the buyer sends the corresponding transaction ID to layer B. 

This identifier allows layer B to publicly verify, by consulting the Bitcoin blockchain ledger, the existence of the payment and its correspondence with the address registered by the seller and the amount expected for the exchange.

Once this proof of payment has been verified in layer B, the deposit locker changes to a final state, preventing the seller from retrieving the item. 

Throughout this phase, the locker remains locked in a non-final state for a predefined period, ensuring that the seller cannot retrieve the item while the buyer is verifying and paying.

So:

· The creation and broadcast of a payment transaction on Layer A (Bitcoin blockchain).

· The transition of the locker to a definitive state (“green” state).

· The impossibility for the seller to recover the object because the buyer’s payment transaction is triggered.

The buyer’s signature therefore irreversibly links:

· The payment.

· The physical locking.

· The finalization of the exchange.

3.6 Refusal or expiration

If the buyer explicitly refuses the exchange, or if the validation period expires without action:

· No payment is triggered.

· The locker remains in a non-final state.

· The seller may return to recover their object.

The recovery is carried out by means of a cryptographic proof issued from Layer B, linked to the initial exchange session and verified locally by the locker infrastructure. This proof makes it possible to authorize the opening of the locker without identity disclosure, while guaranteeing that only the legitimate depositor may recover the object.

3.7 Logistics intervention

Once the locker is definitively locked following the buyer’s validation, the object becomes eligible for logistical handling. From that moment, the exchange between the buyer and the seller is considered finalized from a financial standpoint, the payment having been triggered on the settlement layer.
At the time of handling, the object is removed from the deposit locker by the logistics operator, who at that moment creates a cryptographic commitment, and is then transported to the planned reception location. It is important to note that, within the framework of this process, the object is supposed to be transported without any possible modification of its state, this state having been immobilized during the initial deposit by the seller and validated by the buyer on the basis of observable physical characteristics.
Upon arrival, the object is deposited in a reception locker. This locker then performs a new acquisition of observable physical characteristics and compares them with the data recorded during the initial deposit and already accepted by the buyer.
Any significant divergence between the characteristics measured upon reception and those recorded during the initial deposit indicates that the state of the object has been modified during logistical handling, even though it was supposed to remain unchanged since its initial immobilization. In this case, the deposit may be automatically refused by the system.
This verification requires no additional validation by the seller or the buyer, since they have already accepted the characteristics of the object at the moment of the initial deposit. In the event of conformity, the deposit is accepted, the locker moves to a valid state and the object becomes recoverable by the buyer.
In the event of non-delivery, deadlines being exceeded, or non-conformity detected upon reception, logistics may be held economically liable, according to automated settlement mechanisms relying on the settlement layer based on a decentralized public blockchain such as Bitcoin. This liability is intended to guarantee the integrity of the process without introducing an arbitral third party or calling into question the anonymity of the parties.
The access of logistics operators to the lockers is not based on general authority, but on temporary cryptographic capabilities issued by the coordination layer, strictly limited in time, space and purpose.

3.8 Recovery of the object by the buyer

Once the object has been delivered and validated by the reception locker, it becomes recoverable by the buyer. At this stage, the exchange is considered finalized from both a financial and logistical standpoint: the payment has already been triggered during the initial validation by the buyer, and the object has been transported without modification of its state.
Recovery by the buyer is carried out via a cryptographic proof linked to the exchange identifier and managed by the state and coordination layer (Layer B). This proof allows the buyer to open the corresponding reception locker, without revealing their civil identity or interacting with logistics or the seller.
During recovery, no new validation is required. The physical characteristics of the object having already been verified upon reception by the locker and compared with the data recorded during the initial deposit, the system considers the object to be compliant. The locker then moves to a single open state allowing the buyer to remove the object, and then closes definitively.
Once the object has been recovered, the exchange session is closed. No subsequent action is possible on this exchange via the infrastructure, which guarantees the finality of the process and prevents any reversibility or late dispute.

4. Conceptual Technical Architecture

4.1 Separation of responsibilities of complementary layers

The process relies on an explicit separation between two complementary technical layers, each having a distinct and non‑substitutable role.

Layer A corresponds to the monetary settlement layer. It relies on a truly decentralized public blockchain, resistant to censorship and based on strict consensus rules, such as Bitcoin. This layer is used exclusively for irreversible payments and the economic commitments associated with the different stages of the process.

Layer B corresponds to a distributed cryptographic infrastructure responsible for the coordination of physical states. It is linked to physical lockers and allows the recording, broadcasting and comparison of observable physical characteristics associated with exchanged objects. This layer manages no transfer of monetary value and does not interpret the nature of exchanges; it is limited to state management and the attestation of observable material facts.

This separation aims to avoid any confusion between cryptographic proof and material reality. Layer A guarantees economic irreversibility, while Layer B provides a coordination framework allowing physical events to be linked to cryptographic commitments without introducing an arbitral third party.

4.2 Settlement layer: economic commitments and irreversible payments

Layer A of settlement ensures all economic commitments of the process through mechanisms already existing within the Bitcoin protocol, notably conditional transactions and time locks.

Logistics commitment:

When the object is taken in charge by logistics, the operator produces an explicit cryptographic commitment on Layer A. This commitment takes the form of a conditional transaction locked by a time constraint.

Concretely, a predefined amount is committed such that:

• if no success condition is fulfilled before the deadline

• then the transaction automatically becomes executable in favor of the buyer.

This mechanism requires no later decision or human intervention: the time expiration itself constitutes a sufficient condition.

Case of non‑delivery or delay:

If logistics does not deposit the object in a reception locker within the allotted time, no additional action is required.
The simple passage of time releases the time lock, making the transaction executable according to the predefined rules. The reimbursement of the buyer is then triggered automatically by Layer A.

Case of physical non‑conformity:

Upon arrival, the reception locker performs a new acquisition of observable physical characteristics of the object. These data are compared to the characteristics recorded during the initial deposit and explicitly validated by the buyer at that moment.

It is fundamental to emphasize that:

• the locker does not decide the conformity of the object

• it interprets no rule

• it resolves no dispute

It strictly limits itself to a mechanical comparison between two sets of data:

• the physical data accepted by the buyer during the initial deposit

• the physical data observed at reception

If the sets do not correspond, the object is considered non‑conforming according to the criteria already validated by the buyer. The locker merely attests this divergence.
In this case, no direct signal is sent to the settlement blockchain. Since the object is refused, no success condition is fulfilled, and the time mechanism initiated by logistics simply continues until expiration. At the end of the delay, the conditional transaction becomes executable, triggering the automatic reimbursement of the buyer.

Case of success and cancellation of the time lock:

In the case of conformity, the object is accepted by the reception locker based on the data validated ex ante by the buyer. This acceptance results in the revelation of a cryptographic secret previously committed, allowing the cryptographic condition that invalidates the penalizing branch of the conditional transaction engaged by logistics to be satisfied.

This mechanism relies on classical hashlock / timelock constructions:

• the revelation of the secret prevents execution of the reimbursement

• the economic commitment of logistics is then considered fulfilled

This is not a decision oracle, but simply the lifting of a cryptographic condition defined from the beginning.
Absence of trusted third party:

At no moment does Layer B impose a decision on Layer A. It merely attests observable material facts and reveals, or not, cryptographic elements defined in advance. Economic rules are entirely defined at the initial commitment, and their execution relies exclusively on the protocol of the settlement blockchain.

Thus the process does not rely on a trusted third party, but on:

• irreversible economic commitments

• objective temporal constraints

4.3 Distributed physical state infrastructure layer

Layer B constitutes a distributed cryptographic infrastructure responsible for representing, recording and comparing observable physical states associated with material objects. It does not constitute a monetary blockchain but a registry of verifiable physical states whose function is to coordinate interactions between the material world and the cryptographic system.
Its role is not to issue judgments nor to take arbitrary decisions, but only to observe, record and compare measured observations.

The Layer B registry is of the append‑only type:
data can be added to it but never modified or deleted.

This property guarantees:

• the historical integrity of records.

• the impossibility of retroactively falsifying a measurement.

• the public verifiability of past states.

Each recorded state therefore becomes an immutable timestamped proof.

When an exchange is initiated, the system generates a unique cryptographic identifier. This identifier is derived from parameters such as:

• the public keys of the parties.

• a random uniqueness factor.

• a timestamp.

This identifier reveals no personal information but makes it possible to associate with certainty:

• a seller.

• a buyer.

• an object.

• an exchange session.

It constitutes the common reference for the entire process.

Layer B relies on a distributed network of independent nodes that may be operated by different actors such as:

• locker manufacturers.

• logistics operators.

• technical institutions.

• independent operators / individuals.

Each node holds a copy of the registry and participates in the validation of new states.

The role of a node is strictly defined:

• verify the cryptographic validity of entries.

• verify temporal consistency.

• record new observations.

• refuse any modification of a past state.

No node possesses privileged authority.
Each user of the system possesses a personal cryptographic key allowing them to interact with the infrastructure regardless of their role. The same individual may therefore act successively as buyer or seller without changing cryptographic identity.
Logistics operators possess distinct professional keys used only to sign their transport commitments.

These keys may be stored on secure hardware supports such as:

• cryptographic cards.

• secure modules.

This approach avoids any dependence on a personal device or on centralized infrastructure.

During the initial deposit of an object, the locker automatically performs a multi‑source acquisition of observable physical characteristics. Depending on the available equipment, these measurements may include:

• mass.

• external dimensions.

• volume.

• optical imaging.

• internal imaging (tomography or X‑rays).

• material signatures.

• density distribution.

These data do not constitute a subjective visual description but a set of objective quantitative measurements.
The collected measurements are transformed into a standardized digital representation and then condensed into a unique cryptographic fingerprint.
This fingerprint constitutes a physical identifier mathematically derived from the measured properties of the object. It does not allow the object to be reconstructed but makes it possible to verify whether two observations correspond to the same physical state.
The data measured during the deposit are transmitted to the buyer via Layer B. The buyer examines this information and decides whether to accept or reject it.
Acceptance means that the buyer recognizes that the recorded physical fingerprint corresponds to the expected object. This validation becomes the reference for comparison for all future verifications.
From this moment onward, Layer B never interprets the data: it only compares subsequent measurements with this accepted reference.
During delivery, the destination locker performs a new complete acquisition of physical characteristics according to the same process used during the initial deposit.

A mathematical comparison is then performed between:

• the fingerprint recorded at deposit.

• the fingerprint measured at reception.

Only two outcomes are possible:

• match: the physical state is identical.

• mismatch: the state has been modified.

The system produces no judgment: it only observes equality or inequality of the fingerprints.
The locker is not a trusted third party, an arbitrator, or a decision authority.

It performs only three functions:

• measure.

• compare.

• attest the result.

The logical outcome results exclusively from the mathematical comparison between the initial fingerprint validated by the buyer and the fingerprint measured at reception.
The locker does not interpret the results: it mechanically applies the predefined rule.
Layer B does not claim to demonstrate the internal functioning of an object nor its functional state. It only makes it possible to attest whether a received physical object corresponds or does not correspond to the physical state observed during the initial deposit.
It therefore constitutes a risk‑reduction mechanism, not an absolute proof.

4.4 Distributed validation of Layer B states

The validity of a state recorded in Layer B does not depend on any central authority nor on a single actor. It relies on a distributed validation mechanism ensured by the network of independent nodes maintaining the registry.

When a new event is produced — session creation, measured deposit, buyer validation, logistics pickup, reception measurement — this event is broadcast to the network in the form of a cryptographically signed entry. Each node then independently verifies:

• the validity of signatures.

• the temporal consistency of the event.

• conformity to the expected format.

• compatibility with the previously recorded state.

An event is accepted into the registry only if it satisfies all of these conditions. Otherwise, it is locally rejected by the nodes.
Nodes never validate physical reality itself. They do not verify the object, perform no measurements, and do not judge the results. Their role consists exclusively of validating the cryptographic and logical consistency of the statements produced by measurement devices. In other words, they validate proofs of observation, not the observation itself.
The consensus of Layer B therefore concerns only the order and authenticity of recorded states, not the interpretation of material reality. This distinction ensures that the infrastructure remains a distributed verification system and not a decision‑making mechanism.

When a valid event is accepted by the network, it is added to the append‑only registry and becomes an immutable reference. The more a state is replicated and confirmed by nodes, the stronger its finality becomes. After a certain number of confirmations, a state is considered stable and can no longer be contested without invalidating the entire subsequent history.
This model makes it possible to obtain an essential property:
no isolated actor — neither a node, nor an operator, nor a locker manufacturer — can modify, delete or falsify a recorded state.
Trust therefore does not rely on a participant, but on the distributed structure of the system itself.

5. System resilience and security limits

The security of Layer B relies on a combination of cryptographic guarantees and physical constraints. Unlike purely digital distributed systems, the initial state recorded in Layer B is not an abstract data generated by computation, but the result of a measurable material observation performed by a physical device.
Each state record corresponds to a real event that occurred in the physical world. This property introduces a fundamental constraint: the falsification of a valid state requires an effective material interaction with the infrastructure, and cannot be obtained solely through software manipulation of the network.

5.1 Resistance to identity attacks (Sybil)

In a classical distributed system, an attacker may attempt to take control of the network by multiplying identities. This type of attack aims to influence consensus or the recording of data.

In Layer B, the creation of additional network identities does not make it possible to fabricate false physical states, because:

• measurements are produced by real hardware devices.

• each observation is locally signed by a cryptographic module.

• recorded states are immutable and publicly verifiable.

Thus, multiplying nodes does not make it possible to generate false physical proofs. At most it can disturb the propagation or availability of data, but it cannot retroactively alter a state already validated.

5.2 Physical anchoring of proofs

The fundamental property ensuring the robustness of the system is the physical anchoring of states.
A state is accepted by the network only if it corresponds to a measured and signed observation. The very existence of this state therefore implies that a material event has actually occurred.

This constraint introduces an irreducible real cost for any attempt at falsification, since an attacker would have to compromise:

• a measurement device.

• a hardware cryptographic module.

• or the physical infrastructure itself.

Security therefore does not rely only on a majority of honest nodes, but also on the practical difficulty of reproducing or falsifying a measurable physical event.

5.3 Inherent limits of the model

Layer B does not claim to prevent all attacks. It does not eliminate:

• attempts of network censorship.

• propagation delays.

• attacks on hardware infrastructure.

• physical or technical failures.

It also does not guarantee the internal functioning of an object, but only the measurable correspondence between two observed physical states at distinct moments.
The system therefore constitutes a mechanism of risk reduction, not a mechanism of absolute certainty.

5.4 Separation between physical truth and network consensus

The role of the network is not to determine physical reality, but to record in an immutable way the observations produced.

In other words:

• material reality is established by measurement.

• the network merely attests that this measurement has taken place.

This separation prevents distributed consensus from becoming an arbitrary authority over the state of an object. Nodes do not decide the validity of a physical state; they only verify that this state has been correctly produced and signed.

5.5 Emergent property: hybrid security

The resulting architecture possesses a particular property: it combines two distinct and complementary sources of security:

• mathematical security (cryptography, signatures, immutability)

• physical security (material cost, real constraints, irreversibility of events)

This hybridization makes purely digital attacks insufficient to compromise the system as a whole.

6. Scope, implications and positioning of the model

6.1 Decentralized nature of the process

The proposed model relies on a distributed architecture in which no single entity holds a global decision‑making power.
Layer A relies on a decentralized monetary protocol.
Layer B relies on a distributed registry whose states are validated collectively by independent nodes.
Physical devices measure, nodes record, actors sign.
No central authority interprets, arbitrates or validates on behalf of others.

The process therefore does not rely on trust in an institution, but on:

• cryptographic verifiability.

• immutability of records.

• measurable physical constraint.

• strict separation of responsibilities.

6.2 Conceptual scope

This document describes a theoretical model aimed at structuring asynchronous physical exchanges without dependence on a central arbitral third party.

It proposes an architecture in which:

• value is settled on a decentralized monetary infrastructure.

• physical state is attested through measured observations.

• the coherence of events is ensured by a distributed registry.

This is not a product nor an existing implementation, but a conceptual framework open to discussion, experimentation and improvement.

6.3 Potential domains of application

The model could apply to any situation involving:

• an exchange deferred in time.

• an absence of prior trust.

• a need for objective verifiability of a material state.

This potentially includes:

• peer‑to‑peer exchanges.

• logistics with conditional liability.

• transport of sensitive objects.

• distributed supply chains.

These applications do not constitute an imposed objective but possible illustrations.

6.4 Practical limits and implementation constraints

Such a system would require:

• the deployment of specialized hardware infrastructures.

• the integration of reliable measurement devices.

• technical standardization.

• coordination between operators.
These constraints relate to industrial and economic considerations, not to the logical coherence of the model.

6.5 Assumed structural limits

The model does not claim to:

• eliminate all risk.

• prevent all fraud.

• nor replace existing legal frameworks.

It does not demonstrate the intrinsic nature of an object nor its internal functioning.
It only attests the measurable correspondence between two observed physical states.
It therefore constitutes a mechanism of uncertainty reduction, not an absolute guarantee.

6.6 Intellectual positioning

This document should be understood as:

• an architectural exploration.

• a technical proposal.

• an open framework for reflection.

It describes a structural possibility.

The problem of exchanges of physical goods associated with cryptographic mechanisms has already been the subject of various works and proposals. However, to my knowledge, although I have not had the time nor the opportunity to examine all existing works, the approaches I have seen do not propose the architectural combination presented here.
