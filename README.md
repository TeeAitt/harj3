# Harjoitus 3

Tässä harjoituksessa oli tarkoituksena perehtyä Git:n, ja siinä ohessa myös GitHubiin, käyttämiseen muutamien perustoimintojen avulla sekä asentaaa Saltin avulla minionille jokin (uusi) ohjelma. Tämä harjoitus perustuu Tero Karvisen pitämään Palvelinten Hallinta kurssiin, sekä harjoituksen että kurssin tarkemmat tiedot löytyvät hänen verkkosivuiltaan TeroKarvinen.com ([linkki](http://terokarvinen.com/2020/configuration-managment-systems-palvelinten-hallinta-ict4tn022-spring-2020/)). Git ja GitHub eivät olleet minulle entuudestaan täysin tuntemattomia. GitHubiin olin tunnuksen tehnyt jo aiemmalla Linux Palvelimet kurssilla ja Git:in käyttöön olimme hieman perehtyneet Haaga-Helian Ohjelmointi 2 kurssilla. Tiesin siis hieman noista tässäkin harjoituksessa käytettävistä peruskomennoista ennestään.


Käytettävät laitteet
- Asus VivoBook Pro N552VX kannettava tietokone Xubuntu 18.04 LTS, dualboot sisältää sekä Xubuntu 18.04 LTS että Windows 10 (olen tämän dualbootin asennuksen käynyt läpi artikkelissa, jonka päivitän tähän vielä jälkeenpäin)
- Oracle VirtualBox virtuaalikone, jossa käytössä Xubuntu 18.04 LTS
- Logitech MX518 hiiri

Käytin tässä harjoituksessa Oraclen VirtualBoxissa luotua virtuaalikonetta, jonka olin jo luonut aiemmasssa harjoituksessa 2 (linkki https://teemuaittomaki.wordpress.com/2020/04/15/palv-hallinta-h2/). Virtuaalikoneelle en ollut asentanut Xubuntua, vaan käytin sitä "Try Xubuntu" toiminnon avulla, tällöin sain harjoituksen jälkeen helposti pyyhittyä kaiken puhtaaksi ja aloitettua seuraavan harjoituksen alusta. Huom. virtuaalikoneen kello on aikavyöhykkeellä UTC 00, eli kolme tuntia Suomen aikaa jäljessä (Suomessa käytessä harjoituksen teko hetkellä kesäaika).

Vaikka olinkin Git:n ja GitHubiin ennen tätä harjoitusta hieman tutustunut, niin lukaisin niiden tarkemmista määrittelyistä hieman täst git-scm.com sivuston (linkki https://git-scm.com/) kuvauksesta sekä Wikipedian artikkelista (linkki https://en.wikipedia.org/wiki/GitHub). Git on ilmainen ja avoimeen lähdekoodiin perustuva version hallintajärjestelmä ja GitHub taas tarjoaa hosting-palvelun Git:iä hyödyntävässä ohjelmistokehityksessä.

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

Seuraavaksi loin README.md (tiedostomuotu siis MarkDown) tiedoston, johon lisäsin alkuun vain "Harjoitus3" tekstin, testaamista varten. Lisäsin **add** toiminnolla tämän tiedoston päivitettävien listalle ja **commit -m** toiminnolla toimonnolla hyväksyin tämän päivityksen "Started a readme" kommentin kera (**-m** määrittelee tuon kommentin lisäämisen) ja lopuksi uploadasin (push) päivityksen GitHubiin. Tästä tuli kuittauksena tieto siirrosta, joka vaikutti kaiken perusteella onnistuneen.

**echo "Harjoitus3" >> README.md**
**git add .**
**git commit -m "Started a readme"**
**git push**

Tarkistin vielä GitHubista näkyikö tämä README.md tiedosto sielläkin ja sisälsikö sen tuon Harjoitus3 tekstin. Tiedosto oli siirtynyt GitHubiin onnistuneesti, siinä näkyi kommentti "Started a readme" ja se sisälsi "Harjoitus3" tekstin.
Nyt kun tiesin yhteyden ja siirron Gitin ja GitHubin välillä toimivan, siirryin kirjoittamaan tätä raporttia Gitillä ja luomallani README.md tiedostolla. Avasin toisen välilehden komentoterminaaliin, johon avasin nanolla tuon readme tiedoston ja kopion jo kirjoittamani raportti sisällön siihen. Muotoilin jo tässä vaiheessa muutamia kohtia, kuten otsikot, komennot (lihavoin nämä) ja linkit, käytin muotoilussa apuna tätä GitHubin ohjetta ([linkki](https://help.github.com/en/github/writing-on-github/basic-writing-and-formatting-syntax)).
