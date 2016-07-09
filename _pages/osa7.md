---
layout: page
title: Ohjeita tulevaan
permalink: /osa7/
order: 7
---

Tekemämme sovellus jäi vielä aika kämäiseksi. Yksi tärkeä parannus olisi
keskusteluun uuden viestin lähetys suoraan käyttäjän omalta sivuilta
jossa näkyy kaikki keskustelut.

## Vinkkejä tuleviin Rails-sovelluksiin esimerkiksi työharjoittelussa:

### Sovelluksen automaattiset testit

Sovelluksen toimintaa voidaan testata automaattitesteillä monilla
tasoilla, modelien toiminnasta käyttöliittymään. Isoissa
Rails-sovelluksissa käyttöliittymän automaattitestaus on tärkeää, jotta
uusia toiminnallisuuksia koodattaessa vanhojen haluttu toiminta ei
muutu. Rails-käyttöliittymätestausta kannattaa tehdä
[Capybaralla](https://github.com/jnicklas/capybara). Capybara-testiin
kirjoitetaan erilaisia automaattisia nappien klikkauksia sekä formien
täyttämisiä, ja sen jälkeen tarkistus että sivulla on oikeanlainen
sisältö expect(page).to have\_content -vaiheessa.

### Vapaita CSS-kirjastoja ja teemoja

CSS:n osaaminen on tärkeä taito, mutta joskus on ajankäytöllisesti
parempi käyttää valmiita CSS-teemoja. Esimerkiksi
[täältä](http://www.free-css.com/free-css-templates) löytyy
ammattimaisen näköisiä CSS-teemoja jotka voi asentaa tiedostojen
linkkaamisen avulla Rails-sovellukseen.

### Reaaliaikaisuuden toteuttaminen

Reaaliaikaisuuden toteuttaminen tarkoittaa sitä, että käyttäjä saa
sivulle uutta sisältöä palvelimelta ilman että päivittää sivua. Tähän on
monia tekniikoita, joista yksi on
[websocketit](https://en.wikipedia.org/wiki/WebSocket). Railsissa
websocketeja voi käyttää joko [sisäisellä
ActionCable-kirjastolla](https://github.com/rails/rails/tree/master/actioncable)
tai käyttäen hieman helppokäyttöisempiä ulkoisia kirjastoja kuten
[Pusheria](https://pusher.com/).
