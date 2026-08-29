# Lab 2 Activity Log

  ----------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Date        Application   Activity            Tool/Method        Result / Observation          Notes
  ----------- ------------- ------------------- ------------------ ----------------------------- -----------------------------------------------------------------------
  28 Aug 2026 DVWA / Lab    Prepared harmless   Kali terminal      Recorded MIME type, file size Markers contained no malicious or executable content
                            marker files                           and SHA-256 hashes            

  28 Aug 2026 DVWA          Normal JPG upload   Firefox            Upload succeeded              Baseline established

  28 Aug 2026 DVWA          JPG retrieval       Firefox            Uploaded image was retrieved  Content-delivery behaviour recorded
                                                                   successfully                  

  28 Aug 2026 DVWA          Prepared mismatch   Kali terminal      `lab2-mismatch.jpg`           38 bytes; SHA-256 recorded
                            marker                                 identified as `text/plain`    
                                                                   despite `.jpg` extension      

  28 Aug 2026 DVWA          Mismatch upload     Firefox            Mismatched file was accepted  Filename/content validation weakness observed

  28 Aug 2026 DVWA          Mismatch retrieval  Firefox            File could not be displayed   Consistent with plain-text content rather than a valid JPEG
                                                                   because it contained errors   

  28 Aug 2026 DVWA          Command baseline    Firefox            `127.0.0.1` returned normal   Baseline established
                                                                   ping output                   

  28 Aug 2026 DVWA          Minimal             Firefox            Harmless command marker       Testing stopped after minimal proof
                            command-injection                      appeared in the response      
                            proof                                                                

  28 Aug 2026 Mutillidae II Registered a lab    Firefox            Account successfully          Used only for authorised lab access
                            account                                registered                    

  28 Aug 2026 Mutillidae II Normal JPG upload   Firefox            File was moved to             Storage path recorded
                                                                   `/tmp/lab2-marker.jpg`;       
                                                                   validation reported as not    
                                                                   performed                     

  28 Aug 2026 Mutillidae II Storage             Docker/container   File existed; MIME type was   Verified server-side storage
                            verification        terminal           `image/jpeg`; SHA-256 matched 
                                                                   original marker               

  28 Aug 2026 Mutillidae II Mismatch upload     Firefox            `lab2-mismatch.jpg` was       Filename/content mismatch observed
                                                                   accepted and moved to         
                                                                   `/tmp/`; validation reported  
                                                                   as not performed              

  28 Aug 2026 Mutillidae II Browser retrieval   Firefox            No clickable retrieval link   Storage was verified through the container instead
                            attempt                                was provided                  

  28 Aug 2026 Mutillidae II Command baseline    Firefox            DNS lookup of `localhost`     Baseline established
                                                                   returned normal DNS results   

  28 Aug 2026 Mutillidae II Minimal             Firefox            `ICDFA-LAB2-MUT-CMD-MARKER`   Testing stopped after minimal proof
                            command-injection                      appeared in the response      
                            proof                                                                

  29 Aug 2026 DVWA          Changed security    Firefox            Security level changed from   Stronger-mode retest initiated
                            level                                  Low to Impossible             

  29 Aug 2026 DVWA          Upload retest       Firefox            Same `lab2-mismatch.jpg` was  Response:
                                                                   rejected                      `Your image was not uploaded. We can only accept JPEG or PNG images.`

  29 Aug 2026 DVWA          Command-injection   Firefox            Modified input was rejected   Response: `ERROR: You have entered an invalid IP.`
                            retest                                                               
  ----------------------------------------------------------------------------------------------------------------------------------------------------------------------

## Testing Principles

-   Testing remained within the authorised local lab environment.
-   Harmless marker files were used for upload testing.
-   Command-injection testing used non-destructive marker commands only.
-   No malware or executable payloads were used.
-   No destructive commands were executed.
-   No persistence, privilege escalation, external callbacks or
    unrelated-file access were attempted.
-   Testing stopped once the required behaviour was demonstrated.

## Outstanding Cleanup Record

The final cleanup/reset checks are intentionally left to be completed
after the evidence package has been preserved. The final record should
document removal of learner-created markers, application reset, and
verification that no listener, persistence mechanism, temporary
assessment account or other learner-created artefact remains.
