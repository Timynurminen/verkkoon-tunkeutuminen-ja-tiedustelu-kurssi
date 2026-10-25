# h1-Korva-netissä

## x) Spektrini

<img width="949" height="556" alt="image" src="https://github.com/user-attachments/assets/f2b667da-5528-4c96-99a8-c8fc3fd5a001" />


Valitsin sovelluksia, joita käytän arjessa (FM-radio, Wi-Fi) sekä tämän kurssin aiheita (ADS-B).
Taajuuden kasvaessa aallonpituus lyhenee kaavalla λ = c / f, esim. FM 100 MHz -> noin 3 m ja Wi-Fi 2,4 GHz -> noin 12 cm.
Siksi matalien taajuksien antennit ovat isoja ja korkeiden pieniä.

**Oma huomio:** Läpäisevyys yleensä heikkenee taajuuden kasvaessa (Wi-Fi heikkenee seinien läpi), mutta röntgen on poikkeus: se läpäisee kehon, vaikka taajuus on erittäin korkea.

### Lähteet

- [Traficom: Radiotaajuusmääräys 4 AD/2023M, taajuusjakotaulukko](https://www.traficom.fi/sites/default/files/media/regulation/Radiotaajuusm%C3%A4%C3%A4r%C3%A4ys%204AD2023M.pdf) (AM-radio, 526,5–1606,5 kHz)
- [Traficom: Ilmailun navigaatio- ja valvontalaitestrategia (luonnos, päivitetty 2020)](https://traficom.fi/sites/default/files/media/regulation/Traficom%20Ilmailun%20navigaatio-%20ja%20valvontalaitestrategia_%20luonnos_%20p%C3%A4ivitetty%202020.pdf) (ADS-B, 1090 MHz)
- [ITU: Frequency Assignment Plans (GE84)](https://www.itu.int/en/ITU-R/terrestrial/broadcast/plans/pages/plans.aspx) (FM-radio, 87,5–108 MHz)
- [ETSI EN 300 328 V2.2.2 (Bureau Veritas, tiivistelmä)](https://www.cps.bureauveritas.com/newsroom/etsi-en-300-328-v222-will-become-mandatory-6th-august-2021) (Wi-Fi, 2400–2483,5 MHz)
- [Jyväskylän yliopisto: Säteilyn ja aineen vuorovaikutus](https://users.jyu.fi/~hejajama/ipho_valmennusmateriaali/s%c3%a4teily/s_teilyn_ja_aineen_vuorovaikutus.pdf) (näkyvä valo, röntgen)


## c) ADS-B.

Avasin ADS-B Exchange -palvelun (https://globe.adsbexchange.com/) ja valitsin Helsingistä lähteneen Finnairin koneen.


<img width="957" height="1297" alt="image" src="https://github.com/user-attachments/assets/d53fd23a-e52a-43db-a3a7-f8645e35159a" />

### Kone ja lento

- Lentotunnus: FIN1673
- Rekisteritunnus: OH-LXF
- Lentoyhtiö: Finnair Oyj
- Konetyyppi: AIRBUS A-320
- ICAO hex: 461F67
- Korkeus (barometrinen): 34 025 ft (n. 10,4 km)
- Maanopeus: 411 kt (n. 760 km/h)
- Suunta: 232,8°
- Lähde: ADS-B

Kone lähti Helsingistä ja lensi kaappaushetkellä matkalentokorkeudessa Itämeren yllä lounaaseen. ADS-B Exchange ei näyttänyt tälle lennolle määränpäätä. ADS-B-lähetys ei sisällä tietoa määränpäästä: kone lähettää vain tunnuksensa, sijaintinsa, korkeutensa, nopeutensa ja suuntansa.
Määränpään saisi selville muista lähteistä, esimerkiksi lentoyhtiön aikataulusta.

### Miten tiedot on saatu

1. Kone määrittää oman sijaintinsa satelliittipaikannuksella (GNSS).
2. Koneen transponderi lähettää tiedot automaattisesti taajuudella 1090 MHz (Mode S Extended Squitter).
   Tästä tulee nimi Automatic Dependent Surveillance - Broadcast: kone ei odota kyselyä, vaan lähettää tiedot kaikille.
3. Vapaaehtoisten maa-asemat (antenni ja SDR-vastaanotin) vastaanottavat lähetykset ja välittävät ne ADS-B Exchangelle.
4. ADS-B Exchange kokoaa datan kartalle. Tämän koneen viestit vastaanotti yli 7 maa-asemaa .

**Oma huomio:** Yllätti, että kuka tahansa voi seurata lentokoneita reaaliajassa, koska lähetykset ovat salaamattomia. Toisaalta lähetyksestä ei selviä, minne kone on menossa, joten määränpää pitää selvittää muualta.

**Lähteet**
- [ADS-B Exchange](https://globe.adsbexchange.com/)
- 
