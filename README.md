# Harjoitus 3

Tässä harjoituksessa oli tarkoituksena perehtyä Git:n, ja siinä ohessa myös GitHubiin, käyttämiseen muutamien perustoimintojen avulla sekä asentaaa Saltin avulla minionille jokin (uusi) ohjelma. Tämä harjoitus perustuu Tero Karvisen pitämään Palvelinten Hallinta kurssiin, sekä harjoituksen että kurssin tarkemmat tiedot löytyvät hänen verkkosivuiltaan TeroKarvinen.com ([linkki](http://terokarvinen.com/2020/configuration-managment-systems-palvelinten-hallinta-ict4tn022-spring-2020/)). Git ja GitHub eivät olleet minulle entuudestaan täysin tuntemattomia. GitHubiin olin tunnuksen tehnyt jo aiemmalla Linux Palvelimet kurssilla ja Git:in käyttöön olimme hieman perehtyneet Haaga-Helian Ohjelmointi 2 kurssilla. Tiesin siis hieman noista tässäkin harjoituksessa käytettävistä peruskomennoista ennestään.


Käytettävät laitteet
- Asus VivoBook Pro N552VX kannettava tietokone Xubuntu 18.04 LTS, dualboot sisältää sekä Xubuntu 18.04 LTS että Windows 10 (olen tämän dualbootin asennuksen käynyt läpi artikkelissa, jonka päivitän tähän vielä jälkeenpäin)
- Oracle VirtualBox virtuaalikone, jossa käytössä Xubuntu 18.04 LTS
- Logitech MX518 hiiri

Käytin tässä harjoituksessa Oraclen VirtualBoxissa luotua virtuaalikonetta, jonka olin jo luonut aiemmasssa harjoituksessa 2 ([linkki](https://teemuaittomaki.wordpress.com/2020/04/15/palv-hallinta-h2/)). Virtuaalikoneelle en ollut asentanut Xubuntua, vaan käytin sitä "Try Xubuntu" toiminnon avulla, tällöin sain harjoituksen jälkeen helposti pyyhittyä kaiken puhtaaksi ja aloitettua seuraavan harjoituksen alusta. Huom. virtuaalikoneen kello on aikavyöhykkeellä UTC 00, eli kolme tuntia Suomen aikaa jäljessä (Suomessa käytessä harjoituksen teko hetkellä kesäaika).

Vaikka olinkin Git:n ja GitHubiin ennen tätä harjoitusta hieman tutustunut, niin lukaisin niiden tarkemmista määrittelyistä hieman täst git-scm.com sivuston ([linkki](https://git-scm.com/)) kuvauksesta sekä Wikipedian artikkelista ([linkki](https://en.wikipedia.org/wiki/GitHub)). Git on ilmainen ja avoimeen lähdekoodiin perustuva version hallintajärjestelmä ja GitHub taas tarjoaa hosting-palvelun Git:iä hyödyntävässä ohjelmistokehityksessä.

### Aloitin harjoituksen 20.4.2020 klo 14:08.


## Tee tämän tehtävän raportti MarkDownina

Tässä ensimmäisessä tehtäväosiossa tarkoituksena oli harjoitella MarkDownin käyttöönottoa ja käyttää sitä koko raportin kirjoittamiseen (nuo alustustekstit kirjoitin LibreOffice Writellä). MarkDown ei ollut minulle entuudestaan tuttu, joten tutustuin siihen hieman näistä GitHubin ohjeista ([linkki 1](https://guides.github.com/features/mastering-markdown/) ja [linkki 2](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)) avulla. MarkDownilla (.md päätteinen tiedosto) pystyy kirjoittamaan tekstiä, johon yksinkertaisilla lisäyksillä saa lisättyä verkossa näkyvät muotoilut, esim. #  lisää H1 tason otsikon, ## taas H2 tason otsikon jne., ja - pystyy tekemään tyyliteltyjä bullet-point listoja. MarkDown tiedostoihin pystyy myös upottamaan linkkejä.

Ennen Git:n asennusta vaihdoin näppäinasettelun suomalaiseksi sekä päivitin pakettitiedot ajantasalle. Gitin asennukseen ja käyttöön ottoon käytin hyödyksi tätä Tero Karvisen ohjetta ([linkki](http://terokarvinen.com/2016/publish-your-project-with-github)) asiasta, siinä käydään myös läpi GitHubin luodun repositoryn liittäminen Gitiin.

**setxkbmap fi**

**sudo apt-get update**

**sudo apt-get install git -y**

Gitin asennuksen jälkeen kirjauduin Githubiin tunnuksillani sisään ja tein sieltä uuden repositoryn klikkaamalla pääsivun vasemmasta yläkulmasta "New" painiketta. Tmän jälkeen pääsin varsinaiseen luonti osuuteen. "Owner" kohdassa näkyy oma käyttäjätunnukseni, tämän viereisessä kentässä määritellään repositoryn nimi. Annoin tässä sen nimeksi "harj3", joka totta kai viittaa harjoitus 3:n. Mielestäni on järkevää antaa jokin projektia kuvaava nimi, helppo itse hahmottaa mihin mikäkin repository liittyyä ja jos useampi henkilö työskentelee sen kanssa, niin selkeä nimeäminen vähentää epäselvyyksiä. "Description" kohdan jätin tyhjäksi, jossain "oikeassa" projektissa siihen kannattaisi varmastikin laittaa muutama oleellinen asia projektiin liittyen. Seuraavaksi määriteltiin oliko repository julkinen (Public) vai yksityinen (private), valitsin nyt tässä harjoituksessa yksityisen, koska ei ole tarkoituksenakaan, että kukaan muu näkisi tätä. Vaikka olisin valinnut julkisen vaihtoehdon, niin pystyisin silti määrittelemään kuka tähän pystyisi osallistumaan. "Initialize this repository with a README" kohdan jätin valitsematta, koska halusin luoda README-tiedoston koneella itse. Lopuksi klikkasin "Create reporsity" painiketta, jonka jälkeen tuli vielä "Quick setup" sivu, jossa ylimpänä oli linkki luomaani reporsitoryyn (jonka liitän Gitiin) ja muutama neuvo alkuun pääsemiseksi.

Siirryin takaisiin Gitiin, jossa määrittelin siihen käyttäjätiedot, näitä olivat sähköpostiosoite sekä käyttäjänimi. Määrittelin lisäksi että Git muistaa GitHubiin liittyvän salasana tunnin ajan (aika ilmoitettu sekuntteina, 3600 sekunttia), jotten joudu tuota salasanaa joka kerta kirjoittamaan uudestaan, kun esim. päivitän GitHubin harj3 reporsitoryyn tekemiäni muutoksia.

**git config --global user.email "<lisää-tähän-sähköpostiosoite>"**

**git config --global user.name "määritä-tähän-nimi"**

**git config --global credential.helper "cache --timeout=3600"**

Seuraavaksi liitin GitHubissa olevan reporsitoryn linkin Gitiin.

**git clone https://github.com/<tässä-github-ja-repository-osoitteesi>**

Tämän jälkeen tuli pyyntö syöttää GitHubin käyttäjätunnus sekä salasana. Tietojen syöttämisen jälkeen kotihakemistoon oli muodostunut harj3 kansio tästä GitHubissa luodusta repositorystä. Eli tuohon kansioon liittyvät tiedostot pystyi jatkossa helposti päivittämään GitHubiin ja vastakkain GitHubista pystyi myös lataamaan/päivittämään uudet ja muuttuneet tiedot tähän paikalliseen kansioon.

Seuraavaksi loin README.md (tiedostomuotu siis MarkDown) tiedoston, johon lisäsin alkuun vain "Harjoitus3" tekstin, testaamista varten. Lisäsin **add** toiminnolla (luin näistä toiminnoista tarkemmin Gitin man sivuilta) tämän tiedoston päivitettävien listalle ja **commit -m** toiminnolla toimonnolla hyväksyin tämän päivityksen "Started a readme" kommentin kera (**-m** määrittelee tuon kommentin lisäämisen) ja lopuksi uploadasin (push) päivityksen GitHubiin. Tästä tuli kuittauksena tieto siirrosta, joka vaikutti kaiken perusteella onnistuneen.

**echo "Harjoitus3" >> README.md**

**git add .**

**git commit -m "Started a readme"**

**git push**

Tarkistin vielä GitHubista näkyikö tämä README.md tiedosto sielläkin ja sisälsikö sen tuon Harjoitus3 tekstin. Tiedosto oli siirtynyt GitHubiin onnistuneesti, siinä näkyi kommentti "Started a readme" ja se sisälsi "Harjoitus3" tekstin.
Nyt kun tiesin yhteyden ja siirron Gitin ja GitHubin välillä toimivan, siirryin kirjoittamaan tätä raporttia Gitillä ja luomallani README.md tiedostolla. Avasin toisen välilehden komentoterminaaliin, johon avasin nanolla tuon readme tiedoston ja kopion jo kirjoittamani raportti sisällön siihen. Muotoilin jo tässä vaiheessa muutamia kohtia, kuten otsikot (alkuun erinnäinen määrä #-merkkejä riippuen otsikosta), komennot (lihavoin nämä, komennon alkuun ja looppun **-merkit) ja linkit (linkkiteksti []-merkkien väliin ja itse verkkosivu heti perään ()-väliin, jolloin []-välissä oleva sana toimii hyperlinkkinä kyseisellä verkkosivulle), käytin muotoilussa apuna tätä GitHubin ohjetta ([linkki](https://help.github.com/en/github/writing-on-github/basic-writing-and-formatting-syntax)).

Muotoilut tehtyäni ja tallennettuani tiedoston, päivitin GitHubiin. Siirto Gitin mukaan näytti onnistuvan. Siirryin siis GitHubiin ja tarkistin asian. Tekstit sekä muotoilut olivat päivittyneet onnistuneesti, myös verkkosivuille (lähteet siis) tehdyt linkitykset toimivat oikein.

**git add .**

**git commit -m "Report start included"**

**git push**

Nyt kopion vielä tähän harjoitukseen liittyvät kuvat tuohon harj3 kansioon, jotta nekin siirtyisivät suoraan GitHubiin aina raportin (readme tiedosto) päivityksen yhteydessä. Kopioinnin jälkeen päivitin ne vielä GitHubiin ja tarkistin GitHubista, että siirto oli onnistunut ja että kuvat avautuivat. Siirto onnistui ja kuvat avautuivat myös, eli tämänkin osalta homma toimi.

**cp /home/xubuntu/Pictures/*.png /home/xubuntu/harj3/**

**git add .**

**git commit -m "Report and pictures"**

**git push**


## Näytä omalla git-varastollasi esimerkit komennoista ‘git log’, ‘git diff’ ja ‘git blame’, selitä tulokset

Tässä tehtäväosiossa tuli kokeilla git komentoja **git log**, **git diff** ja **git blame** omalle git-varastolle, eli tälle jonka tässä harjoituksessa nyt loin.

Alkuun kokeilin **git log** komentoa. Se toi selkeästikin lokitiedot Gitissä tapahtuneista commit:sta. Siinä ilmeisesti commit:lle annettu tunniste (pitkä merkkisarja), commit:n tekijän nimi eli käyttäjätieto joka Gitin käyttöönotossa luotiin, commit:in päivämäärä ja kellonaika sekä commit:lle annettu selite. Tässäkin mielessä huomaa, että tuon selittään on hyvä olla jollakin tapaa informatiivinine, se helpottaa selkeästi jos jälkeenpäin tulee noita lokeja tarkastella. Luin vielä gittutorial man sivulta, että tuon **git log** tiedot juurikin kertovat tiedot noista tehdyistä commit:sta.

Seuraavaksi kokeilin **git diff** komentoa, mutta se ei tuonut mitään tietoa. Luin siis taas tuolta **man gittutorial** sivulta siitä lisätietoa. Selvisi että tuo komento listaa muutokset joita tehty Git kansioon, mutta ei vielä **add** toiminnolla lisätty. Tallensin siis tähän readme tiedostoon lisäämäni raporttitiedot ja kokeilin **git diff** komentoa uudestaan.

Nyt komentoterminaaliin tuli tietona raporttiin kirjoittamani tekstit, joita ei vielä ollut **add** toiminnolla lisätty päivitettävien listalle. Vihreällä tekstillä näkyi päivittämätön teksti ja sen yläpuolella näkyi harmaalla jo päivitetty materiaali. Tämä komento vaikutti varsin kätevältä, jos olisi tarkoitus esim. vain osa tiedoista siirtää kyseissä vaiheesa päivitettävien listalle, niin tällä vaikuttaisi saavan helposti hyvän kokonaiskuvan mitä on siirtämättä (eli ei käyttäisi **add .** toimintoa joka lisää kaiken, vaan **add tiedosti7**).

Viimeisenä kokeilin **git blame** komentoa. Lukasin siitä hieman Gitin man sivuilta, se näyttää halutusta tiedostosta kuka ja mitä siitä on viimeksi muokattu (heh, nyt tajuan blame, ketä pääsee siis syyttelemään). Katoin siis README.md tiedostoa **git blame README.md** komennolla. Sillä avautui yksityiskohtainen lista tiedoston jokaisesta rivistä, jossa näkyi viimeisin muokkaaja (Teemu Aittomaki, eli minä), pvm ja kellonaika, rivinumerot sekä varsinainen rivin sisältö. En ensimmäisestä tiedosto noilla riveillä (eli "fa62b00c") ollut varma, että mitä se tarkoittaa, joten etsin googlettamalla asiaan vastausta. Löysin tämän atlassian.com sivuston ([linkki](https://www.atlassian.com/git/tutorials/inspecting-a-repository/git-blame)) artikkelin, jossa kerrottiin, että se on muokkauksen id. Tutkin hieman lisää tuo omaa git blame listaani ja huomasinkin, että tuo id muuttuu selkeästi tapahtumahetken mukaan. Eli ne joissa on sama pvm ja kellon aika, on sama id, mutta kun kellonaika (tässähän nyt ei tietenkään pvm vaihdu) vaihtuu, niin myös id muuttuu. Alla muutama esimerkki:

**fa62b00c (Teemu Aittomaki   2020-04-20 14:13:22 +0000  1) # Harjoitus 3**

**ddd5c045 (Teemu Aittomaki   2020-04-20 14:31:54 +0000 13) Vaikka olinkin**

**d50d42de (Teemu Aittomaki   2020-04-20 14:42:47 +0000 67) Nyt kopion**

Lopussa näkyi myös tapahtumia, joita ei ollut commit:ttu vielä, joten niillä ei ollut varsinaista id:tä, tietona vain **00000000** eikä ketään ns. vastuu henkilöä. Eli tiedoston tiedoston muokkaaja tieto lisätään vasta commit:n jälkeen. Pvm ja kellonaika näkyivät jo. Alla yksi esimerkkirivi tällaisesta:

**00000000 (Not Committed Yet 2020-04-20 15:20:07 +0000 80) Tässä tehtäväosiossa**

Tämän tehtäväosion lopuksi päivitin muutokset (eli päivitetyn raportin sekä kuvat) GitHubiin.

**git add .**

**git commit -m "Updates to report and pictures"**

**git push**

## Tee tyhmä muutos gittiin, älä tee commit:tia. Tuhoa huonot muutokset ‘git reset –hard’. Huomaa, että tässä toiminnossa ei ole peruutusnappia.

Tässä tehtävässä oli tarkoituksena käyttää **git reset -hard** komentoa. En tiennyt tarkalleen mitä se teki, mutta nimestä sekä tehtävänannosta pystyi päättelemään, että se varmastikin resetoi jossakin määrin tehtyja muutoksia. Ennen kuin kokeilin komentoa, päivitin kaikki päivittämättömät tiedot GitHubiin.

Lisäsin harj3 kansioon uuden resettesti.txt tekstitiedoston, johon kirjoitin tekstin "Kokeillaan mitä git reset -had komennolla tapahtuu." ja tämän jälkeen kokeilin varsinaista reset komentoa.

**nano resettesti.txt**
**git reset --hard**

Komennosta seurasi tieto **HEAD is now at b962e0b Updates to report and pictures**. En ollut ihan varma mitä tämä tarkoitti, mutta **Updates to report and pictures** selkeästikin viittasi viimeisimpään commit:n, siinähän käytin tuota selostetta. **b962e0b** jonkinasteiselta id:ltä, mutta se ainakaan vaikuttanut liittyvän blame toiminnolla nähtäviin rivi id:hin, ne olivat 8 merkkiä pitkiä kun taas tämä oli 7 merkkiä pitkä. **HEAD is now at** taas ilmisesti kertoi missä kohdassa resetin alkukohta olisi, siltä se ainakin kuulosti, tuon **b962e0b** taas tällöin voisi olettaa olevan jokin tähän liittyvä id. Seuraavaksi katsoin oliko tekemäni resettesti.txt tiedosto kadonnut harj3 git kansiosta, mutta kun **cat resettesti.txt" komennolal kokeilin, niin näkyi että tiedosto sisältöineen oli selkeästi edelleen kansiossa.

**nano resettesti.txt**

**git reset --hard**

**cat resettesti.txt**

Eli **git reset --hard** ei ainakaan tuota tiedostoa minulta poistanut suoraan, asettiko se siis jonkin asteisen merkin, jonka jälkeiset tiedostot resetoidaan? En oikeastaan tiennyt tai osannut sanoa, joten turvauduin googleen. Löysin tämän devconnected.com sivuston ([linkki](https://devconnected.com/how-to-git-reset-to-head/)) ohjeen, jossa avattiin tätä komentoa. Eli tiedostot tulee aluksi siirtää **add** toiminnolla odottamaan (eli indexiin) commit:ia, jonka jälkeen **git reset --hard** resetoi tilanteen poistamalla ne kokonaan sekä indexistä git kansiosta palauttamalla tilanteen takaisin edellisen commit:n jälkeiseen tilanteeseen. devconnected.com sivuston ohjeen luettuani kokeilin tätä siirtämällä resettesti.txt tiedoston indexiin (eli odottamaan commit:ia), jonka jälkeen katsoin indexin tilan **git status** komennolla, siellä näkyi että resettesti.txt tiedosto odotti commit:ia. Nyt siis kokeilin **git reset --hard** komentoa, jonka jälkeen katsoin Gitin statuksen, nyt resettesti.txt tiedosto oli kadonnut indexistä, mikään tiedosto ei odottanut commit:ia. Listasin vielä git kansion sisällön, josta näki, että tiedosto oli kadonnut myös sieltä kokonaan.

**git add .**

**git status**

**git reset --hard**

**git status**

**git reset --hard** komennolla saa siis varsin helposti poistettua virheelliset tiedot sekä indexistä että koko kansiosta hyppäämällä takaisin edelliselle commit:lle. Reset komennon kanssa tosin kannattaa olla tarkkana, koska jos on **add** komennolla siirtänyt myös jotakin oleellista odottamaan commit:ia ja siirtoa, niin katoavat nämä myös tässä samassa.
