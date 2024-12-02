<template>
  <footer class="footer">
    <section class="contact">
      <h2>Contact Us</h2>
      <p>Phone: <a href="tel:8296601933">8296601933</a></p>
      <p>Email: <a href="mailto:gowthammrgowthu1999@gmail.com">gowthammrgowthu1999@gmail.com</a></p>
    </section>
    <section class="footer-links">
      <ul>
        <li><a href="#">Privacy Policy</a></li>
        <li><a href="#">Terms of Service</a></li>
        <li><a href="#">Careers</a></li>
        <li><a href="#">Support</a></li>
      </ul>
    </section>
  </footer>

  <div class="footer-bottom">
    <p>&copy; 2024. All rights reserved.</p>
  </div>
</template>

<script>
export default {
  name: "FooterSection",
};
</script>

<style scoped>
.footer {
  background-color: #333;
  color: #f8f8f8;
  padding: 40px 20px;
  text-align: center;
  border-top: 4px solid #0066cc;
}

.contact {
  margin-bottom: 20px;
}

.contact h2 {
  font-size: 1.8em;
  margin-bottom: 15px;
}

.contact p {
  font-size: 1.2em;
  margin: 5px 0;
}

.contact a {
  color: #4da6ff;
  text-decoration: none;
}

.contact a:hover {
  text-decoration: underline;
}

.footer-links ul {
  list-style: none;
  padding: 0;
  margin: 20px 0;
  display: flex;
  justify-content: center;
  gap: 15px;
}

.footer-links a {
  color: #cccccc;
  text-decoration: none;
  font-size: 1em;
}

.footer-links a:hover {
  color: #4da6ff;
}

.footer-bottom {
  background-color: #222;
  color: #aaaaaa;
  padding: 10px 0;
  text-align: center;
  font-size: 0.9em;
  border-top: 1px solid #444;
}
</style>
