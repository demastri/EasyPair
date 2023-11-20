files
    main
        globals - fileWriter / lineSeparator / locale / captions (ResBundle)
        Main() - constructor
        main(String[]) - entry point
            params are xx YY filename
                xx YY correspond to locale strings in file like JavaPairing_xx_YY.properties
                    should be <= 2 chars each...
               filename is a FIDE tournament report to be "checked"
            sets userLocale, LookAndFeel
            uses the global createLocale to write the default properties file from the ones given by the file above
            otherwise just open the JavaPairing resource bundle
            if a filename to check is given, calles initializeTournament with it
            else tries to initialize a blank tournament
                ? shows modal to determine what to init ?
            show the EntryForm!
        scanComponents(Container)
            for each element in the container, 
                get titles (really content) and 
                if creating a locale, write text 
                otherwise get the appropriate text
        registerText(String)
            builds a "key" from the first 40 non-punctuation characters of text
            writes the key and value to fOut
        localizedText(String)
            builds a "key" from the first 40 non-punctuation characters of text
            looks in "captions" for a string with that key as a localized version

    enterframe.java
        enterframe.form (graphical representation)
        Looks like a commmon panel using embedded JPanels for
            Control (at top - jPanel1)
            Registration
            Rounds
            Results
            Output

    initializeTournament
        show modal to select individual / team / open existing tournament