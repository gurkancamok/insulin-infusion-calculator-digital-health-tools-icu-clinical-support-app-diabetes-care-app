# Insulin Infusion Clinical Decision Support System

### Protocol-driven clinical decision support for structured insulin infusion management

---

## Live Application

**Launch the application:**

https://gurkancamok.github.io/insulin-infusion/

---

## Overview

The **Insulin Infusion Clinical Decision Support System** is a browser-based clinical decision support application that translates a structured insulin infusion protocol into an interactive digital workflow.

The system evaluates blood glucose values, previous glucose measurements, measurement intervals, current infusion rates, and protocol-defined clinical conditions to generate the corresponding protocol action.

Rather than requiring the user to manually navigate multiple decision tables, calculate hourly glucose changes, identify the appropriate Δ / 2Δ adjustment range, and determine the resulting infusion action, the application executes these steps through a deterministic rule-based decision process.

---

## Clinical Workflow

The application supports the principal decision pathways defined in the source protocol, including:

- Blood glucose below 50 mg/dL
- Blood glucose between 50–74 mg/dL, including assessment of hypoglycemia symptoms
- Blood glucose ≥75 mg/dL
- Hourly blood glucose trend calculation
- Infusion-rate adjustment according to Δ and 2Δ rules
- Protocol-defined physician notification thresholds
- Insulin infusion initiation guidance
- Blood glucose monitoring intervals
- Hypoglycemia management pathways

The system also retains the source protocol tables, clinical warnings, monitoring instructions, infusion preparation guidance, and references within the application interface.

---

## Decision Logic

For ongoing insulin infusion management, the application calculates the hourly glucose change using:

**Hourly glucose change = (Current BG − Previous BG) / Measurement interval**

The resulting trend is evaluated against the patient's current blood glucose range and the current insulin infusion rate.

The system then identifies the corresponding protocol action, including:

- Increase by Δ
- Increase by 2Δ
- No change
- Decrease by Δ
- Temporarily stop the infusion and decrease by 2Δ
- Protocol-specific hypoglycemia actions
- Physician notification when required

Where the source protocol does not define a precise numerical interpretation, the application does not silently generate an unsupported value.

---

## Clinical Decision Support Design

The application was designed to convert a static multi-step clinical protocol into a structured digital decision pathway.

The workflow brings together:

**Clinical input → hourly trend calculation → protocol rule selection → infusion-rate rule → protocol action**

This structure reduces the number of manual interpretation steps required when navigating the original protocol while preserving the protocol-defined clinical logic.

---

## User Interface

The system provides:

- Responsive desktop and mobile interface
- Turkish and English language support
- Structured clinical input fields
- Dynamic hypoglycemia assessment
- Protocol decision output
- Integrated warning messages
- Expandable protocol guidance
- Blood glucose decision matrix
- Δ / 2Δ infusion-rate table
- Insulin infusion initiation guidance
- Monitoring protocol
- Clinical references

The interface is designed to make the underlying protocol transparent rather than hiding the decision rules from the user.

---

## Technical Architecture

The application is implemented as a lightweight browser-based system using:

- HTML5
- CSS
- Vanilla JavaScript
- Deterministic rule-based decision logic
- Responsive user interface design

The application does not require a server-side calculation engine or external JavaScript framework for its core clinical decision logic.

This architecture enables rapid deployment through standard web infrastructure and allows the decision logic to remain directly inspectable.

---

## Protocol Fidelity and Verification

The digital decision logic was reviewed against the original insulin infusion protocol, with particular attention to:

- Blood glucose range boundaries
- Hourly glucose-change thresholds
- Δ and 2Δ infusion-rate bands
- Hypoglycemia pathways
- Physician notification thresholds
- Infusion initiation ranges
- Undefined protocol ranges
- Turkish and English decision outputs

Boundary-condition and regression testing were performed across the protocol decision pathways.

Special attention was given to clinically important transition points such as:

**50 / 74 / 75 / 99 / 100 / 139 / 140 / 199 / 200 mg/dL**

and the hourly change thresholds used by the protocol decision matrix.

The application is designed not to invent a clinical rule when the source protocol does not provide one.

---

## Protocol Transparency

A key design principle of the system is **traceability between the digital output and the underlying clinical protocol**.

Users can review within the same interface:

- Original decision categories
- Infusion adjustment table
- Hypoglycemia instructions
- Insulin infusion initiation instructions
- Monitoring requirements
- Clinical warnings
- Source references

This allows the digital decision output to remain auditable against the protocol on which it is based.

---

## Intended Use

This application is a clinical decision support implementation of a defined insulin infusion protocol.

It is intended to support structured protocol interpretation and does not replace clinical judgment, institutional governance, or physician-directed treatment decisions.

When a clinical situation is outside the scope of the source protocol, the original protocol and appropriate clinical escalation pathway should be followed.

---

## Development

**Gürkan ÇAMOK, MSc**  
**Clinical Decision Support Systems Developer**

Focus areas:

- Clinical Decision Support Systems
- Digital Health
- Clinical Workflow Engineering
- Medication Safety
- Healthcare Software
- Rule-Based Clinical Systems

---

## License

This repository is distributed under the **MIT License**.
