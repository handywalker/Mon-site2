# Mon-site2
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Robe de Cérémonie Bicolore - Boutique</title>
    <style>
        :root {
            --primary-color: #7b2cbf;
            --primary-hover: #5a189a;
            --whatsapp-color: #25D366;
            --text-main: #333;
            --text-muted: #777;
            --bg-color: #f8f9fa;
            --white: #ffffff;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-main);
            display: flex;
            justify-content: center;
            padding: 20px;
        }

        .product-container {
            background: var(--white);
            max-width: 800px;
            width: 100%;
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            overflow: hidden;
            position: relative;
        }

        /* Section Image */
        .image-gallery {
            position: relative;
            background: linear-gradient(135deg, #9d4edd, #3c096c);
            padding: 20px;
            text-align: center;
        }

        .main-image {
            width: 100%;
            max-width: 400px;
            height: auto;
            border-radius: 10px;
            transition: transform 0.3s ease;
        }

        .badge-promo {
            position: absolute;
            top: 20px;
            left: 20px;
            background: #9d4edd;
            color: white;
            padding: 5px 15px;
            border-radius: 20px;
            font-weight: bold;
            font-size: 14px;
            z-index: 10;
        }

        .thumbnails {
            display: flex;
            justify-content: center;
            gap: 10px;
            margin-top: 15px;
        }

        .thumbnail {
            width: 60px;
            height: 60px;
            border-radius: 8px;
            cursor: pointer;
            border: 2px solid transparent;
            transition: 0.2s;
            object-fit: cover;
            background-color: #eee;
        }

        .thumbnail.active {
            border-color: var(--primary-color);
        }

        /* Section Détails */
        .product-details {
            padding: 25px;
        }

        .rating {
            color: #ffb703;
            font-size: 14px;
            margin-bottom: 10px;
        }

        .rating span {
            color: var(--text-muted);
            margin-left: 5px;
        }

        h1 {
            font-size: 24px;
            margin-bottom: 10px;
            line-height: 1.2;
        }

        .description {
            color: var(--text-muted);
            font-size: 15px;
            margin-bottom: 20px;
            line-height: 1.5;
        }

        .price-container {
            display: flex;
            align-items: center;
            gap: 15px;
            margin-bottom: 20px;
        }

        .current-price {
            font-size: 28px;
            font-weight: bold;
            color: var(--primary-color);
        }

        .old-price {
            font-size: 18px;
            color: var(--text-muted);
            text-decoration: line-through;
        }

        /* Options */
        .options-section {
            margin-bottom: 25px;
        }

        .options-label {
            font-weight: bold;
            display: block;
            margin-bottom: 10px;
        }

        .sizes-container {
            display: flex;
            gap: 10px;
            flex-wrap: wrap;
        }

        .size-btn {
            padding: 8px 16px;
            border: 1px solid #ddd;
            background: var(--white);
            border-radius: 5px;
            cursor: pointer;
            transition: 0.2s;
            font-weight: 500;
        }

        .size-btn:hover {
            border-color: var(--primary-color);
        }

        .size-btn.selected {
            background: var(--primary-color);
            color: white;
            border-color: var(--primary-color);
        }

        /* Actions */
        .actions {
            display: flex;
            flex-direction: column;
            gap: 15px;
        }

        .btn-commander {
            background: var(--primary-color);
            color: white;
            border: none;
            padding: 15px;
            border-radius: 10px;
            font-size: 18px;
            font-weight: bold;
            cursor: pointer;
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 10px;
            transition: 0.3s;
        }

        .btn-commander:hover {
            background: var(--primary-hover);
        }

        .social-actions {
            display: flex;
            gap: 10px;
        }

        .btn-whatsapp {
            background: var(--whatsapp-color);
            color: white;
            border: none;
            padding: 15px;
            border-radius: 50%;
            width: 50px;
            height: 50px;
            font-size: 24px;
            cursor: pointer;
            display: flex;
            justify-content: center;
            align-items: center;
            transition: 0.3s;
        }

        .btn-share {
            background: #f0f0f0;
            color: var(--text-main);
            border: none;
            padding: 15px;
            border-radius: 10px;
            flex-grow: 1;
            font-weight: bold;
            cursor: pointer;
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 8px;
            transition: 0.3s;
        }

        .btn-share:hover { background: #e0e0e0; }
        .btn-whatsapp:hover { background: #128C7E; }

        /* Notification */
        .toast {
            position: fixed;
            bottom: 20px;
            left: 50%;
            transform: translateX(-50%) translateY(100px);
            background: #333;
            color: white;
            padding: 12px 24px;
            border-radius: 30px;
            font-size: 14px;
            opacity: 0;
            transition: 0.4s;
            z-index: 100;
        }

        .toast.show {
            transform: translateX(-50%) translateY(0);
            opacity: 1;
        }

        /* Responsive */
        @media (min-width: 768px) {
            .product-container {
                display: flex;
            }
            .image-gallery {
                width: 50%;
                display: flex;
                flex-direction: column;
                justify-content: center;
            }
            .product-details {
                width: 50%;
            }
            .actions {
                flex-direction: row;
            }
            .btn-commander {
                flex-grow: 1;
            }
            .social-actions {
                width: auto;
            }
        }
    </style>
</head>
<body>

    <div class="product-container">
        <!-- Section Images -->
        <div class="image-gallery">
            <div class="badge-promo">-25%</div>
            <!-- Remplacez l'URL par votre vraie image -->
            <img src="https://via.placeholder.com/400x500.png?text=Robe+Turquoise" alt="Robe de Cérémonie" class="main-image" id="mainImage">
            
            <div class="thumbnails">
                <img src="https://via.placeholder.com/400x500.png?text=Robe+Turquoise" class="thumbnail active" onclick="changeImage(this, 'https://via.placeholder.com/400x500.png?text=Robe+Turquoise')">
                <img src="https://via.placeholder.com/400x500.png?text=Dos+de+la+Robe" class="thumbnail" onclick="changeImage(this, 'https://via.placeholder.com/400x500.png?text=Dos+de+la+Robe')">
                <img src="https://via.placeholder.com/400x500.png?text=Details+Perles" class="thumbnail" onclick="changeImage(this, 'https://via.placeholder.com/400x500.png?text=Details+Perles')">
            </div>
        </div>

        <!-- Section Détails -->
        <div class="product-details">
            <div class="rating">
                ⭐⭐⭐⭐⭐ <span>Excellent | Noté 4,8 (2000 clients)</span>
            </div>

            <h1>Robe de Cérémonie Bicolore Blanc et Turquoise</h1>
            
            <p class="description">
                Élégante, pudique et raffinée : la robe qui vous met en valeur pour chaque grande occasion. Ceinture ornée de perles pour une touche d'élégance.
            </p>

            <div class="price-container">
                <span class="current-price">4 500 XOF</span>
                <span class="old-price">6 000 XOF</span>
            </div>

            <div class="options-section">
                <span class="options-label">Sélectionnez votre taille :</span>
                <div class="sizes-container" id="sizeContainer">
                    <button class="size-btn" onclick="selectSize(this)">S</button>
                    <button class="size-btn" onclick="selectSize(this)">M</button>
                    <button class="size-btn" onclick="selectSize(this)">L</button>
                    <button class="size-btn" onclick="selectSize(this)">XL</button>
                    <button class="size-btn" onclick="selectSize(this)">XXL</button>
                </div>
            </div>

            <div class="actions">
                <button class="btn-commander" onclick="addToCart()">
                    🛒 Commander
                </button>
                <div class="social-actions">
                    <button class="btn-whatsapp" onclick="contactWhatsApp()" title="Commander sur WhatsApp">
                        <!-- Icône SVG WhatsApp -->
                        <svg width="24" height="24" viewBox="0 0 24 24" fill="white" xmlns="http://www.w3.org/2000/svg">
                            <path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413z"/>
                        </svg>
                    </button>
                    <button class="btn-share" onclick="shareProduct()">
                        🔗 Partager
                    </button>
                </div>
            </div>
        </div>
    </div>

    <!-- Notification Toast -->
    <div class="toast" id="toast">Produit ajouté au panier !</div>

    <script>
        // Gestion de la galerie d'images
        function changeImage(element, src) {
            document.getElementById('mainImage').src = src;
            
            // Gérer la classe active
            let thumbnails = document.querySelectorAll('.thumbnail');
            thumbnails.forEach(thumb => thumb.classList.remove('active'));
            element.classList.add('active');
        }

        // Gestion de la sélection de la taille
        let selectedSize = null;
        function selectSize(element) {
            let buttons = document.querySelectorAll('.size-btn');
            buttons.forEach(btn => btn.classList.remove('selected'));
            
            element.classList.add('selected');
            selectedSize = element.innerText;
        }

        // Fonction pour afficher la notification
        function showToast(message) {
            const toast = document.getElementById('toast');
            toast.innerText = message;
            toast.classList.add('show');
            
            setTimeout(() => {
                toast.classList.remove('show');
            }, 3000);
        }

        // Action Commander
        function addToCart() {
            if (!selectedSize) {
                showToast("⚠️ Veuillez sélectionner une taille !");
                return;
            }
            showToast(`✅ Taille ${selectedSize} ajoutée au panier !`);
            // Ici vous pouvez ajouter la logique pour envoyer les données à votre backend
        }

        // Action WhatsApp
        function contactWhatsApp() {
            let message = `Bonjour, je suis intéressé(e) par la "Robe de Cérémonie Bicolore Blanc et Turquoise" à 4 500 XOF.`;
            if (selectedSize) {
                message += ` J'ai choisi la taille ${selectedSize}.`;
            } else {
                message += ` Pouvez-vous m'aider pour la taille ?`;
            }
            
            // Remplacez le numéro par le vôtre (format international sans le +)
            let phoneNumber = "2250000000000"; 
            let url = `https://wa.me/${phoneNumber}?text=${encodeURIComponent(message)}`;
            window.open(url, '_blank');
        }

        // Action Partager (Réseaux sociaux)
        function shareProduct() {
            if (navigator.share) {
                navigator.share({
                    title: 'Robe de Cérémonie Bicolore',
                    text: 'Découvrez cette magnifique robe sur notre boutique !',
                    url: window.location.href,
                }).catch(console.error);
            } else {
                // Fallback pour les navigateurs qui ne supportent pas l'API Share
                showToast("🔗 Lien copié dans le presse-papiers !");
                navigator.clipboard.writeText(window.location.href);
            }
        }
    </script>
</body>
</html>
