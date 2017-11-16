# Provider Interface API 2.3

Leverantörsoberoende öppet API för effektivt systemsamarbete mellan tjänsteleverantörer (TL eller SP), öppna nät (ÖN) och kommunikationsoperatörer (KO eller CO).

API exponerar de accesser som ställs till förfogande för tjänsteleverantörer att leverera sina tjänster på. På de accesser som exponeras kan sedan transmissionsprodukter beställas, avbeställas och konsolideras.

Innehåller operationer med följande syften:
* Hämta säljdata/univers från KO.
* Beställa transmissionsprodukter hos KO.
* Hämta tekniska detaljer och status på aktiva transmissionsprodukter hos KO.
* Stöd för autoaktivering.
* Uppfyller GDPR.

## Innehåll

1. [Ändringar mot tidigare versioner](changelog.md)
2. [Feasibility API](feasibility.md)
3. [Availability API](availability.md)
4. [Service Activation API](service_activation.md)
5. [Order Events API](order_events.md)
6. [Option82 Lookup API](option82_lookup.md)
7. [Web Portal API](web_portal.md)
8. [FM Link Status API](fm_linkstatus.md)
9. [KO: Alla aktiva transmissionsprodukter](co_active_services.md)
10. [TL Kundinformations API](access_customer_info.md)
11. [TL: Sökning av beställda transmissionsprodukter](query_sp.md)
12. [Option82](option82.md)
13. [Övergripande](misc.md)

## Terminologi

### Access

En _Access_ definieras som en avlämningspunkt som måste aktiveras för att en slutkund skall få transmissionsprodukt. Utgörs typiskt av en port i en access-switch, förbindelsen till och uttaget i bostaden.

### Feasibility

_Feasibility_ definieras som lista med _accesser_ med tillhörande data för att unikt kunna identifiera accesser (adress, lägenhetsbeteckningar etc.) och vilka transmissionsprodukter som är potentiellt beställningsbara (per _access_). _Feasibility_ omfattar inte om transmissionsprodukterna är aktiva eller tillgängliga. _Feasibility_ används till säljkampanjer, täckningskartor och liknande. _Feasiblitity_ används även vid kontakt med slutkund för att identifiera vilken specifik _access_ som transmissionsprodukter skall aktiveras på.

### Availability

_Availability_ definieras som aktuell status på vilka transmissionsprodukter som är aktiva och vilka som går att leverera på en specifik access. _Availability_-frågor används ofta interaktivt, exempelvis under konversation med potentiell slutkund. KO kan med hjälp av _Availability_ indikera om en transmissionsprodukt är "upptagen" av en annan TL.

### Transmissionsprodukt

En _Transmissionsprodukt_ definieras som en transmissionsprodukt, vars realisation är unik. Det skall alltså endast finnas en transmissionsprodukt med samma nätkonfiguration. Det betyder att det inte får finnas olika tekniska transmissionsprodukter beroende på pris, bindningstid eller andra erbjudanden.
_Transmissionsprodukter_ skall även vara ortogonala mot andra tekniska transmissionsprodukter av annan transmissionsproduktetyp. Transmissionsproduktetyp är Bredband, Telefoni och TV. En _Transmissionsprodukt_ får inte avse mer än en transmissionsproduktetyp. Det betyder att det inte får finnas tekniska transmissionsprodukter som avser flera transmissionsprodukter, exempelvis "Bredband 10/10 + TV".
