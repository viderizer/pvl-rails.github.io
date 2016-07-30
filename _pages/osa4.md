---
layout: page
title: Sivut hienoiksi
permalink: /osa4/
order: 4
---

## Tässä osassa muokkaamme viewejä ja asennamme Bootstrap-tyylikirjaston

Sivut ovat nyt aika rumat. Emmehän edes tiedä, onko joku kirjautunut
sisään vai ei. Muokataan viewejä niin että näkyvillä on Kirjaudu
sisään -nappi jos kukaan ei ole kirjautunut, ja Kirjaudu ulos -nappi
jos on. Haluamme myös näkyviin kirjautuneen käyttäjän
nimen. Asennetaan ensin kuitenkin Bootstrap-tyylikirjasto, sillä siitä
tulee olemaan paljon hyötyä tässä osassa. Lisätään Gemfile-tiedostoon

    gem 'bootstrap-sass'
    group :development do
        gem 'rails_layout'
    end

Gemit asennetaan komennolla

    bundle install

Asennetaan Bootstrap ajamalla

    rails generate layout:install bootstrap3 --force

Käynnistä serveri sen jälkeen uudelleen. Katso selaimesta sovellusta ja
huomaa ero!

### Muokataan navigaatiopalkkia

Sivun yläreunassa on nyt musta navigaatiopalkki. On loogista ja tuttua ilmoittaa
navigaatiopalkissa kirjautuneen käyttäjän nimi. Myös Kirjaudu Ulos- ja
Kirjaudu Sisään -napit sijoitetaan navigaatiopalkkiin.

### Keskustelukysymys

Miten saamme tietää tällä hetkellä kirjautuneen käyttäjän?

Vastaus current\_user -metodi ApplicationControlleriin (`app/controllers/application_controller.rb`).
ApplicationControllerin metodeita voidaan kutsua muista
controllereista.  Helper\_method-määrityksen avulla current\_user
-metodia voidaan kutsua myös vieweistä. Jos et jaksa koodata niin
kopioi
[täältä](https://github.com/UMTti/chat/blob/master/app/controllers/application_controller.rb)

![](/img/current_user.png)

### Kirjautuneen käyttäjän nimi näkyviin

Navigaatiolinkkien view on tiedosto
`app/views/layouts/_navigation_links.html.erb`. Vieweihin saa
kirjoitettua Rubyn ehdolauseita `<% %>` -tagien sisälle.
`<%= %>` -tagi saa sisällään olevan sisällön näkyviin sivulle.

![](/img/current_user_tagi.png)

### Kirjaudu sisään / Kirjaudu ulos

Saat selville `rake routes` -komennolla chat-hakemistossa
sisäänkirjautumisen ja uloskirjautumisen reitit (siis esim
signout\_path). Esimerkiksi uloskirjautumislinkin koodi on siis

    <%= link_to "Kirjaudu ulos", signout_path, class: 'navbar-brand' %>

Rakenna itse sisäänkirjautumisen linkki ja sijoita molemmat linkit
`_navigation_links.html.erb`-tiedostoon oikeisiin kohtiin. Huom. lisää
else-lause ifin jälkeen!

### Vapaavalintaista tyylitystä

Kokeile [Bootstrapin sivuilta](http://getbootstrap.com/css/)
esimerkiksi Buttons-kohdasta lisätä navigaatiolinkin classiin napin
tyylitys btn btn-default.
