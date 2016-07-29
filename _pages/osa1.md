---
layout: page
title: Tutustutaan web-ohjelmointiin
permalink: /osa1/
order: 1
---

### Serveri, tietokanta, selain, http-pyyntö, ääääh! Miten niinku saan sivut nettiin?

Serveri on tietokone, joka sijaitsee jossain päin maailmaa. Serverillä
voi pyöriä ohjelmia ja sillä on *IP-osoite*. Kaikki Internet-verkon
tietoliikenne kulkee IP-paketteina. IP-osoite on niinkuin kotiosoite,
sen perusteella paketit löytävät perille. IP-osoite voi olla muuttuva,
mutta servereillä on yleensä kiinteä IP-osoite joka on sidottu
*domainiin*. IP-osoitteiden ja domainien keskinäiseen muuntamiseen on
olemassa oma järjestelmä, *DNS* eli Domain Name System.

### HTTP-pyynnöt

HTTP on protokolla, jota selaimet ja WWW-palvelimet käyttävät
tiedonsiirtoon. HTTP perustuu siihen, että asiakas (yleensä selain)
lähettää HTTP-pyynnön, johon palvelin vastaa. HTTP-pyyntöjä on useita
erilaisia. Yleisimmät HTTP-pyynnöt ovat GET ja POST. GET-pyyntö on
tarkoitettu sivun hakemiseen serveriltä, POST taas tiedon lähetykseen
serverille. HTTP-pyyntöjen erilaisuuden selittämiseen voi käyttää
vertausta postin toiminnasta. POST-pyyntö on kuin postipaketti, joka
sisältää tietoa tai asioita ja joka toimitetaan vastaanottajalle niin
että hän voi sitä käyttää. GET-pyyntö on taas kuin kuriiri, joka käy
pyytämässä esimerkiksi http://google.com -sivua, ja saa vastaukseksi
HTML-sivun.

Tehtävä: Lataa [Postman-sovellus.](https://www.getpostman.com/)
Postman on vähän kuin tekstiselain, eli sillä pystyy
havainnollistamaan HTTP-pyyntöjen toimintaa. Tee Postmanilla
GET-pyyntö johonkin osoitteeseen ja katso millainen vastaus on. Sen
jälkeen tee POST-pyyntö osoitteeseen http://httpbin.org/post. Httpbin
on testiserveri, joka palauttaa POSTilla lähettämäsi datan
sinulle. Serveri saa itse kuitenkin aina määritellä, mitä se palauttaa
POST-pyyntöön. Lisää Postmanin Body-kohdasta jokin Key ja Value,
lähetä ja katso mitä palautetaan vastauksena. Huomaa myös Postmanin
valikosta, kuinka paljon erilaisia HTTP-pyyntöjä onkaan olemassa.

## Web-ohjelmoinnin työkalut

### Keskustelukysymys

Mitä web-ohjelmoinnin työkaluja tiedät tai olet käyttänyt?

### HTML

Tee Postmanilla GET-pyyntö osoitteeseen http://google.com. Googlen
sivut näyttävät aika sekamelskalta. Kokeile seuraavaksi
hs.fi:tä. Huomaat, että HTML-tiedostoilla on tietty rakenne. Ne
koostuvat tageista ja niiden sisällä olevista tageista ja teksteistä.

### JavaScript

Etsi sivulta script -tagi ja katso millaista koodia sen jälkeen tulee.
Se on JavaScriptiä, ja se suoritetaan käyttäjän selaimessa. JavaScript
on eri asia kuin Java, ja sitä käytetään selaimen toiminnallisuuksiin
sovelluksissa. Tutustu nyt [JQuery-UI:n](http://jqueryui.com/)
demoihin, niin saat jonkinlaista kuvaa siitä, mihin JavaScriptiä
käytetään ohjelmoinnissa. JQuery on JavaScript-kirjasto. Pääset itse
käyttämään JQueryä myöhemmin tällä kurssilla.

### CSS

CSS eli Cascading Style Sheets on taas tarkoitettu sivujen
tyylittämiseen. Tutustumme lisää CSS:ään kurssin osassa 6. Esimerkiksi
tämän kurssisivuston tekstit ja värit on saatu aikaan
CSS:llä. Sivuston CSS on usein määritelty omassa .css
-tiedostossaan. CSS-koodilla voidaan määritellä jokaiselle
HTML-tagille oma tyyli, esimerkiksi tekstin ja taustan väri sekä
fontti. Esimerkiksi seuraava koodi tyylittää h1-tagin (iso otsikko)
niin että sen tekstin väri on oranssi ja teksti on keskitetty sivun
keskelle.

    h1 {
        color: orange;
        text-align: center;
    }

### Palvelinohjelmointi

Nyt olemme tutustuneet HTML:ään, CSS:ään ja JavaScriptiin. Ne kaikki
liittyvät serverin palauttaman koodin näyttämiseen käyttäjälle.
Esimerkiksi Postmanilla huomasimme että erilaisissa selaimissa
serverin palauttama koodi näkyy erilaisena, Postman ei esimerkiski
suorita http://google.com -GET-pyynnön palauttamaa script-tagin
sisällä olevaa JavaScript-koodia. Mutta kuka päättää, mitä serveri
palauttaa?  Esimerkiksi google-hakuahan tehdessä palautus riippuu
siitä, millä hakusanoilla käyttäjä on hakenut. Tähän tarvitaan
palvelinohjelmointia.  Siihen käytetään monia ohjelmointikieliä,
esimerkiksi Pythonia, Javaa ja Ruby On Railsia. Ruby on
olio-ohjelmointikieli kuten Javakin, ja Rails on Rubyyn tehty
web-ohjelmointikirjasto. Palvelinohjelma huolehtii niin tietokannan
käytöstä kuin HTTP-pyyntöjen vastaanottamisesta ja niihin
vastaamisesta. Tällä kurssilla koodaamme Ruby On Railsia ja
seuraavassa osassa teemmekin oman Rails-projektin.

### Tehtävä ennen railsiin siirtymistä

Tee omat nettisivut users.paivola.fi -tunnuksellesi jos niitä ei
ole. Asenna sitä varten jokin tekstieditori, mieluiten sellainen jolla on
helppo käsitellä useita tiedostoja samaan aikaan, esimerkiksi
[Sublime Text](https://www.sublimetext.com/). Nettisivujen tekoon on tarkoitus käyttää sen verran aikaa, että ymmärrät
HTML:n, CSS:n ja JavaScriptin erot ja osaat luoda yksinkertaisen sivun
jossa on käytetty kaikkia näitä kolmea tekniikkaa. Apua sivujen tekoon
saat [W3Schools](http://www.w3schools.com/) -sivustolta.

Nettisivujen siirto palvelimelle
1) Ota ssh-yhteys palvelimelle komennolla 

    ssh tunnus@evo.paivola.fi
    
Luo sinne public_html-kansio komennolla 

    mkdir public_html
    
2) Tiedostot siirretään scp-komennolla (scp = Secure Copy). Ota selvää sopivasta syntaksista [täältä](http://www.hypexr.org/linux_scp_help.php) ja kysy neuvoa tarvittaessa. Oikea syntaksi riippuu esimerkiksi siitä, haluatko siirtää yksittäisen tiedoston eli index.html-tiedoston vai useita tiedostoja. 

3) Asetetaan lukuoikeudet public_html-kansiolle ensin juuressa komennolla

    chmod a+r public_html
    
Sen jälkeen public_html-kansion tiedostoille 

    cd public_html
    chmod a+r .
    
Tiedostojen lukuoikeuksien säätäminen voi joskus olla hankalaa. Saat tietää komennolla

    ls -la

kansioiden ja tiedostojen lukuoikeudet. Komennoilla 

    cd kansio

ja 

    cd ..
    
siirryt kansioon ja takaisin sieltä. 
    
    
