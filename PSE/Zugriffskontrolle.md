# Zugriffkontrolle
- Konzepte um zu spezifizieren welcher Aufrufer was darf

## Zugriffsschutz
von am wenigsten zu am meisten zugreifbar
#### private
- Nutzbar innerhalb Klassrumpfs
#### default/package private
- Nutzbar aus Klassen innerhalb desselben Packages
#### protected
- Nutzbar innerhalb von Klassen im selben Package und Unterklassen
#### public
- Nuztbar von überall