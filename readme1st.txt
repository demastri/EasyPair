JavaPairing - rev. 2.9 - September 2015
 
This is a tool to manage a chess tournament, team or individual (you can set 
teams of one player only! -;), i.e. player registration, round generation, results,
ranking & crosstable, report to Federation and WEB page generation.

I decided to start this work because of some unsatisfaction with commercial software,
need to workaround some bugs, to overcome some unpleasant restrictions i.e. to allow
late entrant & quickly handle reserves, to improve the user interface, to flow and
speed up the work of the arbiter and finally, if desired, to allow players to meet
more than once.
The open source philosophy has been adopted, so anyone may contribute with some 
piece of code and see what the software really does!
Anyway, I did it to contribute to chess success worldwide.

The program is currently developed with 
     - NetBeans IDE 7.0.1 (http://www.netbeans.org/downloads/)
     - Java Runtime Environment (JRE) 1.6 from Sun Microsystems Inc. 
       (http://java.sun.com/javase/downloads/index.jsp)
Also, the two tools are available in bundle (http://java.sun.com/javase/downloads/netbeans.html)
 
The distribution can run as is on any platform, including Windows, Linux and Macintosh, 
only needed is Java support (JRE 1.6 or more).

Expand the '.zip' file to your hard disk, maintaining the subfolder structure.
Execute the 'JavaPairing.jar' file in the 'dist' subfolder. By default the program
speaks English, but local languages are easily handled by substituting strings at
runtime. You have to supply the 'JavaPairing_xx.properties' file with translations
where xx is the language code (see 'i18n' folder for details). Pack your language 
file into the .jar and start. 
Italian, French and German translations are already available! If available, a non 
native language may be invoked specifying xx and YY as parameters at startup, where
YY is the country code (i.e. to see Italian outside of Italy, specify 'it IT').

To modify the program, open the installation folder with NetBeans (File/OpenProject ...),
browse to the root installation folder and click 'Open Project Folder',
then expand the tree to 'Source Packages'/'javapairing', double click 'EnterFrame.java'.

Player data can be read from any commonly distributed text database. A filter should 
be easily build, after that you can drag&drop (or double-click) players into the grid.
Filters for FIDE, Italian and German Chess Federations are included.

Pairing systems implemented are:
- swiss Dutch (endorsed by FIDE)
- swiss Dubov (under endorsment by FIDE)
- swiss Simple (based on rating)
- swiss Pefect Colours (it is a must to alternate the colours!)
- Amalfi Rating (system approved by FSI and under evaluation of FIDE) 
- round robin, based on Berger tables
- 'by hand'. The program helps you much ranking the players or teams and highlighting 
  previous opponents and colour constrains. Colour optimization may be obtained.

Output is produced in HTML format; may be directly printed or sent to the preferred 
browser (highly suggested). Report to Federation and WEB site are generated too.
JavaPairing data files are portable on every operating system, without using 
conversion tools.

In the same folder of this file (readme1st.txt) you will find:
- The license (gpl-3.0-standalone.htm)
- about the author
- The JavaPairing User Manual
- 'i18n' folder
  - info on internationalization of the program
  - the language and country codes to use to name the language file
  - some localized files 
- 'TOURNAMENTS' folder
  - some real tournament files, may be loaded by the program
- 'test' folder
  - some test/simulation tournament files, may be loaded by the program
- 'DATABASES' folder
  - some schemata to import player data from FIDE & FSI distributions
  - some FIDE & FSI distributions (.txt, .csv)
- 'REPORTS' folder
  - specifications for report to FED generation
  - some report samples
- 'AMALFI' folder
  - rules and test examples of Amalfi Rating algorithm
  - info on JavaPairing implementation of this system
- 'SWISS' folder
  - FIDE rules for swiss pairing systems
  - info on JavaPairing implementation of this system
- 'ROUND ROBIN' folder
  - some related documents
- 'KEIZER' folder
  - some related documents ... maybe implemented in the future. I, don't know.

I think the program is already fine tuned to be used in any tournament, under 
arbiter's responsibility.
If you like this program and use it to administer real tournaments, a donation to 
the "Bobby Fischer" chess club of Cordenons - Italy will be greatly appreciated.
Donation is intended to be a self financing method for the standard activities of 
the chess club and to improve it. As well as, this will stimulate me to continue 
the software development. Updates, mailing list and quick bug fix are guaranteed 
to registered users.
For bank transfer 
		A.S.D. Circolo Scacchi Cordenons 
		c/o B.N.L. Pordenone
		IBAN: IT86 N 01005 12500 000000000299
		SWIFT: BNLIITRR
Depending on national law, free donation to sport associations may be tax deducible.
The receipt may be requested, please write to the email address.

for contact: Eugenio Cervesato. eucerve@tin.it  mobile (+39) 338 5960366

*********************************************************************************

improvements / bug fix log after rev. 1.0

rev. 2.9 - September 2015

032 topic: improvement; general

    - fixed bug rounding Elo variation
    - fixed bug generating FIDE report (half point bye)
    - fixed bug reading FIDE report (half point bye)

rev. 2.8 - September 2014

031 topic: improvement; engine

    - Improved the Swiss Dutch Engine for computational complexity when in a big group
      even the "split according the color due" workaround does not work
    - Improved the TRF FIDE import when in the same round more BYE than one happen 
      (the last one read is kept if odd. Others are assumed to be half-point-bye or 
      full-point-bye. Warning! This may cause a checker error!)
    - Improved the checker and the cross table generation as stated at previous point

030 topic: improvement; general

    - Updated Elo FIDE calculations to rules dated 1st july 2014. K=40/20/10

rev. 2.7 - November 2013

	*** 'SWISS DUTCH' PAIRING ENGINE ENDORSED BY FIDE !! ****

rev. 2.6 - June 2013

029 topic: improvement; general

    - Improved the Swiss Dutch Engine (aligned to Istanbul 2012. bug C.1, X and Z)
    - Improved read/write FIDE report (aligned to Istanbul 2012. forfeit with colour)
    - Improved cross table and statistics
    - Added import of teams from a .csv file (the team name shall be on the previous 
      field of that containing the player names and on its own record; a filter has 
      to be prepared regarding the player record. Data is loaded by specifying '*' 
      in the 'Load player from database' field)
    - Now it is possile to blank the player's name in insert results of a team 
      tournament (i.e. to put 2-0f, no board)
    - Improved FIDE report import
    - It is now possible to batch check FIDE reports, specifying the file name as a
      startup parameter.
    - It is possible to import player's data up to 5 files at a time.

rev. 2.5 - February 2013
the endorsment procedure restarts

028 topic: improvement; general

    - Developed the checker to test a FIDE report against the Dutch engine (checkbox
      in the 'open tournament' window)
    - Improved the Swiss Dutch Engine (aligned to Istanbul 2012)
    - Computational complexity better handled
    - Removed auto acceleration of the swiss (new check box in the setup window)
    - Fixed a bug in ranking with assignment of 1/2 point to the BYE
    - Updated lower FIDE Elo limit to 1000

rev. 2.4 May 2012

027 topic: improvement; general

    - Improved the Swiss Dutch Engine
    - Result 0-0 is now allowed. For adjourned games use 1/2-1/2
    - Updated K=30 to estimate the tranche FIDE for unrated players
    - Improved mouse click on the tables

rev. 2.3 March 2012

026 topic: improvement; engine

    - Improved the Swiss Dutch Engine for extreme situations.
    - Added 'Verbosity Level' to the 'explain' window (the text is also saved to the
      'log.txt' file, coded "UTF-8". It may be needed to specify this coding when
      opening the file with a text editor or a wordprocessor to see up and down 
      floater constrains represented by up and down arrows)
    - Reporting score brackets theese simbols are used:
      w  = colour due white
      b  = colour due black
      w? = colour due mild white but can change (rule A7.e)
      b? = colour due mild black but can change (rule A7.e)
      W  = colour due absolute white
      B  = colour due absolute black
      W? = colour due absolute white but can change (rule A7.d)
      B? = colour due absolute black but can change (rule A7.d)
      .  = no colour preference
      -  = no floater constrain
      up arrow   = upfloater constrain   (rule B5 then B6)
      down arrow = downfloater constrain (rule B5 then B6)

rev. 2.2 November 2011

025 topic: improvement; general

    - Added a tournament simulator with parametrization. To enter digit 'simulation'
      in the field 'Load player from database' of the 'Registration' page
    - fixed Buchholz Kallithea bug (two or more unplayed games)

024 topic: improvement; engine

    - Fixed some bugs of the swiss Dutch and Dubov engines. 
    - Added improvements to avoid factorial complexity. Anyway, it is not excluded
      the need to abort the engines in extreme situations where calculation takes
      a very long time. If this occur, please try to pair the round with a different
      engine

rev. 2.1 August 2011

023 topic: improvement; engine

    - Swiss Dutch algorithm has been improved to prevent factorial complexity in a
      large group with unbalanced colours (sample from 'Città di Cordenons 2011';
      round 2; group 1; x=2; p=18)
    - bug fix Dutch pairing algorithm ('sample from Mario Held 14_5'; round 4; group 5);
      when x=0 strict remove floats first, then the strict flag. 
    - bug fix colour assignment
    - bug fix final order pairs
    - improved colour due explanation

022 topic: improvement; general

    - Thanks to Georges Marchal <gmarchal (at) scarlet.be> added the French 
      translation of the program!
    - Code updated for NetBeans IDE 7.0
    - Elo FIDE calculations updated to rules valid from 1st July 2011
    - Buchholz calculation updated to Kallithea Congress 2009
    - can read (import) FIDE report

021 topic: improvement; output

    - Improved printer pagination of board cards and player cards.
      Remember to use the 'send to browser' button and do 'print preview' on that!
      You can fine tune pagination adjusting the 'number of rows per page' field.
      If this call does not work in your PC, directly open the file 'temp.html'.
      And, if available, use the zoom factor to reduce ink and paper waste.

rev. 2.0 January 2011

020 topic: improvement; general

    - A dialog has been added at the startup to quickly allow to select
      individual tournament/team tournament/open existing file.
    - Added player cards.
    - Added 'Weighted Boards' tie-break for team tournaments. Individual results
      are multiplied by a board coefficient (1.9 - 1.7 - 1.5 - 1.3 ... 0.1) then 
      added together.
    - Improved graphics and icons.
    - A facility to merge two tournament file has been added to allow:
      a) to build large open tournaments registering players from different
         PCs and then merging data,
      b) to reuse old tournament file,
      c) to convert team to individual tournament.
      A checkbox field has been added to the 'open tournament' window at the 
      right side. It is available if a tournament is in memory (read/written)
      and no rounds are yet generated (or they are completely removed).
      n.b. To export player's data it is suggested to use the 'report to
           FED' procedure.
    - According to FIDE rules, delta performance for score 0% is now -800.
    - Added flag 'F' for Elo FIDE

rev. 1.9 December 2010

019 topic: improvement; output

    - Elo variation page has been extended taking into account games between 
      Fide rated players (for both k=25 and 15). For the others the 'tranche FIDE'
      is calculated if applicable. 

018 topic: improvement; engine

    - improved messages on due colour and constrains (colour and floats)

rev. 1.8 November 2010

017 topic: improvement; engine

    - completed development of the 'swiss Dutch' engine. It passes three test
      tournaments: NORDICWC, TU_29_11 and TU_31_13, can exchange S1<->S2 for 
      any number of elements.

rev. 1.7 October 2010

016 topic: improvement; engine

    - started development of the 'swiss Dutch' engine with the goal to be full
      compliant to FIDE official rules. At the moment it passes three test
      tournaments: NORDICWC, TU_29_11 and TU_31_13, but obviously could not 
      pass other tests ...
      The current implementation can exchange S1<->S2 for one element at a time 
      and the last two of S1 with the first two of S2.

rev. 1.6 July 2010

015 topic: improvement; general

    - added report to German Federation
    - for schema to import players from a variable length fields database it is
      allowed to specify the character '|' to join two fields and the character
      '-' to extract only the first part of a field (introduced to read German
      database format of the file SPIELER.TXT) 
    - added sorting capability of teams/players in the 'Registration' grid.
      Can be done by clicking on the column header or by using the right button
      of the mouse. It is allowed until the first round is built
    - fixed a bug on the 'ritired' flag for individual tournaments
    - cross tables present now the current round instead of '-BYE' if results are 
      missing, by using the symbol '?'. For team tournaments the holders are
      temporarily paired. For tie break it is correct to consider a not yet played 
      game as BYE. To have the ranking at the last really played round, go to the
      'Rounds' page and decrease the round counter 
    - fixed a bug on partial ranking by age
    - improved the layout of the text obtained by the 'copy as plain text' in the
      'Output' page

rev. 1.5 June 2010

014 topic: improvement; general

    - completed the user manual
    - added the 'implementation of the Swiss' document in the folder 'SWISS'
    - added the German translation of the program and of the user manual
    - added some tests
    - improved the graphic user interface
    - improved import schema handling 
    - added option to load as a whole players from an own database
    - fixed a bug in TPR calculation
    - replaced the nonsense tie-break 'Not Played Games' with 'Score %', coherently
      calculated with the so called 'FIDE rule' ((sum of points in played games + 
      draw for BYE)/number of rounds*100) even if it is not completely convincing.
      Then a win due to BYE or Forfeit scores half point less.
    - added the Board number in the 'Results' page
    - added a button to abort the engine

rev. 1.4 May 2010

     WARNING: previously saved files need to be modified, inserting an empty row 
              after "... // max Players per Team" and before of 
              "...   // total Teams entered", by using a text editor. 
              This procedure creates a row for tie-break criteria storage.

013 topic: improvement; engine
    Problem:
      Amalfi rating algorithm did not exclude absent players.
    Solution:
      Amalfi rating algorithm now correctly exclude absent players from pairing list 

012 topic: improvement; general
    - the max number of Teams is now 500
    - added icon 'Reset' in front of the 'Load player from database' field 
    - in the same field are now handled <Enter> and <Del> keys
    - in the list is now reported the status of the search if negative
    - latecoming pairing has been improved
    - tie-break criteria is selectable in the setup page
    - non standard results are correctly handled
    - IDs are reported on ranking
    - output has been improved by adding page breaks. To evaluate it use the
      'send to browser' button and do 'print preview' on that

rev. 1.3 March 2010

011 topic: improvement; output
    Problem:
      Missing FSI-Italia report.
    Solution:
      Added FSI-Italia report and modified the program to allow easy national implementations.

010 topic: improvement; output
    Problem:
      Missing alphabetic list of Teams/Players.
    Solution:
      Added alphabetic list of Teams/Players after list by IDs.
      Also, ID assignment at first round has been improved.

009 topic: improvement; engine
    Problem:
      Dubov implementation did not fulfill specifications about sorting players.
    Solution:
      Now 1.st half (colour due White) is ordered by increasing ARO, increasing 
      Rating and alphabetically; 2.nd half (colour due Black) is ordered by 
      decreasing Rating, decreasing ARO and alphabetically (rule 6.2 first part).
 
rev. 1.2 January 2010

008 topic: improvement; engine
    Problem:
      It happens in a swiss tournament, especially if there is a wide range
      of playing strengths, that two or more teams (players) may finish with 
      perfect scores. This especially apply if the number of teams (players) is 
      greater than 2 elevated the number of rounds to play.
    Solution:
      Acceleration of the swiss tournament was introduced if the number of teams
      (players) top scored is grater then 2 elevated the number of rounds left to 
      play, excluding the last round.
      The aim is to pair the higher graded (ie "top half") players together, and 
      then to use the top half non-winners to wipe out the 100% scores of "bottom 
      half" players as quickly as possible. Acceleration ceases when this is 
      achieved or when there is only one round left, whichever comes first. 
      The system assumes that lower graded players will not repeatedly beat higher 
      graded players. Like any probability-based system, it can be upset by a 
      sequence of unlikely results. This does not alter the fact that in the long 
      run it is the system most likely to avoid joint winners on 100%.
      Acceleration is invoked automatically, there is no option in the setup. 
      If you need to force acceleration, reduce the number of rounds to play.
      To exclude acceleration, increase the number of rounds to play.

007 topic: bug fix; engine
    Problem:
      Dutch system revealed instable mainly if colour constrains are to be removed.
    Solution: 
      The algorithm for selection of a heterogeneous score group was fixed.
      Permutations due to color constrains were optimized.

006 topic: improvement; output
    Problem:
      Scores were not shown on rounds.
    Solution:
      Current round output now shows scores. 

005 topic: bug fix; other
    Problem:
      Sometimes report to FED and WEB site were not generated.
    Solution:
      A control on file extension was added.

rev. 1.1 November 2009

004 topic: improvement; output
    Problem:
      Output is generated in HTML, that is great for printing and WEB publishing,
      but I need to have plain text too, i.e. to prepare a non standard report to FED.
    Solution:
      A new button was added 'copy as plain text', that composes a plain text from 
      HTML and copies it to the clipboard, so you may paste it in a text editor.
      The quality of conversion is quite good, better than you can do by yourself 
      with standard copy/paste on each item! The procedure is optimized for screen 
      resolution 1024x768.

003 topic: improvement; printing
    Problem:
      In each board card it is not reported the round number.  
      This may cause some confusion mixing board cards on the arbiter desk.
    Solution: 
      In each board card it is now clearly reported the tournament title and the 
      current round number.  

002 topic: bug fix; printing
    Problem:
      'send output to printer' obtain unpleasant zoom factor.
      This is the main reason why a 'send output to browser' was added, so in their
      print preview some browsers offer a resize facility.
    Solution: 
      Thanks to a modification of Jan Michael Soan PrintMe class (www.jmsoan.com),
      the printing procedure was personalized setting the paper size to A4, margins
      at about one centimeter and a dynamic scale factor to correct the problem.

001 topic: improvement; engine
    Problem:
      For Dubov and Dutch swiss systems, an extreme situation was found in a real 
      tournament when the score group becomes too much heterogeneous (i.e. at the 
      6th round of a tournament with 10 teams, because of many pairs broken, a score 
      group with 8 teams is generated, ranging from 8 to 0 points!!).
      In this situation the normal swiss 'S1 vs S2' may alter the tournament and 
      secondary prizes win! 
      This seems to be a problem related to swiss systems, not to the implementation.
      In fact, other programs fall too!
    Solution: 
      I inserted a suggestion to temporary switch to Amalfi rating system, because it
      proceed sequentially and can obtain more homogeneous pairs.

*********************************************************************************
