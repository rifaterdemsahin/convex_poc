# Open Questions

Questions driving this PoC. Each must be answered in `7_Testing_Known`.

## Technical Questions

1. How does Convex handle concurrent mutations — does it guarantee ordering?
2. What is the practical query reactivity latency (mutation → client update)?
3. How does Convex paginate large result sets?
4. Can Convex actions call external REST APIs reliably?
5. How are database indexes defined and what are the query limitations without an index?

## Operational Questions

6. What does the free tier limit at (storage, bandwidth, function calls)?
7. How does Convex handle cold starts for actions?
8. Is the Convex dashboard sufficient for time-travel debugging in production?

## Integration Questions

9. How does Clerk authentication integrate with Convex identity context?
10. Can Convex work alongside an existing REST API as a real-time layer only?
