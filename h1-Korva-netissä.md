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


## a) WebSDR

### Vastaanottimen valinta

Avasin sivun websdr.org, jossa on lista ympäri maailmaa sijaitsevista ohjelmaradioista (SDR, software defined radio), joita voi kuunnella selaimella. Valitsin Twenten yliopiston lyhytaaltovastaanottimen Enschedessä, Alankomaissa.


<img width="1270" height="1285" alt="image" src="https://github.com/user-attachments/assets/399a8aab-0a5e-45c4-a097-a5651b8c56e0" />

### Kanavan etsiminen

1. Klikkailin vesiputousnäkymästä vahvoja signaaleja. Kirkkaat pystyviivat ovat lähettimiä.
2. Kokeilin eri modulaatioita ja huomasin, että AMsync-tilassa 16 metrin kaistalta kuului selkeä AM-lähetys.
3. Kun kanava löytyi, vaihdoin tavalliseen AM-tilaan. Kaiuttimista kuului selkeää puhetta, mutta en saanut kielestä kiinni.
4. Pyöristin taajuuden tasan 17485.00 khz:iin, koska yleisradioasemat ovat 5 khz:n välein.

Signaalin voimakkuus oli -53,5 dBm.

<img width="1133" height="674" alt="image" src="https://github.com/user-attachments/assets/1d9676c8-3ce3-4727-aa55-91a80ef6baa5" />


### Aseman tunnistus

Hain taajuuden short-wave.info palvelusta. 

<img width="744" height="96" alt="image" src="https://github.com/user-attachments/assets/6b112589-405a-4f1e-a8eb-f0af6fdb90b1" />

Tuloksena:

<img width="765" height="31" alt="image" src="https://github.com/user-attachments/assets/a4db9bc3-6df8-4276-a514-712f2103fa2f" />

**Oma huomio:** Mielenkiintoista oli, että arabiankielinen radiolähetys tulee Kiinasta. Lähetys oli suunnattu arabiankielisille kuuntelijoille, mutta se kuului silti hyvin Alankomaissa asti.

## b) Moduwhat?

Käytin samaa Twenten yliopiston WebSDR-vastaanotinta kuin a-kohdassa.

### Kanavan etsiminen

1. Kokeilin ensin 20 metrin kaistaa USB-tilassa, mutta en löytänyt sieltä oikein mitään.
2. Siirryin 40 metrin kaistalle (7100-7200 khz) ja valitsin LSB-tilan.
3. Klikkailin vesiputouksesta signaaleja ja säädin taajuutta.
4. Taajuudelta 7150 khz kuului puhetta (varmaankin espanjaa).

<img width="1133" height="674" alt="image" src="https://github.com/user-attachments/assets/ae90b989-d92a-4be0-9aac-fdf7685d2133" />


### Tulokset:

<img width="1147" height="586" alt="image" src="https://github.com/user-attachments/assets/cec1f1a2-6552-4a29-9292-fdc4e31668d9" />


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
- [Traficom: Radiotaajuusmääräys 4 AD/2023M, taajuusjakotaulukko](https://www.traficom.fi/sites/default/files/media/regulation/Radiotaajuusm%C3%A4%C3%A4r%C3%A4ys%204AD2023M.pdf) (AM-radio, 526,5–1606,5 kHz)
- [Traficom: Ilmailun navigaatio- ja valvontalaitestrategia (luonnos, päivitetty 2020)](https://traficom.fi/sites/default/files/media/regulation/Traficom%20Ilmailun%20navigaatio-%20ja%20valvontalaitestrategia_%20luonnos_%20p%C3%A4ivitetty%202020.pdf) (ADS-B, 1090 MHz)
- [ITU: Frequency Assignment Plans (GE84)](https://www.itu.int/en/ITU-R/terrestrial/broadcast/plans/pages/plans.aspx) (FM-radio, 87,5–108 MHz)
- [ETSI EN 300 328 V2.2.2 (Bureau Veritas, tiivistelmä)](https://www.cps.bureauveritas.com/newsroom/etsi-en-300-328-v222-will-become-mandatory-6th-august-2021) (Wi-Fi, 2400–2483,5 MHz)
- [Jyväskylän yliopisto: Säteilyn ja aineen vuorovaikutus](https://users.jyu.fi/~hejajama/ipho_valmennusmateriaali/s%c3%a4teily/s_teilyn_ja_aineen_vuorovaikutus.pdf) (näkyvä valo, röntgen)
- [WebSDR](http://websdr.org/)
- [Short-wave.info](https://www.short-wave.info/index.php)
- [University of Twente WebSDR](http://websdr.ewi.utwente.nl:8901/)
