APPENDIX B — ACTIVITY LOG
Date/Time
Application
Activity
Tool/Method
Result/Observation
Correction/Notes
28 Aug 2026
DVWA
Prepared harmless markers
Kali terminal
Recorded MIME type, size and SHA-256
No malicious content used
28 Aug 2026
DVWA
Normal JPG upload
Firefox
Upload succeeded
Baseline established
28 Aug 2026
DVWA
Mismatch upload
Firefox
.jpg file containing plain text was accepted
Stored/retrieval behaviour recorded
28 Aug 2026
DVWA
Command baseline
Firefox
Normal localhost ping returned
Baseline established
28 Aug 2026
DVWA
Minimal command test
Firefox
Harmless marker appeared in response
No further exploitation performed
28 Aug 2026
Mutillidae II
Normal JPG upload
Firefox
File moved to /tmp/
Storage subsequently verified in container
28 Aug 2026
Mutillidae II
Mismatch upload
Firefox
File accepted; validation reported as not performed
Browser retrieval not demonstrated
28 Aug 2026
Mutillidae II
Command baseline
Firefox
DNS lookup of localhost succeeded
Baseline established
28 Aug 2026
Mutillidae II
Minimal command test
Firefox
Harmless marker appeared in response
No further exploitation performed
29 Aug 2026
DVWA
Changed security level
Firefox
Changed from Low to Impossible
Stronger-mode retest
29 Aug 2026
DVWA
Upload retest
Firefox
Mismatch rejected
Stronger validation observed
29 Aug 2026
DVWA
Command retest
Firefox
Modified input rejected as invalid IP
Stronger input validation observed

	
