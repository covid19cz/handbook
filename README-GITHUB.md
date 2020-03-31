**GitBook**
- SUMMARY.md je TOC (Obsahový) soubor, podle něhož GitBook generuje obsah. Případné nové MD soubory musí být referencované v něm.
- README.md soubor je nutné zachovat - GitBook ho vyžaduje jako úvodní stránku.
- Je (bohužel) nutné zachovat aktuální adresářovou strukturu.
- Automatická obousměrná synchronizace s https://app.gitbook.com/@covid19cz/s/covid19cz/ (viz https://docs.gitbook.com/integrations/github)
  - GitBook má trochu nešťastný systém konverze médií. 
  - Všechny obrázky z _img_ složky si naimportuje do .gitbook/assets a při jakékoliv editaci v GitBook nahradí všechny reference ve všech .md souborech (a změny pošle do GitHub). To rozbije obrázky všude mimo GitBook.
  - Soubory obrázků v repozitáři ale zůstanou na svém místě, takže je možné odkazy nahradit zpět na _img_ a dokola se takto z GitBookem "přetahovat".
  - Workaround by mohl být GitHub workflow, který automaticky reference při commitu nahradí.

**Pro info: původní konverze z gDoc**
- Postup konverze z gDoc:
  - gDoc > Download > Docx
  - hrubá konverze pomocí pandoc
`pandoc -s '..\prirucka.docx' -t markdown -o prirucka_docx.md --extract-media=media_docx`
  - TUNA ruční editace formátování a testování na privátním GitBook space
- **Masivnější synchronizace s původním gDoc je v podstatě nemožná, toto se tedy nově stává hlavním zdrojem.**