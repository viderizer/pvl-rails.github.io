---
layout: page
title: Web-sovellusten tietoturva
permalink: /osa6/
order: 6
---

Lue [lyhyt muistilista devaajalle tietoturvasta](https://tuuren.wordpress.com/2016/01/23/rails-sovelluksen-tietoturva/)
sekä sen alussa linkattu Railsin tietoturvaohjeistus.

## Keskustelukysymys

Mikä on Cross Site Request Forgery? Miten sen voi estää ohjelmiston kehitysvaiheessa?

## Validoidaan käyttäjännimi ja salasana

Käyttäjänimen tulee olla uniikki ja sen pituuden täytyy olla vähintään 1
merkki. Railsissa tietokantaobjektien attribuuteille voi antaa
vaatimuksia modeleissa. Lisää user.rb -tiedostoon


    validates :name, uniqueness: true, length: { minimum: 1 }

Sen jälkeen mieti itse miten salasana validoidaan vähintään 6 merkin
pituiseksi ja toteuta se.

## Miten validoisit salasanan sisältämään vähintään yhden numeron?
