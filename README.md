# Lab 2 --- File Upload and Command Injection Assessment

## Overview

This repository contains the assessment report and supporting evidence
for Lab 2. Testing was conducted against the authorised local training
instances of DVWA and OWASP Mutillidae II.

The assessment focused on:

-   File-upload validation and filename/content mismatch handling
-   File storage and retrieval/content delivery
-   Command-injection behaviour
-   Affected parameters and execution context
-   Observed versus potential impact
-   Stronger-security retesting
-   Remediation recommendations
-   Cleanup and reset verification

All testing used harmless markers and non-destructive inputs. No
malware, executable upload, destructive command, persistence, privilege
escalation, external callback, or unrelated-system access was performed.

## Repository Contents

  -----------------------------------------------------------------------
  Item                                Description
  ----------------------------------- -----------------------------------
  `report/`                           Final PDF assessment report

  `evidence/`                         Numbered screenshots and other
                                      supporting evidence

  `markers/`                          Harmless test markers and their
                                      supporting hash information

  `evidence-register.md`              Evidence index linking each
                                      evidence ID to its purpose

  `activity-log.md`                   Chronological record of assessment
                                      activities
  -----------------------------------------------------------------------

## Test Environment

  -----------------------------------------------------------------------
  Application             Initial Mode            Stronger Retest
  ----------------------- ----------------------- -----------------------
  DVWA                    Low                     Impossible

  OWASP Mutillidae II     Security Level 0        Not required for the
                                                  stronger-mode
                                                  comparison
  -----------------------------------------------------------------------

## Scope and Safety

Testing was restricted to the local authorised lab environment. The
assessment used minimal proof-of-concept techniques to establish whether
the relevant security boundaries could be crossed. Testing stopped once
the required behaviour was demonstrated.

Potential impacts stated in the report are clearly distinguished from
impacts directly observed during the assessment.

## Key Results

-   DVWA Low accepted the filename/content mismatch marker.
-   Mutillidae II accepted the filename/content mismatch marker and
    explicitly reported that validation was not performed.
-   DVWA and Mutillidae II both demonstrated harmless command-marker
    execution in their vulnerable configurations.
-   At DVWA Impossible, the same mismatched upload was rejected.
-   At DVWA Impossible, the same modified command input was rejected as
    an invalid IP.
-   The stronger DVWA configuration therefore demonstrated a clear
    improvement in the two tested areas.

## Evidence

Evidence IDs are documented in `evidence-register.md`. The individual
evidence files should be kept unchanged after final verification so that
the submitted package remains consistent with the report.

## Submission Note

This repository is intended to provide the final report together with
the supporting assessment evidence and activity documentation.
