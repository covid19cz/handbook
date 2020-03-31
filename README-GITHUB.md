**GitBook**
- Automatická obousměrná synchronizace s https://app.gitbook.com/@covid19cz/s/covid19cz/ (viz https://docs.gitbook.com/integrations/github)
- README.md soubor je nutné zachovat pro GitBook - vyžaduje ho jako úvodní stránku.
- GitBook má trochu nešťastný systém konverze médií. 
  - Všechny obrázky z _img_ složky si naimportuje do .gitbook/assets a při jakékoliv editaci v GitBook nahradí všechny reference ve všech .md souborech (a změny pošle do GitHub). To rozbije obrázky všude mimo GitBook.
  - Soubory obrázků v repozitáři zůstanou na svém místě, takže je možné odkazy nahradit zpět na _img_ a dokola se takto z GitBookem "přetahovat".
  - Workaround by mohl být GitHub workflow, který automaticky reference při commitu nahradí.

**Pro info: původní konverze z gDoc**
- Postup konverze z gDoc:
  - gDoc > Download > Docx
  - hrubá konverze pomocí pandoc
`pandoc -s '..\prirucka.docx' -t markdown -o prirucka_docx.md --extract-media=media_docx`
  - TUNA ruční editace formátování a testování na privátním GitBook space
- **Masivnější synchronizace s původním gDoc je v podstatě nemožná, toto se tedy nově stává hlavním zdrojem.**