# Lab 2 Evidence Register

  -----------------------------------------------------------------------
  Evidence ID       Application       Test/Action       Evidence
                                                        Description
  ----------------- ----------------- ----------------- -----------------
  E-001             Both              Marker            Marker file
                                      preparation       properties, MIME
                                                        types, sizes and
                                                        SHA-256 hashes

  E-002             DVWA              Normal upload     Normal JPG upload
                                                        result

  E-003             DVWA              Retrieval         Successful
                                                        browser retrieval
                                                        of uploaded JPG

  E-004             DVWA              Mismatch          Mismatched JPG
                                      preparation       marker properties

  E-005             DVWA              Mismatch upload   DVWA response to
                                                        the mismatched
                                                        file

  E-006             DVWA              Mismatch          Browser response
                                      retrieval         when retrieving
                                                        the mismatched
                                                        file

  E-007             DVWA              Command baseline  Normal
                                                        ping/command
                                                        response

  E-008             DVWA              Command execution Harmless command
                                                        marker execution

  E-009             Mutillidae II     Normal upload     Normal JPG upload
                                                        response

  E-010             Mutillidae II     Storage           Container
                                      verification      verification of
                                                        stored JPG, MIME
                                                        type and SHA-256
                                                        hash

  E-011             Mutillidae II     Mismatch upload   Mismatched file
                                                        accepted;
                                                        application
                                                        reported
                                                        validation was
                                                        not performed

  E-012             Mutillidae II     Command baseline  Normal DNS lookup
                                                        response

  E-013             Mutillidae II     Command execution Harmless command
                                                        marker execution

  E-014             DVWA              Security-mode     DVWA changed from
                                      change            Low to Impossible

  E-015             DVWA              Secure upload     Mismatched file
                                      retest            rejected at
                                                        Impossible

  E-016             DVWA              Secure command    Modified command
                                      retest            input rejected at
                                                        Impossible
  -----------------------------------------------------------------------

## Marker Details

  ---------------------------------------------------------------------------------------------------------------------------------
  File                  Actual MIME Type                  Size SHA-256
  --------------------- ---------------- --------------------- --------------------------------------------------------------------
  `lab2-marker.txt`     `text/plain`                  25 bytes `f074db25e1f60353354b98970ad32b234d50d80fc611a177541ef44e1b92928a`

  `lab2-marker.jpg`     `image/jpeg`              31,140 bytes `679e180f69354c5f92fb79dc28ebe9fa26a806b193f76e1b82cd6286c2f54237`

  `lab2-mismatch.jpg`   `text/plain`                  38 bytes `77bc5f316accbbabd9c9e848a07c8f70aa655650487d5fdef7f6251587f2d989`
  ---------------------------------------------------------------------------------------------------------------------------------

## Key Observations

### File Upload

-   DVWA Low accepted the filename/content mismatch.
-   The mismatched file was subsequently retrievable, but it could not
    be displayed as a valid image because its content was plain text.
-   Mutillidae II accepted the mismatch and reported:
    `Validation not performed`.
-   Mutillidae II stored the normal JPG and the mismatch under `/tmp/`
    using the supplied filenames.
-   Container verification confirmed that the normal Mutillidae JPG had
    MIME type `image/jpeg` and the same SHA-256 hash as the original
    marker.

### Command Injection

-   DVWA's normal command baseline successfully processed `127.0.0.1`.
-   A harmless command marker appended to the input appeared in the
    response at Low.
-   Mutillidae II's normal DNS lookup for `localhost` returned normal
    DNS results.
-   A harmless command marker appended to the Mutillidae DNS lookup
    input appeared in the response.
-   At DVWA Impossible, the modified command input was rejected with
    `ERROR: You have entered an invalid IP.`

## Stronger-Mode Comparison

  -----------------------------------------------------------------------
  Test                    Weaker Mode             Stronger Mode
  ----------------------- ----------------------- -----------------------
  File upload             Mismatched `.jpg`       Mismatched `.jpg`
                          accepted                rejected

  Command execution       Harmless marker         Modified input rejected
                          executed                
  -----------------------------------------------------------------------

## Evidence Handling Note

This register records the evidence that was documented during the
assessment. It should not be interpreted as claiming that raw HTTP
request/response exports were captured where they were not. The
submission package should contain the actual files that exist in the
final evidence directory.
