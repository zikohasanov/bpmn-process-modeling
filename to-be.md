# To-Be Process — Online Request and Staff Decision

## Proposed first-release workflow

```mermaid
flowchart TD
  subgraph Customer
    A((Start)) --> B[Browse menu and configure cart]
    B --> C[Review total, contact, and notices]
    C --> D{Customer submits?}
    D -- no --> X((End without order))
    D -- yes --> E[Receive reference and pending explanation]
    E --> F[Check verified status]
    R[Receive rejection and next-step guidance]
    Y[Receive ready update and collect order]
  end
  subgraph Ordering_service
    D -- yes --> G[Revalidate menu, price, and options]
    G --> H{Valid and available?}
    H -- no --> I[Return item/price changes for review]
    I --> B
    H -- yes --> J[Persist order as AwaitingReview]
    J --> E
    K[Persist staff decision and event]
    K --> L[Queue notification]
  end
  subgraph Restaurant_staff
    J --> M[Review request and capacity]
    M --> N{Accept?}
    N -- no --> O[Reject with reason]
    N -- yes --> P[Accept request]
    P --> Q[Prepare and mark Ready]
    Q --> S[Verify reference and hand off]
  end
  O --> K
  P --> K
  Q --> L
  L --> R
  L --> Y
```

## BPMN-style interpretation

- Start and end circles represent process start/end events.
- Rectangles represent tasks performed by a participant.
- Diamonds represent exclusive decisions with labeled outcomes.
- The three lanes separate customer, service, and restaurant responsibility.
- Notification is a queued service task; provider delivery is an external dependency and can fail without undoing the order state.
