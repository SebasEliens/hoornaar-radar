# Data sources for hornet-nest localisation in the Netherlands

Oct 2, 2026 · @Sebas Eliëns

Exact hornet and nest locations are open through the NDFF since February 2025. Removal dates and the beehive register are not open: removal data sits with provinces and their contractors, and beehive locations are best collected directly from beekeepers.

## 1. Hornet sightings, nests and removals

| Source | Holds | Location detail | Removal status | Access |
| --- | --- | --- | --- | --- |
| [NDFF – Flora & Fauna Verkenner](https://florafaunaverkenner.nl/) | Validated records from Waarneming.nl and other portals | Exact where entered with GPS; download per 5×5 km block or up to twelve 1×1 km blocks | No | Open, free since 11 Feb 2025; authorised access for more |
| [Waarneming.nl / Observation.org](https://waarneming.nl/) | Almost all Dutch hornet and nest reports | Exact on the platform | Not recorded systematically | Viewing open; bulk export of exact data: contact Observation.org |
| [GBIF – Observation.org dataset](https://doi.org/10.15468/5nilie) | Same records, validated | Netherlands aggregated to 5×5 km | No | Open download (non-commercial licence) |
| Provincial removal records | Nests removed by contracted pest controllers, by date and type | Exact | Yes | Request from the province; Woo request as fallback |
| [Hoornaarspotter app](https://www.hoornaarspotter.be/) | Nests found by search teams, marked empty after removal | Exact | Yes | Via provincial coordinators or search-team leads |
| Municipal records | Nests on public land, council answers | Street level | Often | Woo request or council documents |
| NVWA | Notified of removals under some provincial protocols | Unknown | Yes | Woo request |
| [Vespa-Watch (Flanders)](https://www.vespawatch.be/en) | Nests with treatment status; validated records on GBIF weekly | Exact | Yes | Open map; GBIF download |

**NDFF.** Since 11 February 2025 the NDFF can be consulted free of charge, without a subscription. Only species on the Lijst Kwetsbare Soorten are blurred to 1×1, 5×5 or 10×10 km squares; the Asian hornet is not expected to be on that list (check before relying on it). Authorised access, structural or one-off, goes only to organisations that can show they need more detail. Open question: whether the export carries Waarneming.nl's activity field (nest vs. individual).

**Removal records.** Removal is logged outside Waarneming.nl. In Gelderland, search teams log found nests in the Hoornaarspotter app and log them again as empty after removal; in Noord-Brabant the NVWA is informed once a nest has been removed. Zuid-Holland has already released a 2024 table per municipality (nest counts, success rate, nest type, density) under a Woo request.

**Vespa-Watch.** Flanders destroyed every active reported nest until 1 November 2022. That makes its earlier data an unusually complete removal record for calibration.

## 2. Beehive locations

| Source | Holds | Location detail | Access |
| --- | --- | --- | --- |
| [RVO apiary register (UBN)](https://www.rvo.nl/onderwerpen/identificatie-en-registratie-dieren/ubn-bijen-hommels) | Every keeper's wintering site on 1 February, colony count in bands (1–10, 11–20, 21–30, 31+) | Address or coordinates | Not available: use restricted to contagious-disease outbreaks |
| Beekeepers' own records | Where each hive stood and when, including summer and pollination sites | Exact | With the keeper's consent |
| [NBV](https://www.bijenhouders.nl/) and local beekeeping clubs | Members willing to host detectors | Exact, by recruitment | Partnership |
| Amsterdam municipal register | Hives registered under a local ordinance | Unknown | Ask the municipality |
| [FAVV register (Belgium)](https://www.bthenet.eu/practices/je-bijenstand-en-kolonies-registreren-labelen/) | Permanent apiary locations | Exact | Not public; relevant only for border areas |

**RVO register.** Since 1 January 2025 every keeper, hobbyists included, must register each wintering location with RVO and receives a UBN for it. Only the location on 1 February is registered; summer moves stay in the keeper's own administration. The ministry and RVO have committed to using the register only for contagious disease outbreaks. Because it holds personal data, a Woo request for it is unlikely to succeed.

**Keepers' own records.** Keepers must keep a record per hive of where it has stood. Partner beekeepers can therefore supply hive histories for past seasons, which lets you pair historic nest removals with the hives nearby.

## 3. Context layers for the spatial prior

All of these are open national datasets distributed through [PDOK](https://www.pdok.nl/), most of them under CC0 / public-domain terms.

| Dataset | Use in the model | Access |
| --- | --- | --- |
| AHN (Actueel Hoogtebestand Nederland) | Tree and canopy height from lidar: where secondary nests can hang | Open download via PDOK; AHN1 and AHN2 open since 6 March 2014 |
| BGT (Basisregistratie Grootschalige Topografie) | Detailed land cover (scale 1:500–1:5,000): trees, hedges, water, roads | Open via PDOK services and GML download |
| BAG (Basisregistratie Adressen en Gebouwen) | Buildings: primary-nest habitat | Open via PDOK |
| BRT / TOP10NL | Coarser topography for quick prototypes | Open via PDOK |
| BRP Gewaspercelen | Crop parcels: open farmland with few nest sites | Open via PDOK |

## 4. Access steps, in priority order

1. **Download the open data first.** Pull Asian hornet records from the Flora & Fauna Verkenner and the Vespa-Watch GBIF data, plus the PDOK layers. This needs no approval and is enough to build and test the simulation (Section 8 of the system documentation).
2. **Ask NDFF what the open export holds.** Confirm the coordinate precision for *Vespa velutina* and whether nest records can be told apart from individuals. If the open export falls short, apply for authorised access: a one-off delivery or structural access through your organisation, with a written justification of why the extra detail is needed.
3. **Contact the provinces' exotic-species coordinators.** Ask for removal records (location, removal date, nest type, primary or secondary) for 2023–2025. Start with Zeeland, Noord-Brabant and Zuid-Holland, which have the densest records. Offer the model's outputs in return; provinces are actively looking for better detection methods.
4. **Fall back on a Woo request** if a province does not cooperate. It is free, can be filed by post or e-mail, and must be decided within 4 weeks, extendable by 2. Ask for existing documents only (contractor reports, spreadsheets), since a Woo request cannot oblige a body to create new data. Expect personal data to be redacted.
5. **Approach search-team coordinators** for Hoornaarspotter exports. These teams hold the most precise found-and-removed records but are volunteers, so a data-sharing agreement with the coordinating province is the cleanest route.
6. **Recruit partner beekeepers** through the NBV and local clubs. Ask each for current hive locations and, from their hive records, past locations with dates. Put consent and data use in writing, since hive locations are personal data.
7. **Contact Observation.org** only if NDFF access fails, to ask whether a research export of exact Dutch records is possible.

## Sources

- [NDFF open data and access levels](https://ndff.nl/natuurdata/open-data/)
- [Rijksoverheid: NDFF free to consult from 11 February 2025](https://www.rijksoverheid.nl/actueel/nieuws/2025/02/11/nationale-databank-flora-en-fauna-voortaan-vrij-toegankelijk-voor-iedereen)
- [NDFF: obtaining and using data](https://www.ndff.nl/hetnatuurloket/abonnement/)
- [GBIF: Observation.org dataset description](https://www.doi.org/10.15468/5nilie)
- [Province of Noord-Brabant: Asian hornet protocol (draaiboek)](https://open.brabant.nl/public/download/b0ee6aa0-2d94-4053-a2e4-b023b2533809/54_202207%20Draaiboek%20Aziatische%20hoornaar_geanonimiseerd.pdf)
- [Province of Noord-Brabant: approach document, reports via Waarneming.nl](https://open.brabant.nl/public/download/ac6a8071-df69-43d4-96bc-4f195a2cd310/39_Aanpak%20Aziatische%20hoornaar_geanonimiseerd.pdf)
- [NBV: Gelderland detection and control procedure](https://mijn-nbv.bijenhouders.nl/l/mailing2/link/e8315082-6550-4b2b-bab5-60ead302b7a6/5796)
- [Province of Zuid-Holland: Woo decision on Asian hornet control, part 8](https://www.zuid-holland.nl/publish/besluitenattachments/besluit-op-woo-verzoek-bestrijding-aziatische-hoornaar/samengevoegde-definitieve-stukken-aziatische-hoornaar-deel-8.pdf)
- [INBO: Vespa-Watch dataset](https://www.vlaanderen.be/inbo/en-gb/data-applications/vespa-watch)
- [INBO: Vespa-Watch management module (September 2025)](https://www.vlaanderen.be/inbo/en-gb/news-september-2025/vespa-watch-launches-new-management-module/)
- [INBO: Asian hornet in Flanders project](https://vlaanderen.be/inbo/en-GB/projects/aziatische-hoornaar-in-vlaanderen-uitbreiden-en-ondersteunen-vespa-watch-platform-en-onderzoek-naar-beheermaatregelen)
- [RVO: UBN for bees and bumblebees](https://www.rvo.nl/onderwerpen/identificatie-en-registratie-dieren/ubn-bijen-hommels)
- [NVWA: administrative obligations for beekeepers](https://www.nvwa.nl/onderwerpen/dier/bijen-en-hommels/administratieve-verplichtingen-bij-het-houden)
- [NBV: frequently asked questions on registration](https://www.bijenhouders.nl/veelgestelde-vragen/)
- [AHN: downloading from PDOK](https://www.ahn.nl/_flysystem/media/handleiding_ahn_downloaden_van_pdok.pdf)
- [Rijksoverheid: what happens after a Woo request](https://www.rijksoverheid.nl/onderwerpen/wet-open-overheid-woo/vraag-en-antwoord/wat-gebeurt-er-nadat-ik-een-woo-verzoek-heb-ingediend)
