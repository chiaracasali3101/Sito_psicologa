<script setup lang="ts">
import { ref } from 'vue'
import './style.css' 

const isMenuOpen = ref(false);
const nome = "Dott.ssa Francesca Bocchi";

// Funzione unica per scorrere verso le sezioni
const vaiASezione = (id: string) => {
  if (id === 'home') {
    window.scrollTo({ top: 0, behavior: 'smooth' });
    return;
  }
  const elemento = document.getElementById(id);
  if (elemento) {
    elemento.scrollIntoView({ behavior: 'smooth' });
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
        <a href="#" @click.prevent="vaiASezione('home'); isMenuOpen = false">Home</a>
        <a href="#" @click.prevent="vaiASezione('servizi'); isMenuOpen = false">Di cosa mi occupo</a>
        <a href="#" @click.prevent="vaiASezione('descrizione'); isMenuOpen = false">Il mio approccio</a>
        <a href="#" @click.prevent="vaiASezione('chi-sono'); isMenuOpen = false">Chi Sono</a>
        <a href="#" @click.prevent="vaiASezione('contatti'); isMenuOpen = false" class="cta-small">Contattami</a>
      </div>
    </nav>

    <main>
      <!-- HERO -->
      <header id="home" class="hero">
        <div class="hero-flex-layout">

          <div class="hero-content">
            <h1>Dott.ssa Francesca Bocchi</h1>
            <h2>psicologa clinica</h2>
            <p>Ricevo in studio a <strong>Bologna</strong> e <strong>online</strong>.</p>
            <a href="#" @click.prevent="vaiASezione('contatti')" class="cta-main">Contattami</a>
          </div>
        </div>
      </header>

      <!-- SERVIZI -->
      <section id="servizi" class="services">

        <div class="grid">
          <div class="card">
            <h3>Lavoro con:</h3>
            <ul>
              <li>Bambini</li>
              <li>Adolescenti</li>
              <li>Adulti</li>
              <li>Genitori</li>
            </ul>
          </div>
          <div class="card">
            <h3>Mi occupo di:</h3>
            <ul>
              <li>Disagio emotivo, relazionale, comportamentale e psicosomatico</li>
              <li>Difficoltà evolutive in età evolutiva</li>
              <li>Momenti di cambiamento e transizioni di vita e di ruoli</li>
              <li>Difficoltà genitoriali</li>
            </ul>
          </div>
          <div class="card">
            <h3>Interventi:</h3>
            <ul>
              <li>Consultazione e valutazione clinica del disagio e dei sintomi</li>
              <li>Interventi di supporto psicologico</li>
              <li>Sostegno alla genitorialità</li>
            </ul>
          </div>
        </div>
      </section>

      <!-- DESCRIZIONE / APPROCCIO -->
      <section id="descrizione" class="description-section">
        <div class="description-container">
          <h2 class="quote-title">
            “Ogni sintomo ha un significato, racconta una storia, parla di un bisogno”
          </h2>

          <div class="description-text">
            <p>
              Credo che ogni persona porti con sé una storia unica e che ogni forma di sofferenza meriti di essere ascoltata prima ancora che interpretata.
            </p>
            <p>
              Nel mio lavoro mi occupo della valutazione e dell'intervento clinico del disagio psicologico che può manifestarsi nelle diverse fasi della vita, dall'infanzia all'adolescenza fino all'età adulta, accompagnando la persona anche nei momenti di cambiamento e nei passaggi evolutivi più significativi.
            </p>
            <p>
              Accompagno bambini, adolescenti e adulti in un percorso di comprensione di sé e del proprio disagio, che può esprimersi attraverso sintomi emotivi, relazionali, comportamentali o psicosomatici.
            </p>
            <p>
              Nel mio approccio ad orientamento psicoanalitico, il sintomo non è considerato soltanto come qualcosa da alleviare o eliminare, ma anche come un'espressione del mondo interno, di bisogni, conflitti o aspetti della propria storia che talvolta faticano a trovare altre vie di espressione. Per questo viene accolto e compreso all'interno della storia unica di ciascuno, per coglierne il significato profondo.
            </p>
            <p>
              Il percorso psicologico è uno spazio di ascolto, riflessione e scoperta nel quale la relazione terapeutica rappresenta uno strumento di comprensione e cambiamento per sviluppare modalità più autentiche e consapevoli di vivere le relazioni e affrontare i momenti di difficoltà.
            </p>
            <p>
              È rivolto sia a chi sta vivendo un momento di sofferenza e desidera un supporto psicologico, sia a chi sente il bisogno di conoscersi più a fondo e comprendere meglio il proprio modo di vivere le relazioni, le emozioni e le esperienze.
            </p>
            <p>
              Con bambini e adolescenti il percorso è orientato a comprendere il significato del disagio all'interno della fase evolutiva che stanno attraversando. Attraverso strumenti specifici per l'età evolutiva, offro uno spazio in cui emozioni e difficoltà possano essere accolte e trasformate sostenendo il naturale processo di sviluppo.
            </p>
            <p>
              Il percorso di sostegno psicologico può essere anche rivolto ai genitori per accompagnarli nelle difficoltà legate al ruolo genitoriale e nella relazione con i figli.
            </p>
          </div>
        </div>
      </section>

      <!-- CHI SONO -->
      <section id="chi-sono" class="about">
        <div class="about-grid">
          <div class="about-image">
            <div class="foto-cornice" style="overflow: hidden; display: flex; width: 100%; height: 100%;">
              <img 
                src="/immagini/radice.png" 
                alt="radice" 
                style="width: 100%; height: 100%; object-fit: cover; object-position: center;"
              >
            </div>
          </div>
          <div class="about-text">
            <span class="subtitle">Chi sono</span>
            <h2>La mia formazione:</h2>
            
            <p>
              Mi sono laureata in <strong>Psicologia clinica</strong> presso l'Università di Bologna nel 2021. Sono iscritta all'Albo professionale dell'Ordine degli psicologi dell'Emilia Romagna, sezione A, con il numero 11243.
            </p>
            <p>
              Attualmente sto ultimando la specializzazione in <strong>psicoterapia psicoanalitica dell'età evolutiva</strong> presso la SPP di Milano.
            </p>
            <p>
              Nel corso della mia formazione ho svolto esperienze di tirocinio presso: 
            </p>
            
            <ul class="formazione-lista">
              <li>Il Servizio di supporto psicologico del reparto di Ostetricia, Ginecologia e Fisiopatologia della riproduzione umana del Policlinico Sant'Orsola di Bologna.</li>
              <li>La Neuropsichiatria dell'infanzia e dell'adolescenza (NPIA) presso l'AUSL di Bologna.</li>
              <li>Gruppi di supporto psicologico alla genitorialità.</li>
              <li>Gruppi di supervisione clinica presso il servizio di consultazione clinica genitori-bambini presso il dipartimento Unibo.</li>
            </ul>
          </div>
        </div>
      </section>

      <!-- CONTATTI -->
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
                      src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2845.68009899629!2d11.370956!3d44.5012213!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x477e2b0032fb18b3%3A0x32da43a870afa165!2sPsicologa%20Dott.ssa%20Francesca%20Bocchi!5e0!3m2!1sit!2sit!4v1786187142182!5m2!1sit!2sit"  
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
            </div>
          </div>
        </div>
      </section>
    </main>

    <footer>
      <p>© 2026 {{ nome }} - Psicologa</p>
    </footer>
  </div>
</template>