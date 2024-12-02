<template>
  <section class="services">
    <h2>Our Services</h2>
    <div class="services-grid">
      <div class="service-card" style="background-color: #FFDEE9;">
        <h3>IPO</h3>
        <p>Invest in Initial Public Offerings (IPOs) to access newly listed companies.</p>
      </div>
      <div class="service-card" style="background-color: #B5EAEA;">
        <h3>Stocks Investing</h3>
        <p>Build your wealth by investing in diverse stocks for long-term growth.</p>
      </div>
      <div class="service-card" style="background-color: #C8E7F4;">
        <h3>Bond Market</h3>
        <p>Explore bond investments for a safer, fixed-income return on investments.</p>
      </div>
      <div class="service-card" style="background-color: #FFF5BA;">
        <h3>ETF</h3>
        <p>Diversify your portfolio with Exchange-Traded Funds (ETFs) for balanced growth.</p>
      </div>
      <div class="service-card" style="background-color: #E2F0CB;">
        <h3>Mutual Funds</h3>
        <p>Invest in mutual funds for a professionally managed, diversified portfolio.</p>
      </div>
      <div class="service-card" style="background-color: #FFBCBC;">
        <h3>Options Trading</h3>
        <p>Manage risk and explore leveraged trading with options trading strategies.</p>
      </div>
      <div class="service-card" style="background-color: #E4D8DC;">
        <h3>Forex Trading</h3>
        <p>Trade foreign currencies in the global forex market for liquidity and variety.</p>
      </div>
      <div class="service-card" style="background-color: #D4A5A5;">
        <h3>Real Estate Investment Trusts (REITs)</h3>
        <p>Invest in real estate assets through REITs for long-term, stable returns.</p>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "ServicesSection",
};
</script>

<style scoped>
.services {
  background-color: #f2f2f2;
  padding: 40px 20px;
  text-align: center;
  border-radius: 8px;
}

.services h2 {
  font-size: 2em;
  margin-bottom: 30px;
  color: #333;
}

.services-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr); /* Default: Four cards in a single row */
  gap: 20px;
}

.service-card {
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
  transition: transform 0.2s ease-in-out;
  text-align: left;
}

.service-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
}

.service-card h3 {
  font-size: 1.5em;
  color: #333;
  margin-bottom: 8px;
}

.service-card p {
  font-size: 1em;
  color: #555;
  line-height: 1.6;
}

/* Responsive Design */
@media (max-width: 1200px) {
  .services-grid {
    grid-template-columns: repeat(3, 1fr); /* Three cards per row for medium screens */
  }
}

@media (max-width: 768px) {
  .services-grid {
    grid-template-columns: repeat(2, 1fr); /* Two cards per row for tablets */
  }
}

@media (max-width: 576px) {
  .services-grid {
    grid-template-columns: 1fr; /* One card per row for small screens */
  }

  .services h2 {
    font-size: 1.5em; /* Adjust heading size */
  }

  .service-card {
    padding: 15px; /* Adjust padding for smaller screens */
  }

  .service-card h3 {
    font-size: 1.2em; /* Adjust card heading size */
  }

  .service-card p {
    font-size: 0.9em; /* Adjust card text size */
  }
}
</style>
