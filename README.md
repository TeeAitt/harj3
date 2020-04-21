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


## Tee uusi salt-moduuli

Tässä viimeisessä tehtäväosiossa oli tarkoituksena tehä Salt-moduuli, jossa asennetaan jokin demoni, työpöytäohjelma tai komentokehotteesta toimiva ohjelma. Tarkoituksena oli kuitenkin, että kyseessä on jokin eri ohjelma, kuin olisi jossain aiemmassa kurssin harjoituksessa käytetty. Hetken mietittyäni tuli mieleen löytyisikö SQLite3-ohjelmasta pakettipohjaista asennusta. Olin ohjelman käyttämistä kokeillut pikaisesti toisella kurssilla, mutta silloinkin se oli asennettu lataamalla pakattutiedosto verkkosivulta. Hain siis komentoterminaalin kautta SQLite3:sta jonkinlaista pakettiasennustiedostoa. Lista oli varsin laaja, joten rajasin sen **grep** avulla koskemaan vain paketteja mitkä sisälsivät sqlite3 tekstin. Pakettilistalta löytyi sqlite3 niminen paketti, joka kuvauksen mukaan oli komentoterminaalin kautta käytettä sqlite3 ohjelma, päätin siis kokeilla luoda sen käyttöönoton ympärille salt-moduulin.

**apt-cache search sqlite3**

**apt-cache search sqlite3|grep sqlite3**

Tein Saltia varten virtuaalipalvelimen DigitalOceaniin, minulla oli siellä jo ennestään yksi, joten tein tätä varten oman. Olen tuon virtuaalipalvelimen luonnin käynyt tarkemmin läpi aiemmin Linux Palvelimet kurssin harjoituksessa 4 ([linkki](https://teemuaittomaki.wordpress.com/2020/02/21/harjoitus-4/)), joten käyn tässä tuon luonnin sekä alkuasetukset varsin pikaisesti vain läpi.

Kirjauduttuani DigitalOcean sivustolle sisään, valitsin oikeasta yläkulmasta "Create" pudotusvalikosta "Droplets" valinnan, jolla pääsin luomaan uuden Dropletsin (virtuaalipalvelimen). Loin Dropletsin alla olevilla valinnoilla:

- **Choose an image:** Ubuntu 18.04.3 (LTS) x64
- **Choose a plan:** Standard, $5/mo
- **Choose a datacenter region:** Franfurt
- **Choose a hostname:** ankka

(muut valinnat jätin tyhjiksi/oletuksiksi)

Tämän jälkeen klikkasin "Create Droplet", jonka jälkeen meni muutama sekuntti ja Droplets oli luotu. Seuraavaksi muodoston root-käyttäjällä ssh-yhteyden virtuaalipalvelimeen, annoin kirjautumisen yhteydessä DigitalOceanilta saamani salasanan, jonka jälkeen oli kirjautuneena luomalleni virtuaalipalvelimelle. Seuraavaksi loin virtuaalipalvelimelle uuden teemu nimisen käyttäjän, jolle annoin sudo, adm sekä admin oikeudet.

**ssh root@64.225.105.249**

**sudo adduser teemu**

**sudo adduser teemu sudo**

**sudo adduser teemu adm**

**sudo adduser teemu admin**

Käyttäjän luotuani avasin toisen komentoterminaalivälilehden ja kokeilin teemu-käyttäjällä sisäänkirjautumista virtuaalipalvelimelle. Kirjautuminen toimi, kokeilin vielä, että sudo oikeudet toimivat päivittämällä pakettitiedot. Nekin toimivat, eli nyt pystyin turvallisesti lukitsemaan root-käyttäjältä kirjautumisen yleisesti sekä ssh:n kautta. Aktivoin myös samalla palomuurin, tein siihen kuitenki aluksi aukon ssh-yhteyttä varten.


**ssh teemu@64.225.105.249**

**sudo usermod --lock root**

**sudoedit /etc/ssh/sshd_config** (tästä tiedostota tuli muuttaa **PermitRootLogin** kohta muotoon **no**)

**sudo service ssh restart**

**sudo ufw allow 22/tcp**

**sudo ufw enable**

Näiden jälkeen kokeilin vielä, ettei root-käyttäjällä kirjautuminen varmasti onnistu ssh:n kautta. Kirjautumisyrityksestä seurasi tieto "Permission denied, please try again.", eli kirjautminen ei rootilla enää onnistunut.

Alkuasetusket olivat kunnossa, eli nyt asensin tälle virtuaalipalvelimelle Salt-masterin. Käyn nämä Saltiin liittyvät toiminnot tässä varsin pikaisesti läpi, olen jo aiemmissa harjoituksissa (linkit [Harjoitus 1](https://teemuaittomaki.wordpress.com/2020/04/07/palv-hallinta-h1/) ja [Harjoitus 2](https://teemuaittomaki.wordpress.com/2020/04/15/palv-hallinta-h2/)) käynyt Saltin asennusta ja sen toimintoja tarkemmin läpi. Asennuksen jälkeen tein Saltia varten aukot palomuuriin.

**sudo apt-get install salt-master -y**

**sudo ufw allow 4505/tcp**

**sudo ufw allow 4506/tcp**

Virtuaalikoneelle taas asensin Salt-minionin, jonka jälkeen avasin minionin asetustiedoston muokkaukseen.

**sudo apt-get install salt-master -y**

**sudoedit /etc/salt/minion**

Asetustiedostoon määrittelin master-laitteen IP-osoitteen (**master:** kohta), jotta minion-laite tietää mihin IP-osoitteeseen sen tulee olla yhteydessä. Lisäksi määrittelin minionille tunnistetiedon (**id:** kohta) **laite1**. Tallensin muokkauksen ja käynnistin Salt-minionin uudestaan.

**sudo systemctl restart salt-minion.service **

Seuraavaksi katsoin masterilla **sudo salt-key -A** komennolla, oliko sille tullut hyväksyttäviä avaimia (public key). Listalla oli laite1:n lähettämä avain, hyväksyin sen "y" komennolla. Tämän jälkeen varmistin masterilla vielä "sudo salt '*' cmd.run 'whoami' komennolla, että yhteys ja komennot varmasti toimivat, tähän tuli vastaus "laite1: root", eli minion vastasi komentoon.

Tein seuraavaksi masterille kansion tilatoimintoja varten, joita aluksi kokeilin yksinkertaisella hello.sls tilalla ja helloteemu.txt tiedostolla.

**sudo mkdir /srv/salt**

**sudoedit /srv/salt/hello.sls**

Sisältö:

**/tmp/helloteemu.txt:**

**file.managed:**

**- source: salt://helloteemu.txt**


**sudoedit /srv/salt/helloteemu.txt**

Sisältö:

**Moro, mukavaa iltaa!**

Sitten vielä tilan testaus komennolla **sudo salt '*' state.apply hello**. Tästä tuli paluuna tieto, että tilan suoritus oli onnistunut, helloteemu.txt tiedosto oli kopioitu minionille. Jotta voisin olla asiasta varma, niin tarkistin vielä tämän komennolla "sudo salt 'laite1' cmd.run 'cat /tmp/helloteemu.txt'. Tästä seurasi paluuna "laite1: Moro, mukavaa iltaa!", tällä sain vavhistuksen, että tiedosto oli varmasti kopioitu minionille.

Varsinaisen SQLite3 ohjelman asennusta ja käyttöä testasin aluksi masterilla.

**sudo apt-get install sqlite3 -y**

Luin ohjelman **man** sivuilta ohjeita sen käytöstä. Alkuun kokeilin tehdo testidb.db nimisen tietokannan ja sen sisälle taulun muutamalla sarakkeella ja laittamalla näihin sarakkeisiin hieman jotain tietoa.

**sqlite3 testidb.db** Tämä luo tietokannan.

**create table tuotteet(** Tämä luo tuotteet nimisen taulun.

**tuoteid int primary key** Tämä luo tuoteid sarakkeen, joka on PK ja käyttää numeroita (int).

**nimi varcar(256)** Tämä luo nimi sarakkeen, joka käyttää eri merkkejä (kirjain tai numero).

**kpl int** Tämä luo kpl sarakkeen, joka käyttää numeroita.

**);** Tämä sulkee taulun.

**inset into tuotteet values(123, 'kahvi', 19);** Tämä lisää tietoja tuotteet tauluun.

**inset into tuotteet values(124, 'maito', 7);** Tämä lisää tietoja tuotteet tauluun (eli tässä lisättiin yhteensä kaksi riviä).

**select * from tuotteet;** Tämä tulostaa taulun sisällön.

**.quit** Lopettaa SQLite3 ohjelman.

Tietokannan SQLite3 loi kyseiseen sijaintiin jossa olin, eli teemu-käyttäjän kotihakemistoon, se ei siis luo tietokantaa johonkin ohjelman omaan hakemistoon. Ajatuksenani oli, että salt-moduuli joka tehtävässä oli tarkoitus luoda, asentaisi minion-laitteelle SQLite3 ohjelman sekä samalla esimerkkitietokannan. Esimerkkitietokantaa varten järkevin tapa lienee kuitenkin toteuttaa se vain tiedostokopiointina. Katsoin vielä **cat testidb.db** komenolla miltä tuon tietokannan sisältö näytti.

Tietokannan sisältö oli hieman kryptisen näköistä, päädyin siis siihen, että paras vaihtoehto on tosiaan kopioida esimerkkitietokanta minion-laitteelle sekä luoda käyttäjälle pieni ohje kuinka SQLite3 voi käyttää ja kuinka esimerkkitietokannan saa ohjelmalla auki.

Alkuun tein uuden tilatiedoston komenolla **sudoedit /srv/salt/sql.sls**, jonka sisään kirjoitin alla olevan sisällön:

**sqlite3:**

**pkg.installed**

Tämä asentaa SQLite3 ohjelman (mikäki ei asennettu).

**/etc/skel/databases:**

**file.directory**

Tämä luo skel hakemistoon databases nimisen kansion. Tero Karvinen kertoi luennolla tuosta skel-hakemiston toiminnasta ja luin siitä hieman lisää myös tästä linfo.org sivuston ([linkki](http://www.linfo.org/etc_skel.html)) kuvauksesta. Kun uusi käyttäjä luodaan **adduser** komenolla, niin mikäli /etc/skel/ hakemistoon on määritelty jotain kansioita ja/tai tiedostoja, luodaan nekin uuden käyttäjän kotihakemistoon käyttäjän luonnin yhteydessä. Eli nyt aina kun minion-laitteelle lisätään uusi käyttäjä muodostuu hänelle myös databases hakemisto samassa yhteydessä.

**/etc/skel/databases/esimerkkidb.db:**
**file.managed:**
**- source: salt://esimerkkidb.db**

Tämä luo esimerkkitietokannan skel hakemistoon, sekin siis muodostuu uusille käyttäjille automaattisesti.

**/etc/skel/databases/db_ohje.txt:**

**file.managed:**

**- source: salt://db_ohje.txt**

Tämä luo tietokannan käytöstä ohjeen skel hakemistoon vastaavasti kuin ylempi.

Tein vielä tuon esimerkkitietokannan SQLite3 ohjelmalla sekä nanolla kirjoitin ohjeen uusille käyttäjille.

Esimerkkitietokanta:

**sqlite3 esimerkkidb.db**

**sqlite> create table tuotteet(**

**...> tuote_id int primary key,**

**...> nimi varchar(256),**

**...> kpl int**

**...> );**

**sqlite> insert into tuotteet values(1001, 'esim1', 16);**

**sqlite> insert into tuotteet values(1002, 'esim2' 7);**

**sqlite> insert into tuotteet values(1002, 'esim2', 7);**

**sqlite> insert into tuotteet values(1003, 'esim3', 19);**

**sqlite> select * from tuotteet;**

**1001|esim1|16**

**1002|esim2|7**

**1003|esim3|19**

**sqlite> .quit**


db_ohje.txt tiedostoon kirjoitin pienen listan ohjeita (näkyy kuvassa). Tämän jälkeen vielä kopion tiedostot /srv/salt/ hakemistoon.

**sudo cp esimerkkidb.db /srv/salt/**

**sudo cp db_ohje.txt /srv/salt/**

Ennen sql.sls tilatiedoston toimintojen testaamista minioniin, kokeilin sitä lokaalisti komennolla **sudo salt-call --local state.apply sql --state-output terse**.

          local:

          Name: sqlite3 - Function: pkg.installed - Result: Clean Started: - 21:58:14.802103 Duration: 523.797 ms

          Name: /etc/skel/databases - Function: file.directory - Result: Changed Started: - 21:58:15.330535 Duration: 1.386 ms

          Name: /etc/skel/databases/esimerkkidb.db - Function: file.managed - Result: Changed Started: - 21:58:15.332084 Duration: 14.854 ms

          Name: /etc/skel/databases/db_ohje.txt - Function: file.managed - Result: Changed Started: - 21:58:15.347069 Duration: 3.591 ms


          Summary for local
          
          ------------

          Succeeded: 4 (changed=3)

          Failed:    0

          ------------
          Total states run:     4
          Total run time: 543.628 ms


Tilatoiminnot toiminnot toimivat ainakin lokaalisti, oli siis aika kokeilla käytännössä, eli minionille tilatoimintojen suorittamista.

**sudo salt '*' state.apply sql**


          laite1:

          ----------

          ID: sqlite3

    Function: pkg.installed

      Result: True

     Comment: The following packages were installed/updated: sqlite3

     Started: 22:29:58.509542

    Duration: 8364.982 ms

     Changes:   

              ----------

              libsqlite3-0:

                  ----------

                  new:

                      3.22.0-1ubuntu0.3

                  old:

                      3.22.0-1ubuntu0.2

              sqlite3:

                  ----------

                  new:

                      3.22.0-1ubuntu0.3

                  old:

          ----------

          ID: /etc/skel/databases

    Function: file.directory

      Result: True

     Comment: Directory /etc/skel/databases updated

     Started: 22:30:06.877240

    Duration: 2.954 ms

     Changes:   

              ----------

              /etc/skel/databases:

                  New Dir

          ----------

          ID: /etc/skel/databases/esimerkkidb.db

    Function: file.managed

      Result: True

     Comment: File /etc/skel/databases/esimerkkidb.db updated

     Started: 22:30:06.880267

    Duration: 385.206 ms

     Changes:   

              ----------

              diff:

                  New file

              mode:

                  0644

          ----------

          ID: /etc/skel/databases/db_ohje.txt

    Function: file.managed

      Result: True

     Comment: File /etc/skel/databases/db_ohje.txt updated

     Started: 22:30:07.265757

    Duration: 250.769 ms

     Changes:   

              ----------

              diff:

                  New file

              mode:

                  0644
          
          Summary for laite1

          ------------

          Succeeded: 4 (changed=4)

          Failed:    0

          ------------

          Total states run:     4

          Total run time:   9.004 s



Tilatoiminnon jälkeisestä palautteesta näkyy, että kaikki tilatoiminnot onnistuivat. Kuitenkin vielä varmistaakseni asian, tuli tämä testata.

**sudo salt 'laite1' cmd.run 'ls /etc/skel/databases/'**

**laite1:**

**db_ohje.txt**

**esimerkkidb.db**

Komennon palautteesta näkyy, että minionin /etc/skel/ hakemistoon oli muodostunut databases kansio ja sinne db_ohje.txt sekä esimerkkidb.db tiedostot. Kokeilin vielä erikseen minionilla lisätä uuden matti nimisen käyttäjän, jolla sitten koitan avata esimerkkidb.db tietokannan.

**sudo adduser matti**

**sudo login matti**

**ls** komennolla tarkistin että databases hakemisto näkyi matti-käyttäjän hakemistossa. Siirryin hakemistoon **cd databases/**, avasin esimerkki tietokannan **sqlite3 esimerkkidb.db** ja tulostin tuotteet taulun sisällön **select * from tuotteet;**. Kaikki toimi ja näkyi oikein. Suljin SQLite3:n **.quit** ja katsoin että tietokanta ohje avautuu **cat db_ohje.txt"". Se avautui sekä sinne kirjoitettu sisältö näkyi myös.

Tämä tula sql.sls tilatiedosto toimi siis onnistuneesti. Lisäsin masterille vielä /srv/salt/ hakemistoon sql.sls tilatiedoston toiminnan automatisoivan top.sls tiedoston.

**sudoedit /srv/salt/top.sls**

Sisältö:

**base:**

**'*'**

**- sql**

### Lopetin harjoituksen 21.4.2020 klo 1.57
