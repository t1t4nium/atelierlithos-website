---
layout: default
title: "Atelier Lithos — Un voyage entre volcans et lagons"
permalink: /
---

<section class="hero">
  <div class="hero-eyebrow">Bijoux artisanaux · Pierres naturelles · Fait main</div>
  <h1 class="hero-title">Un voyage entre <span class="hero-accent">volcans</span> et lagons</h1>
  <p class="hero-tagline">L'essence de la Terre à votre poignet.</p>
  <div class="hero-buttons">
    <a class="btn-primary" href="https://www.etsy.com/fr/shop/atelierlithosbijoux" target="_blank">Découvrir la boutique</a>
    <a class="btn-secondary" href="#creations">Nos créations</a>
  </div>
  <img src="/assets/images/hero.jpeg" alt="Bracelets Atelier Lithos" style="width:100%;max-width:900px;height:320px;object-fit:cover;border-radius:4px;margin-top:3rem;">
</section>

<section class="section section-center materials">
  <div class="section-label">Nos matières</div>
  <h2 class="section-title">Des pierres qui ont traversé le monde</h2>
  <p class="section-body">Chaque pierre est choisie pour son histoire, son origine, son énergie. De la lave d'Islande aux turquoises d'Afrique, Atelier Lithos vous connecte à la Terre.</p>
  <div class="materials-grid">
    {% for pierre in site.pierres %}
    <div class="material-card">
      <img class="material-icon" src="/assets/images/{{ pierre.image }}" alt="Perle {{ pierre.nom }}">
      <div class="material-name">{{ pierre.nom }}</div>
      <div class="material-origin">{{ pierre.origine | join: " · " }}</div>
    </div>
    {% endfor %}
  </div>
</section>

<section id="creations" class="section section-center creations">
  <div class="section-label">Nos créations</div>
  <h2 class="section-title">Chaque bracelet, un voyage unique</h2>
  <div class="divider"></div>
  <p class="section-body">Chaque modèle est une création à part entière — une combinaison de pierres choisie pour raconter un paysage, une sensation, un ailleurs.</p>
  <div class="creations-grid">
    {% assign bracelets = site.bracelets | sort: 'date' | reverse %}
{% for bracelet in bracelets %}
    <div class="creation-card">
      <img src="/assets/images/{{ bracelet.image }}" alt="Bracelet {{ bracelet.nom }}" style="width:100%;height:300px;object-fit:cover;">
      <div class="creation-body">
        <div class="creation-name">{{ bracelet.nom }}</div>
        <div class="creation-desc">"{{ bracelet.slogan }}"</div>
        <div class="creation-stones">
          {% for etiquette in bracelet.etiquettes %}
          <span class="stone-pill">{{ etiquette }}</span>
          {% endfor %}
        </div>
        <div class="creation-detail">{{ bracelet.informations_complementaires }}</div>
        <a class="creation-cta" href="{{ bracelet.lien_etsy }}" target="_blank">Voir sur Etsy ↗</a>
      </div>
    </div>
    {% endfor %}
  </div>
</section>

<section class="section section-center contact">
  <div class="section-label">Restez connecté</div>
  <h2 class="section-title">Les nouvelles créations en avant-première</h2>
  <p class="section-body">Suivez-nous pour rester informé des nouvelles créations, des éditions limitées et des offres exclusives.</p>
  <p class="social"><a href="https://www.instagram.com" target="_blank"><img src="/assets/images/instagram.png" alt="Instagram"></a></p>
</section>