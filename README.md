# RMA-DZ5 <h1>WhereIsDaniel?</h1>
<p>
Za ovu zadaću je bilo potrebno napraviti aplikaciju koja korištenjem lokacije na karti prikazuje trenutni položaj korisnik markerom,
te ispisuje na ekran u TextView lokaciju, adresu, grad i zemlju u kojoj se korisnik nalazi. Osim toga omogućiti korisnikovo postavljanje
markera drugačije ikone bilo gdje na kartu te prilikom dodavanja markera pustiti zvuk preko SoundPool klase. Kada aplikacija pronađe 
trenutnu korisnikovu lokaciju moguće je kliknuti na gumb pri čemu se otvara kamera te slikanjem sprema sliku pod imenom trenutne lokacije
i korisniku se šalje notifikacija te klikom na notifikaciju se otvara ta slika u galeriji. Potrebno je zapakirati i potpisati aplikaciju
ključem u trajanju od 50 godina.</p>
<p>Prilikom izrade aplikacije koristio sam se predlošcima sa laboratorijskih vježbi kolegija „Razvoj mobilnih aplikacija“. Jedan od
problema se stvarao kada uređaj promjeni orijentaciju iz vertikalne u horizontalnu ili obrnuto, activity se resetira te se podaci izgube
(pronađena lokacija, korisnikovo postavljanje markera) taj problem sam riješio jednostavno dodavanjem u manifest datoteku jedne linije
koda koja sprečava resetiranje activitya koju sam pronašao na stranici:
https://developer.android.com/guide/topics/resources/runtime-changes.html#HandlingTheChange

Za postavljanje različitih markera za pronađenu lokaciju korisnika i markera za odabranu lokaciju korisnika sam se poslužio unaprijed 
definiranim standardnim markerima koji su objašnjeni na stranici:
https://developers.google.com/android/reference/com/google/android/gms/maps/model/BitmapDescriptorFactory .

Za pokretanja kamere i spremanje nove datoteke(slike) na određenu lokaciju pod određenim imenom pomogao sam se sadržajem na stranici: 
http://stackoverflow.com/questions/12995185/android-taking-photos-and-saving-them-with-a-custom-name-to-a-custom-destinati

te je u manifest datoteci pored dozvole za Internet, pristup (finoj) lokaciji potrebno dozvoliti i pisanje po memoriji
("uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE") 

Za otvaranje slike klikom na notifikaciju pomogao sam se sadržajem na:
http://stackoverflow.com/questions/5383797/open-an-image-using-uri-in-androids-default-gallery-image-viewer .
Jedini problem koji nisam uspio riješiti je što nisam mogao implementirati zvuk unutar aplikacije preko SoundPool klase,
nego sam to napravio preko MediaPlayer klase.
Prilikom zakljucavanja aplikacije u gradle(app) je potrebno dodati multiDexEnabled = true jer je se zakljucavanje rušilo .
</p>
