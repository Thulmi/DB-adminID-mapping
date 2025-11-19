# Mapping von DB adminID auf zugehörige Betreibernamen
In den Schnittstellen der Deutschen Bahn werden Betreiber von Bus- und Bahnlinien oft mit einem Betreiberkürzel `adminID` angegeben. 
In den Schnittstellenspezifikationen der RIS-APIs lässt sich ein guter Anfang einer mapping-Liste finden, auf dem diese Datei beruht. (Ich hoffe das ist in Ordnung die zu nutzen, wenn nicht gerne Bescheid geben!)

## Aufbau der Datei:
Es handelt sich um eine semikolongetrennte csv-Datei mit den folgenden Spalten:
1. `adminID`: Die adminID, wie sie in den Schnittstellen angegeben ist. Sollte in der Regel nicht verändert werden, wenn der Eintrag bereits existiert. 
2. `DB_operator_code`: Das Betreiberkürzel, wie es in den Schnittstellen angegeben ist. Sollte in der Regel nicht verändert werden. 
3. `DB_operator_name`: Der Betreibername, wie er in den Schnittstellen angeben ist. Sollte in der Regel nicht verändert werden. 
4. `DB_subnet_name`: Die Bezeichnung des genauen (Teil-)Netzes, wie sie in den Schnittstellen angegeben ist. In der ursprünlichen Liste findet sich diese Information nicht, sie kann allerdings aus Antworten der DB RIS-APIs als `operatorName` herausgelesen werden und ist insbesondere für Teilnetze der verschiedenen DB Regio Tochterfirmen interessant.
5. `custom_short_name`: Die geläufige Kurzform des Betreiberunternehmens (z. B. "KVB" für "Kölner Verkehrsbetriebe AG", "Bahnen Monheim" für "Bahnen der Stadt Monheim GmbH"). Muss manuell ergänzt werden und ist insbesondere für ÖPNV-Unternehmen interessant, die von der DB nur als "DPN - Nahreisezug" geführt werden).
6. `custom_long_name`: Die offizielle Langbezeichnung des Betreiberunternehmens mit Rechtsform (z. B. "Kölner Verkehrsbetriebe AG" für "KVB", "Bahnen der Stadt Monheim GmbH" für "Bahnen Monheim"). Muss manuell ergänzt werden und ist insbesondere für ÖPNV-Unternehmen interessant, die von der DB nur als "DPN - Nahreisezug" geführt werden).
7. `comment`: Kommentar zum jeweiligen Eintrag, z. B. Linien für die eine adminID bisher beobachtet wurde, falls Unsicherheiten bestehen.

## Sonstiges
Mir ist noch kein guter Weg eingefallen, um verschiedene Niederlassungen kenntlich zu machen. Stand jetzt würde ich es als Kommentar ergänzen. Falls jemand eine bessere Idee hat, gerne vorschlagen!

Danke für Eure Mithilfe! :)
