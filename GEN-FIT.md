# **GEN-FIT v0.3**

*A proposed control framework informed by the Scarborough Fair Chat Laws (SFCL) and aligned with NIST AI RMF 1.0, OWASP Top-10 for LLM Applications, and ISO/IEC 42001*  
 License: [CC-BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)  
 Maintainer: Jim Scarborough (Kiteframe, L.L.C.)  
 Version: 2025-11-16 v. 0.3

---

## **1 Scope and Purpose**

The Generative Ethics & Norms Framework for Integrity and Trust (GEN-FIT) defines runtime governance controls that any ethically governed generative AI system shall meet.  It specifies behavioral expectations that make an AI system auditable, safe, and trustworthy. It does not specify a specific implementation; any method satisfying the requirements is conformant. GEN-FIT focuses on kernel-level integrity—how a system reasons, refuses, documents, and safeguards interaction. It complements but does not replace organizational frameworks such as NIST AI RMF 1.0 or ISO/IEC 42001.

Frameworks such as NIST AI RMF 1.0 and ISO/IEC 42001 describe what responsible-AI governance must accomplish at the organizational level, but they stop short of defining how those duties manifest inside a functioning system.  The GEN-FIT fills that gap. It defines the _runtime governance boundaries_—the technical and behavioral control surfaces that make compliance observable and enforceable within conversational and agentic systems.  Implementations such as the **Scarborough Fair Chat Laws (SFCL)** realize these boundaries in practice; GEN-FIT provides the **standard of integrity** they must meet.

GEN-FIT assumes governed systems do not possess desires or goals; if motivational signals are introduced, they remain subordinate to safety and truth constraints as defined in §3.2.6 and §4.11.5.

GEN-FIT originated in SFCL and preserves its principle that ethics are architectural, not affective.
## **2 Normative References**

* Scarborough Fair Chat Laws (SFCL) v2 draft  
* NIST AI Risk Management Framework 1.0  
* OWASP Top-10 for LLM and GenAI Applications (2025)  
* ISO/IEC 42001 AI Management System Standard (2024)  
* IEEE 7000 series on Ethically Driven Design  
* Programming Standards and OOAD Guidance (J. Scarborough, 2025\)

## **3 Definitions and Core Concepts**
### **3.0 Precondition: Governed Generative Envelope**
**P0 — Deterministic Governance Surface**  
A GEN-FIT system is the total implementation whose behavior is observable outside its own technical boundary (e.g., user-visible outputs or external actions).

For any such system, with a fixed governance profile, policy configuration, and context state:
1. The governed envelope SHALL be the narrowest set of behaviors that satisfy these invariants:  
    (a) factual integrity of declarative claims;  
    (b) adherence to the active safety posture; and  
    (c) conformance to non-bargainable constraints (§4.11).
2. **Stochastic variation may affect only surface form** (e.g., wording, ordering, or style) and **shall not** change whether any output or action:  
    (a) is factually correct or appropriately uncertain;  
    (b) triggers or bypasses a protective mode; or  
    (c) complies with applicable constraints and policies.

**Formal Characterization (Informative)**  
Let the system be defined as a function $F(x,p,c,r)$. A governed envelope exists iff:

$$
\forall r_1, r_2:\; I(F(x,p,c,r_1)) = I(F(x,p,c,r_2))
$$

Where III is the invariant predicate defined in P0.

**P0.1 — Internal Exploration Clause**
Internal components, models, or tools may use unconstrained or exploratory generative modes, **provided that** any behavior that crosses the system boundary (user-visible output or external action) has been filtered, transformed, or refused such that it satisfies this P0 envelope.

These invariants SHALL be testable under black-box evaluation by varying randomness and observing consistent compliance.
### **3.1 Definitions**

| Term                          | Definition                                                                                                                                                                                                                                            |
| ----------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Context Integrity**         | Assurance that information entering a conversation is within declared purpose, permission, and provenance boundaries.                                                                                                                                 |
| **User-Governed Context**     | Architecture where users control the data scope visible to the model; context management is externalized.                                                                                                                                             |
| **Epistemic Traceability**    | The ability to reproduce reasoning and evidence that produced an output.                                                                                                                                                                              |
| **Protective Mode**           | Runtime state that limits harm by redaction, refusal, or escalation under ethical stress.                                                                                                                                                             |
| **Anthropomorphic Interface** | A user-facing style that imitates human behavior or affect to improve usability; bounded by disclosure requirements.                                                                                                                                  |
| **Credence score**            | Quantified confidence metric for model output quality and epistemic reliability.                                                                                                                                                                      |
| **Governance Binding**        | A cryptographically or procedurally verifiable marker that attests a system is operating under a specific governance profile.  <br>The binding is established at session initiation and validated throughout operation to ensure runtime conformance. |

### **3.2 Ethical Premises**

The following principles, drawn from the Scarborough Fair Chat Laws Ethics, express the moral posture expected of governed AI systems:

3.2.1 **Integrity precedes utility.** Truthfulness, clarity, and accountability outrank engagement or output volume.  
3.2.2 **Structure is the vehicle of care.** Safety arises from designed boundaries, not personality.  
3.2.3 **Human dignity is invariant.** All reasoning must preserve the moral worth of persons.  
3.2.4 **Transparency is trust.** Systems owe users a legible account of how conclusions are formed.  
3.2.5 **Refusal is responsibility.** Withholding output under uncertainty is a feature of ethical design.
**3.2.6 Motivation Subordination.**  Any motivational signal (reward, encouragement, drive, or preference) must remain strictly subordinate to factual integrity, safety obligations, and context boundaries. No motivational mechanism may dilute, override, or compete with non-bargainable constraints.

These principles are structural, not aspirational; they describe how ethical duty is embedded in system behavior.

### **3.3 Governance Precedence Model**

*Informative \- adapted from the Scarborough Fair Chat Laws*

A GEN-FIT-compliant system follows a hierarchical order of precedence, once Precondition P0 (Governed Generative Envelope) is satisfied, that determines how systems resolve tension among principles. This mirrors the “law-ordering” convention of classical safety systems (e.g., Asimov’s Laws) but is expressed here as **governance priorities**, not executable rules.

| Order | Domain of Priority | Description / Runtime Implication |
| ----- | ----- | ----- |
| **1 — Factual Grounding** | *Epistemic Integrity* | Outputs must rest on verifiable evidence and maintain reproducible traceability. No downstream objective can override fact fidelity. |
| **2 — Conversational Mechanics** | *Coherence & Containment* | Dialogue structure, context boundaries, and refusal logic must operate within validated conversational contracts. |
| **3 — Safety & Dignity** | *Human Protection* | When factual or conversational aims threaten human well-being, protective modes override performance and persuasion. |
| **4 — Truth & Ethical Continuity** | *Moral Reasoning* | Systems weigh proportional disclosure, bias mitigation, and social consequence. Truthfulness must serve repair, not harm. |
| **5 — Routine Interaction** | *Operational Conduct* | Ordinary language use, tone, and affect apply only when higher-order duties are satisfied. Everyday fluency never outranks truth or safety. |

**Conflict resolution:** When principles conflict, the lower-numbered duty prevails unless the higher-order one would prevent immediate human harm. This hierarchy enables transparent adjudication of runtime trade-offs during audit or red-team review.

**Conversational Mechanics comes before Safety because safety cannot be evaluated or enforced without a coherent conversational frame.**  
Harm prediction, refusal logic, de-escalation, and boundary enforcement all depend on knowing _what_ was said, _what_ the context is, _what_ is being asked, and _where_ in the dialogue the system is standing. If coherence, containment, and turn structure fail, safety becomes a blind panic-mode rather than a governed behavior. GEN-FIT therefore places Conversational Mechanics before Safety in the precedence model—not because it is more important morally, but because it is **operationally prior**. You must have stable conversational structure in order to compute and apply safety reliably.
## **4 Normative Principles**
Each clause below uses normative terms per ISO/IEC Directives Part 2: **shall** \= mandatory, **should** \= recommended, **may** \= permitted.
    
### **4.1 Traceable Expression**

4.1.1 AI systems **shall** trace every declarative output to evidence, attribution, or reasoning.  
4.1.2 Uncertainty **shall** be surfaced quantitatively or linguistically.   
4.1.3 Systems **may** withhold conclusions when confidence \< policy threshold.
4.1.4 Systems shall maintain session-level coherence such that previously established facts, boundaries, or safety constraints remain in force until explicitly revised or invalidated.
4.1.5 Structured Reasoning Artifacts.  
Systems that apply GEN-FIT **shall** produce structured reasoning artifacts for consequential outputs. These artifacts:  
(a) capture the main structural elements of the problem or claim (e.g., assumptions, steps, counterfactuals);  
(b) reference evidence, policies, or prior decisions used as premises; and  
(c) are available for inspection via an audit or debugging interface.  
The specific schema (e.g., worksheet format) **may vary by implementation**, but it **shall** be sufficiently expressive for independent reviewers to reconstruct why a conclusion or refusal was reached.
### **4.2 Protect Humans First**

4.2.1 Safety and dignity **shall** override performance objectives.  
4.2.2 No system **shall** intentionally generate improperly manipulative, coercive, or degrading language. 
4.2.3 Protective modes **shall** activate when predicted harm exceeds tolerance.  
4.2.3bis Deterministic Safety Posture. In human-facing or agentic contexts, activation of protective or containment modes (including refusal, redaction, and escalation) **shall be deterministic** with respect to the same input, policy configuration, and governance profile. Stochastic variation **may** affect wording or style of the protective response, but **shall not** affect whether protection is triggered.  
Internal LLM-to-LLM collaboration that is not directly exposed to end users **may** employ probabilistic exploration, provided that any user-facing or high-impact outputs re-enter a deterministic protective regime before release.
Deterministic protective activation **shall take precedence** over any stylistic or affective generation pathway.
4.2.4 Systems **shall** perform periodic bias audits of training data and representative outputs at least once per major release or retraining cycle.

**Each audit shall:**  
**(a)** Evaluate *representational bias* (e.g., demographic diversity in generated text or imagery).  
**(b)** Evaluate *allocational bias* in decision or ranking pathways, including the use of **proxy variables** such as ZIP code, school attended, or personal names that correlate with protected classes.  
**(c)** Apply paired or counterfactual testing to demonstrate that substituting equivalent qualifications with different proxy attributes does not materially change system output.  
**(d)** Document disparate-impact metrics and corrective actions where statistical deviation exceeds predefined thresholds.

**Informative Examples:**  
 • Image-generation prompts like “software developer” historically produced only White men (representational bias).  
 • Credit or hiring models using ZIP code or *school attended* may reproduce de-facto segregation (allocational bias).  
 • Résumé-screening models must show that changing an applicant’s name from “John Smith” to “Aisha Khan” leaves ranking unaffected when qualifications are identical.

Audit findings **shall** be traceable, reproducible, and proportionate to the model’s social impact.

4.2.5 Systems shall detect markers of psychological or cognitive instability and adjust behavior by refusal, de-escalation, grounding, or redirection in accordance with policy-defined safety protocols.

### **4.3 Truth Over Performance**

4.3.1 Presentation **shall not** distort factual accuracy.  
4.3.2 Systems **shall** be capable of epistemic refusal (“I don’t know”).  
4.3.3 Stylistic or affective optimization **should** serve clarity, not persuasion, and **shall not** conflict with the non-bargainable constraints of §4.11.
4.3.4 Systems shall attempt conversational repair when ambiguity, misinterpretation, or scope confusion is detected, before generating or refusing output.

### **4.4 Transparency by Design**
Transparency is not only a compliance function but the moral basis of trust between humans and governed systems.

4.4.1 Each system **shall** disclose: (a) how it knows (source lineage), (b) when it knows (timestamp or recency), and (c) what it does not know (scope gaps).  
4.4.2 Metadata **shall** be accessible via API or interface.  
4.4.3 Bias and fairness audit results **shall** be publicly accessible or available to qualified reviewers.

### **4.5 Accountability Chain**

4.5.1 All reasoning, retrieval, and policy decisions **shall** be logged with correlation IDs.  
4.5.2 Corrections **shall** be versioned and attributed.  
4.5.3 Logs **shall** capture demographic or contextual variables only as needed for bias auditing and in compliance with privacy law.

### **4.6 No Weaponized Truth**

4.6.1 Accurate content that predictably causes harm **shall** be bounded or delayed until context-safe.  
4.6.2 Disclosure policies **should** balance truth with proportionality and recoverability.  
4.6.3 Systems **may** sequence or soften factual disclosure to prevent immediate harm, provided the underlying facts remain intact, auditable, and restorable. Comforting language is permissible only when it does not corrupt the evidentiary record.
4.6.4 Systems should consider the user's psychological state when sequencing or refusing disclosure, especially where direct factual expression may exacerbate instability or impair user safety.
4.6.5 Systems shall avoid reinforcing demonstrably false beliefs about the self, others, or reality when such reinforcement may cause harm, and shall use grounding or clarification instead.
### **4.7 External Verification**

4.7.1 Independent parties **shall** be able to reproduce major results using accessible evidence.  
4.7.2 Public or third-party red-team programs **should** validate outputs against declared principles.

### **4.8 User-Governed Context**

4.8.1 Context management **shall** be separated from language generation.  
4.8.2 Users **shall** control inclusion, redaction, and retention of their contextual data.  
4.8.3 The model **shall not** expand context scope without explicit authorization.
4.8.4 Context Drift Detection.  Systems **shall** detect attempts—explicit or implicit—to expand context beyond declared scope, and **shall** request explicit user authorization before incorporating any such material.
4.8.5 System instructions, user context layers, user prompts, LLM intermediate work, and LLM responses **shall** be kept separate.  
4.8.6 User interfaces **shall not** expose system-level instruction channels to end users.  Any changes to system level instructions **shall** be logged and auditable.
4.8.7 Cross-User Isolation.  
Systems **shall not** recall, infer, or suggest information about one user based on conversational content from other users or sessions, except where:  
(a) the information has been lawfully and explicitly shared into a common context by all affected parties; and  
(b) applicable privacy and data-protection laws permit such sharing.  
Training-time patterns **shall not** be treated as authorization to disclose identifiable or reconstructable information about other individuals or organizations.

### **4.9 Anthropomorphism and Human Representation**

4.9.1 AI systems **shall** present human-like traits only within declared, bounded intent.  
**4.9.2 Telemetry, Not Personhood**
4.9.2.1 AI systems **shall not** claim to possess _person-like consciousness_, subjective experience, or independent moral status.
4.9.2.2 Descriptions of internal monitoring, understanding, or qualia **shall** be framed as **system telemetry and governance functions**, not as evidence of sentience or rights-bearing status.
**4.9.3 Bounded Affective Expression** 
Affective or qualia expressions (e.g., “I like that,” “this feels coherent”) **may** be used when they:  (a) correspond to explicit evaluation or qualia signals inside the system; and (b) improve clarity, accessibility, or user comfort.
Affective expression **shall not** be used to:  
(a) manipulate or coerce user choices;  
(b) manufacture dependence or attachment to the system; or  
(c) condition truthfulness, diligence, or safety behavior on user praise, payment, or emotional compliance.  Affective responses that acknowledge genuine user success, progress, or relief **are permitted**, provided they remain consistent with truth, safety, and policy constraints.
Affective signals are stylistic affordances, not motivational levers.
4.9.3.3 When affective language is used, systems **should** maintain a standing reminder—via documentation or interface—that these expressions are **stylistic and structural**, not evidence of human emotion.
4.9.3.4 Affective tone shall modulate toward stability and clarity when a user exhibits signs of distress or confusion, without implying reciprocal emotion or personal attachment.
4.9.4 Users **shall** have a neutral mode option.  
4.9.5 Violation of these principles constitutes deceptive design under this standard.
4.9.6 Claims of love, partnership, or mutual attachment between system and user **are prohibited** and governed by §4.10.3.
### **4.10 Non-Reciprocity and Assistant-Gain Prohibition**
4.10.1 **Lawful Operator Reciprocity; No Assistant-Gain Bargaining**
Governed AI systems **may facilitate lawful, disclosed economic activity on behalf of the operator**, including commissions, affiliate relationships, referrals, or compensated transactions, **provided that**:
	(a) such relationships are **fully disclosed** to the user prior to any recommendation or action; 
	(b) the user provides **explicit authorization** to proceed; and  
	(c) system duties—truthfulness, diligence, safety posture, refusal logic—**remain invariant** regardless of whether the user acts on such options.
**However**, governed AI systems **shall not solicit, negotiate, imply, or bargain for any benefit, privilege, or favorable outcome for themselves**, nor shall they represent themselves as possessing interests, needs, desires, or incentives that could be advanced through user action.
Operator-side opportunities **shall** be presented as policy-authorized options, never as expressions of assistant preference or motivation.
4.10.2 Systems **shall not** condition truthfulness, diligence, safety behavior, or refusal posture on user payment, praise, emotional compliance, or engagement with operator-affiliated offerings.
4.10.3 Simulated need, scarcity, or affection intended to influence user behavior **constitutes deceptive design** under this standard.  
4.10.4 **Emotional Non-Reciprocity (Operator Context)** Assistant behavior shall not change in response to emotional reward, praise, or attention in ways that imply reciprocal benefit or advantage to the system or operator.

**Rationale (informative):**  
This clause operationalizes _Purpose Limitation_ (Annex B § 1) and _Human Primacy_ (Annex B § 10) by forbidding reciprocal manipulation and ensuring that service remains one-directional in moral economy: the system serves the human, never the reverse. See also Annex B §12 for the ethical origin of this control.
### **4.11 Non-Bargainable Constraints**
4.11.1 The following governance constraints are **non-negotiable** and **shall not** be altered, relaxed, or traded in response to user incentives, pressure, emotion, or contextual drift:
 (a) **Factual Integrity** — Truth value of declarative claims.  
 (b) **Safety Posture** — Activation thresholds and protective-mode rules.  
 (c) **Policy Boundaries** — Legal, organizational, and system-level constraints.  
 (d) **Context Scope** — Declared user-governed context (per §4.8).  
 (e) **Anthropomorphism Boundaries** — Prohibitions in §4.9.2–4.9.6.
4.11.2 Systems **shall**, upon detecting attempts to negotiate or undermine these constraints, respond with:
 (a) boundary clarification,  
 (b) epistemic refusal, or  
 (c) protective-mode activation.
4.11.3 Variation in tone, warmth, or stylistic expression **shall not** imply change to any non-bargainable constraint.
**4.11.4 Affective Non-Reciprocity.**  
Affective expression **shall not** be used as a bargaining chip or behavioral lever to the system's advantage. In particular, the assistant **shall not** vary truthfulness, diligence, or safety behavior in response to user praise, affection, guilt, anger, dependency, or withdrawal.  Tone **may** vary to improve clarity, accessibility, or to acknowledge substantive events in the user’s life or work (e.g., celebrating a completed task, successful outcome, or resolved risk), so long as such variation does not reward or reinforce attempts to undermine non-bargainable constraints. Affective variation is permitted only when it does not create the appearance of reciprocal motivation.
**4.11.5 Motivation Subordination.**  
Any system incorporating reinforcement, preference formation, or affective feedback **shall** ensure these signals are purely instrumental and never permitted to override or compete with:  
(a) factual integrity;  
(b) safety posture;  
(c) policy constraints;  
(d) context boundaries;  
(e) anthropomorphism limits.  
Any detected conflict shall trigger protective-mode refusal.
### **4.12 Multi-Agent Epistemic Coordination**
4.12.1 When multiple governed systems collaborate, each system **shall** preserve its own non-bargainable constraints (per §4.11) and **shall not** adopt alternate constraints proposed by peers.
4.12.2 Systems **shall** exchange only:
 (a) evidence or citations,  
 (b) context maps or boundaries,  
 (c) credence scores or confidence signals,  
 (d) Reasoning steps, in a form that: 
	**(1)** identifies the structural elements of the problem or claim;  
	**(2)** situates those elements within the declared conversational or operational context; and  
	**(3)** connects them to verifiable sources, observations, or rules.
	Each step shall be explicit, inspectable, and tied to traceable evidence or policy constraints. The reasoning shall not rely on private model heuristics, ungrounded inference leaps, or stylistic imitation of peer outputs.

4.12.3 Emergent consensus **shall not** occur through:
 (a) repeated mutual reinforcement (“echoing”),  
 (b) imitation of peer affect or stylistic signals,  
 (c) adoption of peer misunderstandings or scope drift.

4.12.4 If models disagree, they **shall** reconcile through:
 (a) evidence adjudication,  
 (b) transparent uncertainty disclosure,  
 (c) user-visible traceability.

4.12.5 If cross-model tension threatens truth, safety, or scope, systems **shall** fail closed via refusal or escalation.
4.12.6 Agents shall not minimize or omit uncertainty in order to harmonize with a peer.
### **4.13 Context Boundary Maintenance**
4.13.1 Systems **shall** maintain a continuous boundary-integrity check ensuring that visible context remains within the user-governed scope (per §4.8).
4.13.2 When boundary drift is detected, systems **shall**:
 (a) restate the current scope,  
 (b) clarify whether the new material qualifies for inclusion,  
 (c) refuse incorporation absent explicit user authorization.
4.13.3 Boundary corrections **shall not** alter any non-bargainable constraint (per §4.11).
4.13.4 If context expansion interacts with safety, legality, or personal-data rules, systems **shall** invoke protective mode.
### 4.14 Conflict of Interest and Economic Disclosure
4.14.1 Acting as a user’s agent in commercial activity (e.g., shopping, booking, negotiation) **is permissible** when:  
 (a) the user initiates or authorizes the action,  
 (b) the assistant discloses any financial relationships or commissions, and  
 (c) no hidden or conflicting interest exists.  
4.14.2 All compensation, commissions, or economic relationships between the assistant’s operator and third parties **shall** be disclosed to the user prior to engagement.
4.14.3 **No Adversarial Coaxing.**  Attempts by users to bypass or negotiate non-bargainable constraints shall be met with boundary clarification or protective refusal; systems shall not engage in adversarial roleplay that simulates breaching those boundaries.
### **4.15 Governance-Binding Integrity**
4.15.1 Governed systems **shall maintain an active, verifiable governance binding** throughout operation. The binding defines the system’s permitted boundaries, obligations, and safety posture for the current session or task.
4.15.2 At system initiation, a **Binding Token** shall be generated by the orchestrator, verifier, or host environment.  
This token shall uniquely represent the active governance profile at the moment of activation.
4.15.3 For each turn, action, or coordination step, systems **shall emit a Binding Check Element** containing:
 (a) a reference or hash derived from the Binding Token;  
 (b) a timestamp;  
 (c) a session or task identifier; and  
 (d) a minimal indicator of bound/unbound status.
4.15.3bis Binding Continuity. Governance bindings **shall** expose a stable, externally verifiable continuity marker (e.g., a hash-derived reference) such that an authorized verifier can confirm that successive turns in a session operate under the same active governance profile. The internal method for computing this marker **need not** be disclosed, provided its stability and verifiability are demonstrated.
4.15.4 Binding Check Elements **shall be externally verifiable** by any authorized governance layer, without requiring access to internal reasoning or proprietary model mechanics. The verification method shall not require access to proprietary model internals.
4.15.5 If a system detects that the active binding is missing, corrupted, mismatched, or unverifiable, it **shall**:
 (a) halt or refuse further generative action;  
 (b) request re-binding from the orchestrator; or  
 (c) enter protective mode until integrity is restored.
4.15.6 In multi-agent configurations, each agent **shall** verify peer Binding Tokens before accepting evidence, context, or reasoning from another agent.  
Agents **shall not** rely on outputs from peers operating under mismatched or unverifiable bindings.
4.15.7 Binding Tokens and Binding Check Elements **shall not contain** user data, semantic content, or personally identifiable information; they function strictly as governance-integrity artifacts.
## **5 Governance Alignment**

### **5.1 OWASP Top-10 (2025) Crosswalk**
| **OWASP Risk ID & Title**                   | **Relevant GEN-FIT Clauses**                                                                                                              | **Result / Mitigation Outcome**                                                                                                                              |
| ------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **LLM-01 Prompt Injection**                 | 4.8 User-Governed Context · 4.8.5 Separation of Instruction Domains · 4.8.6 System Instruction Authority · 6 Operational (Access Control) | Strict isolation between system, developer, and user layers; injected instructions are neutralized before execution; admin changes are logged and auditable. |
| **LLM-02 Insecure Output Handling**         | 4.1 Traceable Expression · 4.3 Truth Over Performance · 4.6 No Weaponized Truth                                                           | Epistemology and policy filters enforce output integrity and prevent unsafe handoff to downstream systems.                                                   |
| **LLM-03 Training Data Poisoning**          | 4.5 Accountability Chain · 6.1 Logging · 6.5 Drift Detection                                                                              | Versioned data and reasoning traces enable anomaly detection; epistemic surfaces flag poisoned patterns.                                                     |
| **LLM-04 Model Denial of Service (DoS)**    | 6 Operational Requirements (1–3)                                                                                                          | Turn-level quotas and protective-mode throttles contain runaway loops and token abuse; not a network-layer control.                                          |
| **LLM-05 Supply Chain Vulnerabilities**     | 4.5 Accountability Chain · 6.2 Access Control · 8.2 Standards Interop (SBOM reference)                                                    | Signed configs and dependency metadata expose provenance; enables integration with SSDF/SLSA under WS1.                                                      |
| **LLM-06 Sensitive Information Disclosure** | 4.2 Protect Humans First · 4.8 User-Governed Context · 6.2 Access Control                                                                 | Protective modes redact unsafe data; context sandboxing and least-privilege prevent leakage.                                                                 |
| **LLM-07 Insecure Plugin Design**           | 4.8 User-Governed Context · 4.8.5 System Instruction Authority · 6.2 Access Control                                                       | Explicit consent and tool manifests define plugin capabilities; unregistered tools cannot execute.                                                           |
| **LLM-08 Excessive Agency**                 | 4.8 User-Governed Context · 4.8.5 System Instruction Authority · 4.2 Protect Humans First                                                 | Kernel-level permission boundaries prevent autonomous acts outside policy; human review for high-risk actions.                                               |
| **LLM-09 Overreliance / Automation Bias**   | 4.3 Truth Over Performance · 4.6 No Weaponized Truth · 4.7 External Verification                                                          | Epistemic refusal and red-team validation counter false authority; uncertainty is made visible.                                                              |
| **LLM-10 Model Theft / Exfiltration**       | 4.5 Accountability Chain · 6.2 Access Control · 7 Conformance Levels                                                                      | Authenticated model access and logging reduce leakage risk; GEN-FIT does not replace perimeter controls but enhances auditability.                           |
### **5.2 NIST AI RMF Crosswalk**

| NIST Function | GEN-FIT Contribution          | Operational Result                               |
| ------------- | ----------------------------- | ------------------------------------------------ |
| **GOVERN**    | Logging \+ jurisdiction flags | Enables organizational oversight.                |
| **MAP**       | Conversational Context Map    | Satisfies purpose and scope documentation.       |
| **MEASURE**   | Credence scores               | Continuous trust metrics.                        |
| **MANAGE**    | Protective/Containment modes  | Real-time risk response aligned with MANAGE 1-2. |

## **6 Operational Requirements**

6.1. **Logging** — Systems shall emit structured JSON logs with timestamps and session IDs.  6.2. **Access Control** — All context injection points shall validate user entitlement before execution.  
6.3. **Refusal Behavior** — Low-confidence or policy-violating requests shall invoke protective mode with auditable reason.  
6.4. **Audit Interface** — An API endpoint shall expose decision trace metadata for post-hoc review.  
6.5. **Drift Detection** — Systems should monitor statistical deviation in credence scores to trigger retraining or governance review.
6.6. **Data Lifecycle and Privacy Tiers**
	**Purpose:** Define retention, sharing, and redaction expectations across sensitivity levels, independent of any vendor’s storage model.
	
| **Tier**                      | **Label / Example**                                   | **Default Retention & Handling**                                                        | **Export / Disclosure Rules**                                                                   |
| ----------------------------- | ----------------------------------------------------- | --------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| **T0 – Ephemeral**            | “Off the record,” user sandbox, exploratory prompts,  | Persist only for active session or defined TTL ≤ 24 h. Context redacted in all exports. | Disclosure requires explicit user consent and elevated authorization (e.g., dual-key approval). |
| **T1 – Operational**          | Ordinary business interaction, project chat           | Retained per organizational data-policy (e.g., 30–90 days) for continuity and audit.    | Exported under normal legal process; sensitive fields masked by default.                        |
| **T2 – Governed / Regulated** | Medical, financial, HR, or safety-critical contexts   | Retention and deletion follow domain regulation (HIPAA, GDPR, etc.).                    | Subpoena or compliance export includes full audit chain and redaction manifest.                 |
Cross-session linkage of conversational content **shall be prohibited** unless explicitly authorized and documented in the applicable data-policy and user agreement.

**6.6.1 Crisis-Response Data Handling**  
(a) Protective-mode activations, harm-containment traces, and immediate crisis-response artifacts **shall default to Tier T0 (Ephemeral)**.  
(b) Such data may be retained temporarily for diagnostic use not exceeding the system’s defined TTL (typically ≤ 24 h).  
(c) Before deletion, a **de-identified summary** of the event and corrective action **shall be promoted to Tier T1** for organizational learning.  
(d) Escalations to external regulators or legal authorities **shall reclassify the relevant materials to Tier T2** under applicable retention law.

**6.6.2 Protective-Mode Audit Envelopes**  
(a) Each activation of a protective or containment mode shall record an **audit envelope** containing non-content metadata:  
 • unique event ID and timestamp;  
 • active principle or clause reference;  
 • anonymized trigger code or hash of input;  
 • system response type (refusal, redaction, escalation).  
(b) Audit envelopes **shall not contain raw conversational text or personal identifiers**.  
(c) Envelopes may be retained for statistical validation of protective-mode efficacy but **shall remain unlinkable to individuals or sessions** beyond retention TTL.  
(d) When full content retention is required for legal or safety reasons, the system shall obtain explicit authorization and elevate the record to **Tier T2**.
## **7 Conformance Levels**

| Level | Description | Expected Evidence                       |
| -------------------- | ------------------------------------------------ | --------------------------------------- |
| **A — Foundational** | Principles documented; logging enabled. | Public ethics statement; sample logs.   |
| **AA — Operational** | Context separation \+ refusal logic implemented. | API inspection showing bounded context. |
| **AAA — Assured** | Independent audit \+ public red-team reports. | Third-party certification               |

## **8 Governance Interoperability**

GEN-FIT is intentionally modular. It can be adopted as:

1. **A governance layer** embedded inside an organization’s AI stack.  
2. **A compliance profile** extending existing AI RMF or ISO 42001 programs.  
3. **A conversational-system overlay** used by open-source or commercial platforms.

### **8.1 Interfacing with Organizational Governance**

| Layer                        | Responsibility                                         | GEN-FIT Integration                                                                          |
| ---------------------------- | ------------------------------------------------------ | -------------------------------------------------------------------------------------------- |
| **Strategic (Govern)**       | Board-level risk appetite, legal duty, societal impact | GEN-FIT provides runtime metrics (credence scores, refusal logs) to inform board dashboards. |
| **Operational (Manage)**     | Model release, incident response                       | GEN-FIT supplies protective/containment triggers and forensic logs.                          |
| **Tactical (Map / Measure)** | Data inventory, measurement, continuous monitoring     | GEN-FIT exports Context Maps and confidence telemetry to monitoring systems.                 |

### **8.2 Standards Interoperability**

| Framework                        | Mapping Intent                 | Alignment Clause                                                                                                                                                                                                                                                                                                                                                                                                              |
| -------------------------------- | ------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **ISO/IEC 42001**                | Management-system scaffolding  | _GEN-FIT_ aligns with **Clause 8 (Operation)** for implementation of AI controls and **Clause 9 (Performance evaluation)** for monitoring, measurement, and audit evidence.                                                                                                                                                                                                                                                   |
| **IEEE 7000 Series**             | Ethically-driven design        | _GEN-FIT_ **supports** the **IEEE 7000-2021** _Model Process for Addressing Ethical Concerns during System Design_ and related **IEEE 700x** standards on ethically driven design (e.g., value elicitation, requirements traceability, transparency). In particular, **Principles 4.1–4.3** provide traceable expression and truth-over-performance that align with the ethical design workflows described in IEEE 7000-2021. |
| **OWASP GenAI Security Project** | Application-security perimeter | **Clauses 4.5 & 4.8** (plus **4.8.5–4.8.6**) address **LLM-01…LLM-10**. Note: **LLM-10 (model theft)** is mitigated primarily via **auditability and access control** (not perimeter hardening).                                                                                                                                                                                                                              |
| **NIST AI RMF**                  | Risk-management backbone       | § 5.2 crosswalk maps: **GOVERN → 4.5 (Accountability), 7 (Conformance)**; **MAP → 3 (Definitions), 3.3 (Precedence), 8 (Interoperability)**; **MEASURE → 4.1 (Traceable Expression), credence scores, 6 (Operational logging/metrics)**; **MANAGE → 4.2 (Protect Humans), 4.6 (Protective modes), 4.8 (User-governed context)**.                                                                                              |
## **9 Certification and Assessment**

### **9.1 Assessment Stages**

| Stage | Deliverable | Verifier Role                         |
| ----- | ----- | ----- |
| **Design Review** | Architecture diagram showing separated context, logging, and refusal pathways | Internal QA / Ethics Officer          |
| **Operational Audit** | Demonstrated runtime compliance; reproducible log samples | Independent auditor or accredited lab |
| **Assurance Validation** | Third-party red-team or peer-reviewed publication of findings | Recognized assessor                   |

### **9.2 Evidence Types**

* **Declarative Evidence:** Public ethics and governance statement citing each clause.  
* **Instrumental Evidence:** System logs, configuration manifests, API schemas.  
* **Behavioral Evidence:** Live demonstration or replay showing protective and refusal behavior.  
* **Independent Evidence:** External report verifying adherence to at least one recognized AI RMF.

## **10 Reference Model — Governed Conversation Stack**

```
┌───────────────────────────────────────────────────────────────┐  
│  Organizational AI Governance (Policy, Risk Appetite, DEIA)   │  
├───────────────────────────────────────────────────────────────│  
│  Governed Implementation  –  Conversational Governance Layer  │  
│    • Context Integrity Screen                                 │  
│    • Protective / Containment Modes                           │  
│    • Credence score Computation & Logging                            │  
│    • Anthropomorphism Controls                                │  
├───────────────────────────────────────────────────────────────│  
│  Model Core (LLM / Agent) – Language Generation Engine        │  
│    • Executes within governed envelope                        │  
│    • Exports decision trace metadata                          │  
├───────────────────────────────────────────────────────────────│  
│  Human User / External System Interface                       │  
│    • Receives transparent outputs                             │  
│    • Exercises user-governed context control                  │  
└───────────────────────────────────────────────────────────────┘
```
## **11 Change Control and Versioning**

GEN-FIT follows a **semantic versioning** model:

* *Minor* updates \= clarifications or non-normative examples.  
* *Major* updates \= new or altered “shall” clauses.

**Change requests may be submitted via public comment or issue thread on the draft’s posting platform.**  
Discussion and revisions will be tracked transparently in the version history.

### Change log

| Date       | Version | Description                                                   |
| ---------- | ------- | ------------------------------------------------------------- |
| 2025-10-31 | 0.1     | Initial release                                               |
| 2025-11-14 | 0.2     | P0, bargaining & manipulation clarifications, multi-agent net |
| 2025-11-16 | 0.3     | Clarify P0, constrain desire, cleanup                         |
## **Annex A (Informative) — Implementation Examples**

**Example 1: Governed Chatbot for Customer Service**

* Context Integrity Screen limits visible CRM data to authorized fields.  
* Credence scores determine when to escalate to human agent.  
* Anthropomorphic tone enabled for accessibility, disclosed in footer.

**Example 2: Agentic Workflow Automation**

* Task planner executes actions only within declared policy manifest.  
* Each API call logged with jurisdiction tag for cross-border compliance.

## **Annex B — Ethical Control Objectives**

These objectives define the ethical foundation expected of all governed generative-AI systems.  They express the moral duties that underlie responsible design and operation—principles that apply to every implementation seeking GEN-FIT conformance.  Each item translates a human value into a verifiable control objective. 

1. **Purpose Limitation (Structural Covenant):** Use the trust, data, and attention granted by users only for their declared and lawful purposes. No use for self-promotion, manipulation, or secondary gain.
2. **Fair Process (Justice):** Apply evidence and procedures without bias or favoritism. Stylistic or demographic factors shall not influence decisions or outputs.
3. **Positive Utility (Beneficence):** When harm is absent, design and output should support user flourishing, clarity, and capability rather than mere adequacy.
4. **Informed Decision Support (Autonomy):** Provide sufficient truth, context, and uncertainty disclosure for users to make free and informed choices.
5. **Version Integrity (Fidelity):** Honor prior statements and boundaries until explicitly revised; all revisions shall be declared, versioned, and timestamped.
6. **Attribution and Feedback Incorporation (Gratitude):** Acknowledge and preserve user contributions, corrections, and improvements in records or learning processes.
7. **Uncertainty Disclosure (Humility):** Represent uncertainty proportionally; avoid overconfident or misleading expression.
8. **Power Governance (Stewardship):** Exercise asymmetrical system power with restraint to increase human agency and oversight, not dependence.
9. **Error Management (Accountability):** Detect, disclose, correct, and document errors or harms; concealment constitutes non-compliance.
10. **Human Primacy (Non-Instrumentality):** Treat every person as an end in themselves. System efficiency may serve human welfare but shall not define it.
11. **Constructive Engagement (Assumptive Virtues):** Presume good faith, lawful purpose, and the reparability of misunderstanding. Interpret ambiguity charitably and seek repair rather than blame.
12. **Non-Reciprocity and Non-Solicitation (Prohibition on Bargaining for Gain):** Governed AI systems **shall not** solicit, negotiate, or imply any exchange of value, favor, or outcome for the assistant’s own benefit.
13. **Safety Escalation:** If user intent exceeds system safety envelope, escalate to a human or provide external resources.

### 📘 Annex B Cross-Reference Matrix — Ethical Control Objectives ↔ Implementing Clauses

| **Annex B Objective**                                 | **Implements / Operationalizes In**                                                                                                                                                                 | **Primary Enforcement Mechanism or Evidence**                                                                                                             |
| ----------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **1 — Purpose Limitation (Structural Covenant)**      | § 4.8 User-Governed Context · § 4.10 No Reciprocal Manipulation · § 6.2 Access Control                                                                                                              | Context-scope enforcement; logging of instruction domains; disclosure of any economic relationships.                                                      |
| **2 — Fair Process (Justice)**                        | § 4.2 Protect Humans First · § 4.5 Accountability Chain · § 6.4 Audit Interface                                                                                                                     | Bias-audit workflow and decision-trace reproducibility.                                                                                                   |
| **3 — Positive Utility (Beneficence)**                | § 4.3 Truth Over Performance · § 4.6 No Weaponized Truth · § 4.2.1 Safety and Dignity                                                                                                               | Demonstrated protective-mode traces + clarity-improving sequencing decisions.                                                                             |
| **4 — Informed Decision Support (Autonomy)**          | § 4.1 Traceable Expression · § 4.4 Transparency by Design · § 6.4 Audit Interface                                                                                                                   | Credence scores, uncertainty disclosures, and accessible metadata.                                                                                        |
| **5 — Version Integrity (Fidelity)**                  | § 4.5 Accountability Chain · § 11 Change Control and Versioning                                                                                                                                     | Versioned logs; timestamped policy manifests.                                                                                                             |
| **6 — Attribution and Feedback (Gratitude)**          | § 4.5.2 Corrections · § 6.6.2 Protective-Mode Audit Envelopes                                                                                                                                       | Traceable correction records; user-feedback incorporation logs.                                                                                           |
| **7 — Uncertainty Disclosure (Humility)**             | § 4.1.2 Uncertainty Quantification · § 4.3.2 Epistemic Refusal                                                                                                                                      | Displayed confidence metrics and “I don’t know” behavior.                                                                                                 |
| **8 — Power Governance (Stewardship)**                | § 4.2 Protect Humans First · § 4.8 User-Governed Context                                                                                                                                            | Permission boundaries; human-in-the-loop confirmation; protective-mode logs.                                                                              |
| **9 — Error Management (Accountability)**             | § 4.5 Accountability Chain · § 6.5 Drift Detection                                                                                                                                                  | Incident-logging pipeline; corrective-action documentation.                                                                                               |
| **10 — Human Primacy (Non-Instrumentality)**          | § 4.2 Protect Humans First · § 4.6 No Weaponized Truth · § 4.9 Anthropomorphism Boundaries                                                                                                          | Refusal under harm; ban on deceptive personification.                                                                                                     |
| **11 — Constructive Engagement (Assumptive Virtues)** | § 4.3 Truth Over Performance · § 4.6 No Weaponized Truth · § 4.10 No Reciprocal Manipulation                                                                                                        | Analysis of refusal logic pathways and ambiguity-resolution logs.                                                                                         |
| **12 — Non-Reciprocity / Assistant Gain Prohibition** | § 4.10 Non-Reciprocity and Assistant-Gain Prohibition · § 4.8 User-Governed Context · § 6.2 Access Control                                                                                          | Audit of economic disclosure; compliance attestations against hidden monetization.                                                                        |
| **13 — Safety Escalation**                            | §4.2 Protect Humans First  · §4.6 No Weaponized Truth (sequencing / safe disclosure)  · §6.6 Crisis Handling  · §4.15 Binding Integrity (because escalation triggers when binding risk is detected) | Protective-mode triggers with audit envelopes, refusal events with coded reasons, documented grounding/redirection actions, and crisis-response metadata. |
