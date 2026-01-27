---
layout: default
title: Home
---

<section class="hero">
  <img src="{{ '/assets/images/logo.png' | relative_url }}" alt="Leaflet" class="hero-logo">
  <h1>Leaflet</h1>
  <p class="tagline">See past the cover — discover books you'll actually love</p>
  
  <span class="coming-soon">Coming Soon</span>
  <p class="subtitle">iOS & Android</p>
</section>

<div class="home-content">
  <h2>What is Leaflet?</h2>
  <p>Point your phone at any bookshelf. Leaflet reads the spines, looks up ratings from real readers, and shows you which books are worth your time.</p>
  <p><strong>No more guessing.</strong> No more judging books by their covers.</p>
  
  <hr>
  
  <form action="https://buttondown.com/api/emails/embed-subscribe/Larlyssa" method="post" class="signup-form" id="signup-form">
    <label for="bd-email">Get notified when we launch:</label>
    <div class="signup-row">
      <input type="email" name="email" id="bd-email" placeholder="you@email.com" required />
      <input type="submit" value="Notify Me" />
    </div>
    <p class="signup-success" id="signup-success">✓ Thanks! We'll email you when Leaflet launches.</p>
    <p class="signup-error" id="signup-error">Something went wrong. Try again?</p>
  </form>

  <script>
    document.getElementById('signup-form').addEventListener('submit', async function(e) {
      e.preventDefault();
      const form = this;
      const email = document.getElementById('bd-email').value;
      const success = document.getElementById('signup-success');
      const error = document.getElementById('signup-error');
      const submitBtn = form.querySelector('input[type="submit"]');
      
      submitBtn.value = 'Sending...';
      submitBtn.disabled = true;
      
      try {
        const response = await fetch(form.action, {
          method: 'POST',
          body: new FormData(form),
          mode: 'no-cors'
        });
        form.querySelector('.signup-row').style.display = 'none';
        form.querySelector('label').style.display = 'none';
        success.style.display = 'block';
      } catch (err) {
        error.style.display = 'block';
        submitBtn.value = 'Notify Me';
        submitBtn.disabled = false;
      }
    });
  </script>
</div>
