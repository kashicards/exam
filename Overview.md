```dataview
table status as "Status"
from "03-Knowledge/Exam/Prüfungsvorbereitung/schriftlich"
where status
flatten regexreplace(file.name, "^[Uu](\\d+).*", "$1") as unit
sort regexmatch("^U\\d", file.name) desc, (status = "erledigt") desc, number(unit) asc, file.name asc
```

