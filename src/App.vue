<script setup lang="ts">
import { ref } from 'vue'

const isMenuOpen = ref(false);
const nome = "Dr.ssa Francesca Bocchi";

// Funzione unica per scorrere verso le sezioni
const vaiASezione = (id: string) => {
  const elemento = document.getElementById(id);
  if (elemento) {
    elemento.scrollIntoView({ behavior: 'smooth' });
  } else if (id === 'home') {
    window.scrollTo({ top: 0, behavior: 'smooth' });
  }
};
</script>

<template>
  <div class="site-wrapper">
    <nav>
      <div class="logo" @click="vaiASezione('home')" style="cursor:pointer">{{ nome }}</div>

      <!-- Pulsante Hamburger -->
      <button class="hamburger" @click="isMenuOpen = !isMenuOpen" :class="{ 'is-active': isMenuOpen }">
        <span></span>
        <span></span>
        <span></span>
      </button>

      <div class="menu" :class="{ 'open': isMenuOpen }">
        <a href="#home" @click="isMenuOpen = false">Home</a>
        <a href="#servizi" @click="isMenuOpen = false">Di cosa mi occupo</a>
        <a href="#chi-sono" @click="isMenuOpen = false">Chi Sono</a>
        <a href="#contatti" @click="isMenuOpen = false" class="cta-small">Contattami</a>
      </div>
</nav>

    <main>
      <header id="home" class="hero">
        <div class="hero-flex-layout">
          
          <div class="hero-side-img left-img">
            <img src="/immagini/radice.png" alt="Grafica sinistra">
          </div>

          <div class="hero-content">
            <h1>Francesca Bocchi</h1>
            <h2>psicologa clinica</h2>
            <p>Ricevo in studio a <strong>Bologna</strong> e <strong>online</strong>.</p>
            <a href="#" @click.prevent="vaiASezione('contatti')" class="cta-main">Contattami</a>
          </div>

          <div class="hero-side-img right-img">
            <img src="/immagini/radice.png" alt="Grafica destra">
          </div>

        </div>
      </header>

      <section id="servizi" class="services">
        <h2>Mi occupo di:</h2>
        <div class="grid">
          <div class="card">
            <h3>Valutazione clinica: </h3>
            <p>percorsi di consultazione per bambini, adolescenti e adulti, volti ad accogliere il disagio, comprenderne il significato profondo e individuare il percorso terapeutico.</p>
          </div>
          <div class="card">
            <h3>Percorsi di supporto psicologico:</h3>
            <p>per bambini, adolescenti e adulti.</p>
          </div>
          <div class="card">
            <h3>Supporto alla genitorialità:</h3>
            <p>interventi di sostegno dedicati ai genitori e percorsi di accompagnamento alla terapia del filio.</p>
          </div>
        </div>
      </section>

      <section id="chi-sono" class="about">
        <div class="about-grid">
          <div class="about-image">
            <div class="about-image">
              <div class="foto-cornice" style="overflow: hidden; display: flex; width: 100%; height: 100%;">
                <img 
                  src="/immagini/radice.png" 
                  alt="radice" 
                  style="width: 100%; height: 100%; object-fit: cover; object-position: center;"
                >
              </div>
            </div>
          </div>
          <div class="about-text">
            <span class="subtitle">Chi sono</span>
            <div style="text-align: center; margin: 60px 0;">
      </div>
            <h2>La mia formazione:</h2>
            
            <p>
              Mi sono laureata in <strong>Psicologia clinica</strong> presso l'Università di Bologna nel 2021. Sono iscritta all'Albo professionale dell'Ordine degli psicologi dell'Emilia Romagna, sezione A, con il numero 

            </p>
            <p>
              Attualmente sto ultimando la specializzazione in <strong>psicoterapia psicoanalitica dell'età evolutiva</strong> presso la SPP di Milano.
            </p>
            <p>
              Nel corso della mia formazione ho svolto esperienze di tirocinio presso: 
            </p>
            
            <ul class="formazione-lista">
              <li>⁠Il Servizio di supporto psicologico del reparto di Ostetricia, Ginecologia e Fisiopatologia della riproduzione umana del Policlinico Sant'Orsola di Bologna.</li>
              <li>la Neuropsichiatria dell'infanzia e dell'adolescenza (NPIA) presso l'AUSL di Bologna.</li>
              <li>Gruppi di supporto psicologico alla genitorialità.</li>
              <li>⁠Gruppi di supervisione clinica presso il servizio di consultazione clinica genitori-bambini presso il dipartimento Unibo</li>
            </ul>
          </div>
        </div>
      </section>

      <section id="contatti" class="contact-section">
        <div class="contact-container">
          <span class="subtitle">Contatti</span>
          
          <div class="contact-grid">
            <div class="contact-info">
              
              <div class="info-item">
                <span class="icon">📧</span>
                <div>
                  <h4>Email</h4>
                  <p>francescabocchi.psi@gmail.com</p>
                </div>
              </div>

              <div class="info-item">
                <span class="icon">📞</span>
                <div>
                  <h4>Telefono</h4>
                  <p><a href="tel:+393505944725" style="text-decoration: none; color: inherit;">+39 3505944725</a></p>
                </div>
              </div>
              
              <a href="https://wa.me/393505944725" class="whatsapp-btn" target="_blank" style="display: inline-block; margin-top: 10px;">
                Contattami su WhatsApp
              </a>
            </div> 

            <div class="contact-map-column">
              <div class="info-item">
                <span class="icon">📍</span>
                <div>
                  <h4>Studio</h4>
                  <p>Via Serafino Calindri 10/D/E, Bologna (BO)</p>
                  
                  <div class="map-box" style="margin-top: 15px; border-radius: 12px; overflow: hidden; box-shadow: 0 4px 15px rgba(0,0,0,0.08); width: 100%; max-width: 450px;">
                    <iframe 
                      src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2845.68010040811!2d11.368381076196005!3d44.501221271074584!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x477fd49bca59465f%3A0xe5ff461239bf1e6!2sVia%20Serafino%20Calindri%2C%2010%2C%2040139%20Bologna%20BO!5e0!3m2!1sit!2sit!4v1718653000000!5m2!1sit!2sit" 
                      width="100%" 
                      height="280" 
                      style="border:0;" 
                      :allowfullscreen="true" 
                      loading="lazy" 
                      referrerpolicy="no-referrer-when-downgrade">
                    </iframe>
                  </div>
                </div>
              </div>
            </div> </div> </div> </section>
</main>
    <footer>
      <p>© 2026 {{ nome }} - Psicologa </p>
    </footer>
  </div>
</template>
