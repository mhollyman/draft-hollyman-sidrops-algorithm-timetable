The format of the timeline sections.
RFC6916 says: the algorithm transition timetable must be published as a BCP to define the dates of each phase transitions.
Also describe how the community will measure the readiness of cAs and RPs to transition each phase. 
Also must describe the procedures to amend the timetable if problems arise in implementing later phases of the transition.

Milestones:
* CA Ready Algorithm B Date
* CA Go Algorithm B Date
RP Ready Algorighm B Date
Twilight Date
End-Of-Life Date

From section 4.3:

Phase 0
Steady-state of RPKI with only one algorithm suite in use. 

Milestone 1
Tasks:
    Update RFC6485 with Algorithm Suite A and Suite B
    Publish transition timeline document with dates for:
        CA Ready Algorithm B Date
        CA Go Algorithm B Date
        RP Ready Algorithm B Date
        Twilight Date
        EOL Date
        Readiness metrics for CAs and RPs in each phase

Section 4.4:
Phase 1
    This is the CA Ready Algorithm B Date
    All non-leaf CAs MUST be ready to process a request from a child CA to issue or revoke a certificate using Algorithm Suite B. 
    If not ready, timeline document MUST be re-issued. 

Section 4.5:
Phase 2
    This is the CA Go Algorithm B Date
    Each signed product set MUST be available using both Algorithm Suite A and Suite B. 
    Every product for Suite A must include a product for Suite B. 
    RPs MUST validate Suite A and MAY validate Suite B. 
    If substantial number of CAs are not ready, the timeline document MUST be reissued. 

Section 4.6:
Phase 3
    This is the RP Ready Algorithm B Date
    All signed product sets are available using both algorithm suites, all RPs MUST be able to validate them. 
    Recommended RPs process Suite B sets first and prefer them.
    If substantial number of RPs are unable to process product sets in Suite B, timeline MUST be reissued. 

Section 4.7:
Phase 4
    This is the Twilight Date.
    All signed products MUST be issued using Suite B and MAY be issued using Suite A.
    RPs SHOULD NOT assume Suite A product sets are complete. 
    Every RP MUST validate signed product sets using Suite B. 
    If substantial RPs are not capable of processing the new suite, timeline MUST be reissued. 

Section 4.8:
Return to Phase 0
    This is the EOL Date
    Old algorithm Suite A MUST be deprecated using the process in section 10. 
    Algorithm Suite B is now considered Suite A. No Suite B exists. 


Notes:
    1. How do we look for packages of old RP software that will NOT use the Suite B algorithm version? 
    2. How do we test CAs not ready to produce Suite B products?
    3. How do we test RPs unable to process Suite B products?
    4. How do we test RPs that do NOT solicit and download Suite B products?
