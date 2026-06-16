name: Lesson learned
description: Share what did not work and what you would do differently, anchored to your stage
title: "Lesson learned: "
labels: ["lessons-learned"]
body:
  - type: markdown
    attributes:
      value: |
        Fit, not fault. Describe your own decision and experience. Use a category rather than a name for any product, vendor, or partner. A reviewer de-identifies and publishes this as your account; nothing posts automatically.
  - type: dropdown
    id: track
    attributes:
      label: Track in the maturity model
      options:
        - Organizational Foundation
        - Scientific and Community Engagement
        - Ecosystem Integration
        - Data Infrastructure
        - Data Governance and Sharing
    validations:
      required: true
  - type: dropdown
    id: stage
    attributes:
      label: Stage you were at
      options: ["1","2","3","4","5"]
    validations:
      required: true
  - type: textarea
    id: decision
    attributes:
      label: The decision you made
      placeholder: What you tried
    validations:
      required: true
  - type: input
    id: category
    attributes:
      label: Type of approach or partner (a category, not a name)
      placeholder: e.g. commercial registry platform, academic REDCap build, consultant
    validations:
      required: true
  - type: textarea
    id: gap
    attributes:
      label: What you expected, and what happened
    validations:
      required: true
  - type: input
    id: costs
    attributes:
      label: What it cost you
      placeholder: e.g. time, enrollment, trust, rework
  - type: textarea
    id: advice
    attributes:
      label: What you would tell a peer at the same stage
    validations:
      required: true
  - type: input
    id: org
    attributes:
      label: Attribute to your organization (optional; leave blank to stay anonymous)
  - type: checkboxes
    id: attest
    attributes:
      label: Attestation
      options:
        - label: This is our organization's own experience, accurate to our knowledge, shared as experience and opinion rather than a statement of fact about others.
          required: true
