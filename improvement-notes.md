# Improvement Notes

| Change | Current friction hypothesis | Proposed control | Trade-off / measure |
|---|---|---|---|
| Structured menu and cart | Staff transcribe spoken item names and options | Customer selects configured options; staff sees a structured snapshot | Customer must learn the interface; compare corrections per 100 orders |
| One authoritative order reference | Paper, POS, and verbal status may diverge | Service stores order state and transition history | Staff need a reliable device and fallback; measure queue handling time |
| Staff acceptance gate | Submission could be mistaken for a commitment despite capacity limits | Request stays pending until authorized staff accept | Customer waits; monitor decision time and rejection reasons |
| Revalidation at submit | Item status may change while customer browses | Check availability and price at final submit | Some carts need revision; measure abandoned submissions after change |
| Secure status lookup | Status calls interrupt staff | Reference plus one-time verification | Verification friction; track successful lookup and support contacts |
| Explicit failure route | Notification or internet failure can hide the request | Preserve the order, show a browser reference, and expose delivery failure to staff | Adds operational support steps; rehearse outage and retry path |

## Pilot measures

Record a four-week baseline and an eight-week pilot. Report order channel mix, opening hours, staffing, and changes to menu or process. A before/after difference does not establish that the service alone caused the change. Review small samples of order corrections and status calls to classify causes before drawing conclusions.
