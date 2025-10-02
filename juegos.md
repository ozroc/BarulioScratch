---
layout: default # Usa el layout principal (default.html)
title: Catálogo de Juegos de Scratch
---

<style>
  /* Estilos para el grid */
  .grid-container {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); /* Crea columnas flexibles */
    gap: 20px;
    padding: 20px;
  }
  .game-card {
    border: 1px solid #ddd;
    border-radius: 8px;
    overflow: hidden;
    text-align: center;
    box-shadow: 2px 2px 5px rgba(0, 0, 0, 0.1);
    transition: transform 0.2s;
  }
  .game-card:hover {
    transform: translateY(-5px); /* Pequeño efecto al pasar el ratón */
    box-shadow: 4px 4px 10px rgba(0, 0, 0, 0.2);
  }
  .game-card a {
    text-decoration: none;
    color: #333;
    display: block;
    padding: 15px;
  }
  .game-card h2 {
    margin: 5px 0 5px 0;
    color: #007bff; /* Color para los títulos */
    font-size: 1.5em;
  }
  .game-card p {
    font-size: 0.9em;
    color: #666;
  }
</style>

<h1>🚀 Todos los Juegos de Scratch Barulio</h1>
<p>¡Haz clic en cualquier juego para jugarlo y votarlo como favorito!</p>

<div class="grid-container">

  {% for juego in site.juegos %}
    <div class="game-card">
      <a href="{{ juego.url | relative_url }}">
        <h2>{{ juego.title }}</h2>
        <p>Creado por: **{{ juego.author }}**</p>
        <p>{{ juego.description | truncatewords: 15 }}</p>
        
        <button style="background-color: #f7a013; color: white; padding: 5px 10px; border: none; border-radius: 4px; margin-top: 10px;">
          JUGAR
        </button>
      </a>
    </div>
  {% endfor %}
  
</div>
