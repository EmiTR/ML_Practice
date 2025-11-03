KMeans _Clustering

Dieses Repository enthält ein Analyseprojekt zur K-Means-Clustering-Analyse am Beispiel von Online-Retail-Daten.
Ziel ist es, Kundenverhalten zu segmentieren, Erkenntnisse zu gewinnen und daraus realistische Handlungsempfehlungen abzuleiten.

I. Inhalt des Repositories

- Kmeans_Customers_Segmentation.ipynb
  Jupyter Notebook mit Implementierung des K-Means-Workflows: Datenaufbereitung, Auswahl geeigneter K-Werte, Clustering-Logik und Visualisierung.
  Entscheidungen sowie Überlegungen sind in den Kommentaren dokumentiert, sodass jeder Schritt transparent nachvollziehbar ist.

- Kmeans_steps.txt
  Übersicht über die Schritte, die im Notebook durchgeführt werden.

- online_retail_II.xlsx
  Datensatz mit Transaktionsdaten aus dem Bereich Online-Handel.

- requirements.txt
  Enthält alle benötigten Python-Pakete (z. B. pandas, scikit-learn, matplotlib), um das Notebook lokal lauffähig zu machen.

- .venv/
  Virtuelle Umgebung für die lokale Entwicklung (in .gitignore ausgeschlossen).

II. Zusammenfassung: K-Means Kunden-Clustering
1. Ziel der Analyse

Wir wollten verstehen, wie sich unsere Kunden anhand ihres Kaufverhaltens unterscheiden lassen.
Mit Hilfe von K-Means Clustering wurden Kundengruppen (Segmente) gebildet, die ähnliche Eigenschaften teilen.
Das ermöglicht gezieltere Marketing- und Produktentscheidungen.

2. Vorgehen

Datenbasis: Transaktionsdaten aus dem Online-Handel (Bestellungen, Häufigkeit, Umsatz etc.).

Kennzahlen: Für jeden Kunden wurden drei zentrale Dimensionen berechnet:

- Recency – Wie lange liegt der letzte Kauf zurück?
- Frequency – Wie oft kauft ein Kunde?
- Monetary Value – Wie viel Umsatz bringt ein Kunde?

Clustering: Mit dem Algorithmus K-Means wurden Kunden automatisch in Gruppen eingeteilt.

Interpretation & Handlungsempfehlung: Jede Kundengruppe wurde beschrieben und ihre Bedeutung fürs Geschäft eingeordnet. Auf Basis der RFM-Werte wurden Handlungsempfehlungen formuliert.

3. Ergebnisse

Es wurden 7 Kundensegmente identifiziert:

- 4 Gruppen für „normale“ Kunden (non-outliers)
- 3 Gruppen für Kunden mit besonders hohem Umsatz (outliers)

Outliers (sehr umsatzstarke Kunden) sollen gezielt gehalten werden.

Möglicher Business Impact:

- Gezieltere Maßnahmen: Marketingbudgets können auf wertvolle Kundengruppen fokussiert werden.
- Wachstumspotenzial: Umsatzsteigerung vor allem durch Stammkundenpflege und Rückgewinnung ehemals aktiver Käufer.
- Effizienzsteigerung: Weniger Budgetverlust bei wenig lohnenden Kundengruppen.

III. Weiterentwicklung

Die Analyse basiert auf Transaktionsdaten eines Online-Shops, in dem Kunden wiederholt Bestellungen aufgeben können.
Dieses Modell ist jedoch nicht auf jedes Geschäftsmodell übertragbar.

Beispiel:

- Versandhandel: Wiederholungskäufe und Nachbestellungen sind typisch.
- Banken/Finanzdienstleister: Ein Kreditkunde kehrt nicht regelmäßig zurück, um das gleiche Produkt erneut abzuschließen. Hier spielen andere Faktoren wie Prolongation (Vertragsverlängerung) oder Cross-Selling eine größere Rolle.

Für jedes Geschäftsmodell müssen also geeignete Metriken neu definiert werden. Ein Beispiel mit Finanzdienstleister-Daten wird in einer separaten Analyse behandelt.
