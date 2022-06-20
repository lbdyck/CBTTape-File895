```
//***FILE 895 is from Rainer Nowak and contains some modifications  *   FILE 895
//*           to Gilbert Saint-flour's STEMEDIT program as well as  *   FILE 895
//*           some other things that are related.                   *   FILE 895
//*                                                                 *   FILE 895
//*           Please refer to CBT File 183 for Gilbert              *   FILE 895
//*           Saint-flour's materials.                              *   FILE 895
//*                                                                 *   FILE 895
//*           email:  rainer_nowak@gmx.de                           *   FILE 895
//*                                                                 *   FILE 895
//*                   Description of Contents                       *   FILE 895
//*                   ----------- -- --------                       *   FILE 895
//*                                                                 *   FILE 895
//*     For many years the CBT tape has been a great help for       *   FILE 895
//*     me. Usually I used the programs 'as is', but now a          *   FILE 895
//*     colleague wants a way to show him all the stem variables    *   FILE 895
//*     in a REXX exec.  OK, there's STEMEDIT in CBT tape file      *   FILE 895
//*     183, but this can only be used for stem variables like      *   FILE 895
//*     a.1, a.2 and so on.  One big advantage of REXX is, that     *   FILE 895
//*     you can use stem variables in the way like a. =0;do i=1     *   FILE 895
//*     to words(text);j=WORD(text,i);a.j=a.j+1;end . So you can    *   FILE 895
//*     count how many times a word is used in a text.  For such    *   FILE 895
//*     stem variables you can't use STEMEDIT.  So I changed        *   FILE 895
//*     STEMEDIT to VIEW and EDIT all variables in a REXX exec.     *   FILE 895
//*     You'll find the changed source in this file.                *   FILE 895
//*                                                                 *   FILE 895
//*     There are also two edit macros to be used with              *   FILE 895
//*     STEMEDIT.  Call STEMEMCB at the beginning of the edit       *   FILE 895
//*     session to change all '00'x in blanks and shift the '='     *   FILE 895
//*     to the left.  At the end of the edit session STEMEMCE       *   FILE 895
//*     should be called to end up the lines with '00'x.            *   FILE 895
//*                                                                 *   FILE 895
//*     I've also changed TALLY to work under z/OS 1.13.  I know    *   FILE 895
//*     you don't need TALLY anymore, because DSLIST now can do     *   FILE 895
//*     this for you.  But the idea behind TALLY is, to find        *   FILE 895
//*     the ISPF table used by DSLIST and use it for your own       *   FILE 895
//*     needs.  So I wrote DSL as an example, how to use this       *   FILE 895
//*     table.  In DSL you can exclude Datasets from the list,      *   FILE 895
//*     flip between excluded and visible and do HSM RECALL for     *   FILE 895
//*     all visible Datasets.  I hope these programs will be a      *   FILE 895
//*     help for someone.                                           *   FILE 895
//*                                                                 *   FILE 895
//*     CICSSUBS, IMSSUBS and MQSUBS list the active CICS, IMS      *   FILE 895
//*     and MQ systems on the lpar. For DB2 please have a look at   *   FILE 895
//*     DB2 update #124 February 2003, page 22ff.                   *   FILE 895
//*                                                                 *   FILE 895
//*     IS is a little CLIST to be used like this:                  *   FILE 895
//*     //SET1 SET ENV=TEST                                         *   FILE 895
//*     //TEST1 EXEC PGM=IKJEFT1A,                                  *   FILE 895
//*     // PARM='IS &ENV EQ PROD'                                   *   FILE 895
//*     //SYSTSPRT DD SYSOUT=*                                      *   FILE 895
//*     //SYSPROC DD DISP=SHR,DSN=YOUR.CLIST.DSN                    *   FILE 895
//*     //SYSTSIN DD DUMMY                                          *   FILE 895
//*     //* RC = 4                                                  *   FILE 895
//*     //TEST2 EXEC PGM=IKJEFT1A,                                  *   FILE 895
//*     // PARM='IS &ENV EQ TEST'                                   *   FILE 895
//*     //SYSTSPRT DD SYSOUT=*                                      *   FILE 895
//*     //SYSPROC DD DISP=SHR,DSN=YOUR.CLIST.DSN                    *   FILE 895
//*     //SYSTSIN DD DUMMY                                          *   FILE 895
//*     //* RC = 0                                                  *   FILE 895
//*                                                                 *   FILE 895
//*     Lionel B. Dyck send me a TSO help for STEMEDIT. I put       *   FILE 895
//*     this XMIT of a PO SYSHELP dataset to member TSOHELP.        *   FILE 895
//*                                                                 *   FILE 895
//*     To allocate a SYSHELP dataset before the existing           *   FILE 895
//*     allocation I put a REXX to do it in ALOCHELP, the name      *   FILE 895
//*     of the dataset should be given as parm.                     *   FILE 895
//*                                                                 *   FILE 895
//*     ILIBS is a REXX to show the concatination of datasets       *   FILE 895
//*     under the ISPF dd names including the datasets concatinated *   FILE 895
//*     with LIBDEF.                                                *   FILE 895
//*                                                                 *   FILE 895
//*     OLDS is a REXX I hope noone will ever need it. It shows     *   FILE 895
//*     IMS LogSequenceNumber errors in an OLDS. It can be used in  *   FILE 895
//*     3.4 DSLIST.                                                 *   FILE 895
//*                                                                 *   FILE 895
//*     STEMOUT is a shortened STEMEDIT, just to write all vars     *   FILE 895
//*     to a dataset, while you run the REXX in batch.              *   FILE 895
//*                                                                 *   FILE 895
//*     To allocate a SYSPROC dataset before the existing           *   FILE 895
//*     allocation I put a REXX to do it in ALOCPROC, the name      *   FILE 895
//*     of the dataset should be given as parm.                     *   FILE 895
//*                                                                 *   FILE 895
//*     RNREPEAT with panel RNREPEAP is a kind of a serial letter.  *   FILE 895
//*     With this Edit Macro, you can repeat lines and put in       *   FILE 895
//*     values from a PS dataset.                                   *   FILE 895
//*                                                                 *   FILE 895
//*     Rainer Nowak                                                *   FILE 895
//*                                                                 *   FILE 895
```
