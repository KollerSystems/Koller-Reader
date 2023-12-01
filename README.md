# Koller-Reader

Kártyaolvasó forráskódja a Koller-hez.

### mifare olvasó beállítása

Az olvasóhoz írt programkód egy **Waveshare PN532 NFC HAT**-hez lett írva, így egy raspberry pi is kell hozzá.

A HAT-et fel kell konfigurálni *SPI* használatára, ehhez a [weboldalukon](https://www.waveshare.com/wiki/PN532_NFC_HAT) utasítások találhatók. A használt raspberry pi-n engedélyezni kell az *SPI*-t.

Ezek után klónozzuk a raspberry pi-n ebből a repository-ból a reader mappát, és a `config.json` fájlban állítsuk be a szükséges értékeket, hogy a raspberry pi az API szerverrel *websocket* kapcsolaton keresztük kommunikálhasson, illetve a használandó A&B kulcsokat amiket használni fog működése során.

A két fájl, `setupTags.py` és `resetTags.py` segítheti az mifare biléták beállítását, illetve *transport* konfigurációba való helyezését. Beállításhoz futtatni kell a `setupTags.py` fájlt, és megadni egy *csv* formátumú fájl elérési útvonalát. Ebben a fájlban a kulcsok sorrendjében írja a bilétákat, amelyek *transport* konfigurációban vannak.

Az olvasó használatához ezek után futtatni kell a `main.py` fájlt, de csak miután **fut az API szerver**.