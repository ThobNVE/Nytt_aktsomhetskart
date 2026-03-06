# Nytt aktsomhetskart for flom
For oppbygging av grunnmodellen til NVEs nytt aktsomhetskart for flom.
Scripten ble testet i vassdrag nr. 122, "Gaula", Trondheims-region.

Før du begynne å bruke, må du:
1. Oppsett et Anaconda-python system.
2. Bygg conda miljøet med Python_GIS.yml (i /envs/)
3. Aktivere Python_GIS miljøet (i powershell hvis du bruker jupyter, eller i VS Studio/ annet Python programvare)
4. Åpne hovedscripten "Nytt_aktsomhetskart.ipynb" i /Scripts/ med VSCode, jupyter eller lignende programvare.

Det er krav for å ha spesifikk mappesystem for det å fungere.
Mappesystem er som følges:
>/HOVED MAPPE/

>            > /BURNED/       # For DTM innbrent med elvdata som .tif filer

>            > /ELV/          # For Elvenettdata produsert av DTM.

>            > /FLD/          # Flomområder

>            > /RNET/         # Invertert elvenettverk for innbrenning og geometri endring

>            > /FLOWACC/      # For Flow Accumulation .tif filer

>            > /OUT/          # For DTM som er skalert til et valgt oppløsning

>            > /RAW/          # For raw 1 m DTM data lastet ned fra geonorge

>            > /FDIR/         # For strømretning data 

>            > /Scripts/      # For scriptene, både .ipynb og .py

>            > /Skalering/    # For test-scripts for skaleringsmetodikk (ikke nødvendig hvis skalerings-script eksisterer i /Scritps)

>            > /envs/         # For Python miljø .yml (ikke nødvendig)

# Senere kan scriptene bransje ut med utvikling av bedre metodikk.

# Neste steg med grunn-scripten:

# Må gjøres: 

Test av ProbHAND metoden.

Test av høyere oppløsningsdata (e.g. 5m, for 1m er litt komplisert).

En løsning for problemer som kommer fra små sideelv/NBF

# Kan testes:

Effekt av vannregulering og broer.

Innsjøer kan også inkluderes.

Infiltrasjonsverdier med jordbruksdata.

Forbedring av vannstandstignings-beregninger.

Implementering av «flomusikkerhet» på kanten av aktsomhetsområder.

Investigasjon om vifter.

Ulike gjentaksintervaler.

+ 1:50, 1:100, 1:200, 1:500 ?

Lokale klimaer/regimer: Snø / Bre o.s.v.

«Flomregimeregioner»: 

+ teste «best-sak» parametere for f. eks: Innlandet, Nord, Øst, Sør, Vest Norge.

# Hensyn til lagringsplass
Flere av filene i scripten trenger opp til 1GB lagringsplass per .tif fil. Videre, trenger "raw-dtm" mellom 10 - flere hundre GB lagringsplass for å laste ned i 1m oppløsning.
Ta hensyn på lagringsplassen deres, og jobbe med bare ETT vassdrag per brukssak.

