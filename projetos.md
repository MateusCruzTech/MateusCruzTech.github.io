---
layout: projeto 
title: Projetos
tagline: Clique em um card para saber mais e ver o código
link: https://github.com/MateusCruzTech
image: /assets/image/image.png 
---
<link rel="stylesheet" href="{{ '/assets/css/project.css' | relative_url }}"> 

<div class="project-list">
  {% for projeto in site.projetos %}
  <a href="{{ projeto.url | relative_url }}" class="project-card">
    {% if projeto.image %}
      <img src="{{ projeto.image | relative_url }}" alt="Imagem do Projeto {{ projeto.title }}"> 
    {% endif %}
    <div class="card-content">
      <h2>{{ projeto.title }}</h2>
      <p>{{ projeto.tagline }}</p>
      <span class="read-more">Ver Detalhes →</span>
    </div>
  </a>
  {% endfor %}
</div>