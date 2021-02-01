# Privacy

This guidance should not be considered a blueprint for all things privacy when writing code, but rather a starting point. Privacy should be at the top of mind of every developer and architect as they design and implement solutions.

## General Checklist

This checklist is not meant to be exhaustive but rather a starting point to get team started when thinking of their overall architecture:

- [ ] Determine applicable regulations
- [ ] Account for industry/trade organization, e.g. IAB
- [ ] Determine Privacy Stakeholders (e.g. CPO)
- [ ] Determine consumer base (e.g. Will children use the solution?)
- [ ] Classify each dataset (e.g. Sensitive/Non-sensitive)
- [ ] Categorize each dataset (e.g. Medical, Financial, etc.)
- [ ] Map the data flow (from end-user to endpoint)
- [ ] Develop Data Access Plan (who can access what for what reasons)

## Recipes

- [Logging](recipes/logging.md)

## References

- [CCPA](https://oag.ca.gov/privacy/ccpa/regs#:~:text=CCPA%20grants%20California%20consumers%20robust,as%20additional%20protections%20for%20minors.)
- [IAB - CCPA Technical Spec](https://github.com/InteractiveAdvertisingBureau/USPrivacy)
