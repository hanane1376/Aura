<!DOCTYPE html>
<html lang="fr">
<head>
  
  <title>Aura.h - Boutique en ligne</title>
  <style>
    body {
      font-family: 'Segoe UI', sans-serif;
      margin: 0;
      padding: 0;
      background-color: #ffeef0; /* rose pastel */
      color: #333;
    }

    header {
      background-color: #fff;
      text-align: center;
      padding: 30px;
      box-shadow: 0 2px 5px rgba(0,0,0,0.1);
    }

    header h1 {
      margin: 0;
      color: #d49ca3;
    }

    header p {
      font-style: italic;
      color: #777;
    }

    .produits {
      display: flex;
      justify-content: center;
      gap: 30px;
      flex-wrap: wrap;
      padding: 40px;
    }

    .produit {
      width: 250px;
      background-color: #fff;
      border: 1px solid #eee;
      border-radius: 15px;
      box-shadow: 0 4px 8px rgba(0,0,0,0.05);
      text-align: center;
      padding: 15px;
      position: relative;
    }

   .produit img {
  width: 100%;
  height: 300px; /* Tu peux ajuster cette valeur selon ce que tu veux */
  object-fit: cover; /* Pour que l’image remplisse bien l’espace sans déformer */
  border-radius: 10px;
  margin-bottom: 10px;
}
    .produit h3 {
      margin: 10px 0 5px;
    }

    .produit p {
      margin: 0 0 10px;
    }

    .produit button {
      background-color: #d49ca3;
      color: white;
      border: none;
      padding: 10px;
      border-radius: 8px;
      cursor: pointer;
      width: 100%;
    }

    .produit button:hover {
      background-color: #c07c84;
    }

    .commande {
      padding: 40px;
      display: none; /* On le cache au début */
      flex-direction: column;
      align-items: center;
    }

    .commande form {
      max-width: 400px;
      width: 100%;
      background-color: #fff;
      border: 2px solid #000;
      border-radius: 12px;
      padding: 30px;
      box-shadow: 0 4px 12px rgba(0,0,0,0.05);
    }

    .commande h2 {
      margin-bottom: 20px;
    }

    label {
      text-align: left;
      display: block;
      margin-top: 10px;
    }

    input, select, textarea {
      width: 100%;
      padding: 10px;
      margin-top: 5px;
      border: 1px solid #ccc;
      border-radius: 8px;
      font-size: 14px;
    }

    button[type="submit"] {
      margin-top: 20px;
      padding: 12px;
      background-color: #d49ca3;
      color: white;
      border: none;
      border-radius: 8px;
      font-size: 16px;
      cursor: pointer;
    }

    button[type="submit"]:hover {
      background-color: #c07c84;
    }

    .contact {
      background-color: #fff;
      padding: 40px;
      text-align: center;
    }

    .contact h2 {
      margin-bottom: 20px;
    }

    .contact form {
      max-width: 500px;
      margin: 0 auto;
      text-align: left;
    }

    footer {
      text-align: center;
      padding: 20px;
      font-size: 14px;
      color: #777;
    }
  </style>
</head>
<body>

  <header>
    <h1>Aura.h</h1>
    <p>L'élégance à portée de clic</p>
  </header>

  <section class="produits">
    <!-- Produit 1 -->
    <div class="produit">
      <img src="imageAura/image0.jpeg" alt="Robe Emeraude">
      <h3>Robe Emeraude</h3>
      <p>Prix : 8500 DA</p>
      <button onclick="ouvrirCommande('Robe Emeraude')">Commander</button>
    </div>

    <!-- Produit 2 -->
    <div class="produit">
      <img src="imageAura/image2.jpeg" alt="Robe bleu nuit">
      <h3>Robe Bleu Nuit</h3>
      <p>Prix : 8800 DA</p>
      <button onclick="ouvrirCommande('Robe Bleu Nuit')">Commander</button>
    </div>

    <!-- Produit 3 -->
    <div class="produit">
      <img src="imageAura/image3.jpeg" alt="Robe beige">
      <h3>Robe Beige Élégante</h3>
      <p>Prix : 9000 DA</p>
      <button onclick="ouvrirCommande('Robe Beige Élégante')">Commander</button>
    </div>

    <!-- Produit 4 -->
    <div class="produit">
      <img src="imageAura/image1.jpeg"  alt="Robe rose poudré">
      <h3>Robe Rose Poudré</h3>
      <p>Prix : 9000 DA</p>
      <button onclick="ouvrirCommande('Robe Rose Poudré')">Commander</button>
    </div>
  </section>

  <section class="commande" id="commandeSection">
    <h2>Formulaire de Commande</h2>
    <form action="mailto:tonemail@gmail.com" method="POST" enctype="text/plain">
      <label for="nom">Nom :</label>
      <input type="text" id="nom" name="nom" required>

      <label for="produit">Produit :</label>
      <input type="text" id="produit" name="produit" readonly>

      <label for="adresse">Adresse :</label>
      <textarea id="adresse" name="adresse" rows="4" required></textarea>

      <button type="submit">Commander</button>
    </form>
  </section>

  <section class="contact">
    <h2>Contactez-nous</h2>
    <form action="mailto:tonemail@gmail.com" method="POST" enctype="text/plain">
      <label for="nom_contact">Votre nom :</label>
      <input type="text" id="nom_contact" name="nom_contact" required>

      <label for="message">Message :</label>
      <textarea id="message" name="message" rows="5" required></textarea>

      <button type="submit">Envoyer</button>
    </form>
  </section>

  <footer>
    <p>© 2025 Aura.h - Tous droits réservés</p>
  </footer>

  <script>
    function ouvrirCommande(nomProduit) {
      document.getElementById("commandeSection").style.display = "flex";
      document.getElementById("produit").value = nomProduit;
      window.scrollTo({
        top: document.getElementById("commandeSection").offsetTop,
        behavior: "smooth"
      });
    }
  </script>

</body>
</html>
