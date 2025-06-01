<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Global Express - Blog</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500;600;700&family=Open+Sans:wght@400;600&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Open Sans', sans-serif;
            line-height: 1.6;
            color: #333;
            background-color: #f8f9fa;
        }
        
        header {
            background: linear-gradient(135deg, #1a2a6c, #2a4d8e);
            color: white;
            padding: 1.5rem 0;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
            position: sticky;
            top: 0;
            z-index: 100;
        }
        
        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
        }
        
        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            display: flex;
            align-items: center;
            gap: 12px;
        }
        
        .logo h1 {
            font-family: 'Montserrat', sans-serif;
            font-weight: 700;
            font-size: 1.8rem;
        }
        
        .logo-icon {
            background-color: #ff6b6b;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
        }
        
        nav ul {
            display: flex;
            list-style: none;
            gap: 2rem;
        }
        
        nav a {
            color: white;
            text-decoration: none;
            font-weight: 500;
            font-size: 1.1rem;
            transition: all 0.3s ease;
            padding: 0.5rem;
            border-radius: 4px;
        }
        
        nav a:hover {
            background-color: rgba(255, 255, 255, 0.1);
        }
        
        .hero {
            background: linear-gradient(rgba(0, 0, 0, 0.6), rgba(0, 0, 0, 0.6)), 
                        url('https://images.unsplash.com/photo-1499750310107-5fef28a66643?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1170&q=80');
            background-size: cover;
            background-position: center;
            height: 400px;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: white;
            margin-bottom: 3rem;
        }
        
        .hero-content {
            max-width: 800px;
            padding: 2rem;
        }
        
        .hero h2 {
            font-family: 'Montserrat', sans-serif;
            font-size: 2.8rem;
            margin-bottom: 1rem;
            text-shadow: 0 2px 4px rgba(0, 0, 0, 0.5);
        }
        
        .hero p {
            font-size: 1.2rem;
            margin-bottom: 1.5rem;
            max-width: 700px;
            margin-left: auto;
            margin-right: auto;
        }
        
        .btn {
            display: inline-block;
            background-color: #ff6b6b;
            color: white;
            padding: 0.8rem 1.8rem;
            border-radius: 30px;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s ease;
            border: none;
            cursor: pointer;
            font-size: 1rem;
        }
        
        .btn:hover {
            background-color: #ff5252;
            transform: translateY(-2px);
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
        }
        
        .main-content {
            display: flex;
            gap: 2rem;
            margin-bottom: 3rem;
        }
        
        .articles {
            flex: 3;
        }
        
        .sidebar {
            flex: 1;
        }
        
        .blog-post {
            background-color: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.08);
            margin-bottom: 2rem;
            transition: transform 0.3s ease;
        }
        
        .blog-post:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.12);
        }
        
        .post-img {
            width: 100%;
            height: 250px;
            object-fit: cover;
        }
        
        .post-content {
            padding: 1.5rem;
        }
        
        .post-meta {
            display: flex;
            gap: 1rem;
            color: #6c757d;
            margin-bottom: 0.8rem;
            font-size: 0.9rem;
        }
        
        .post-title {
            font-family: 'Montserrat', sans-serif;
            font-size: 1.8rem;
            margin-bottom: 1rem;
            color: #2a4d8e;
        }
        
        .post-excerpt {
            margin-bottom: 1.5rem;
            color: #495057;
        }
        
        .read-more {
            display: inline-flex;
            align-items: center;
            gap: 5px;
            color: #2a4d8e;
            font-weight: 600;
            text-decoration: none;
        }
        
        .read-more:hover {
            text-decoration: underline;
        }
        
        .sidebar-widget {
            background-color: white;
            border-radius: 10px;
            padding: 1.5rem;
            margin-bottom: 2rem;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.08);
        }
        
        .widget-title {
            font-family: 'Montserrat', sans-serif;
            font-size: 1.4rem;
            margin-bottom: 1.2rem;
            color: #2a4d8e;
            padding-bottom: 0.5rem;
            border-bottom: 2px solid #ff6b6b;
        }
        
        .popular-posts {
            display: flex;
            flex-direction: column;
            gap: 1rem;
        }
        
        .popular-post {
            display: flex;
            gap: 1rem;
            padding-bottom: 1rem;
            border-bottom: 1px solid #e9ecef;
        }
        
        .popular-post:last-child {
            border-bottom: none;
            padding-bottom: 0;
        }
        
        .popular-post-img {
            width: 80px;
            height: 80px;
            border-radius: 8px;
            object-fit: cover;
        }
        
        .popular-post-content h4 {
            font-size: 1rem;
            margin-bottom: 0.3rem;
        }
        
        .popular-post-content p {
            font-size: 0.85rem;
            color: #6c757d;
        }
        
        .categories ul {
            list-style: none;
        }
        
        .categories li {
            padding: 0.6rem 0;
            border-bottom: 1px solid #e9ecef;
        }
        
        .categories li:last-child {
            border-bottom: none;
        }
        
        .categories a {
            color: #495057;
            text-decoration: none;
            display: flex;
            justify-content: space-between;
        }
        
        .categories a:hover {
            color: #2a4d8e;
        }
        
        .tag-cloud {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
        }
        
        .tag {
            background-color: #e9ecef;
            color: #495057;
            padding: 0.4rem 0.8rem;
            border-radius: 30px;
            font-size: 0.9rem;
            text-decoration: none;
            transition: all 0.3s ease;
        }
        
        .tag:hover {
            background-color: #2a4d8e;
            color: white;
        }
        
        .newsletter form {
            display: flex;
            flex-direction: column;
            gap: 1rem;
        }
        
        .newsletter input {
            padding: 0.8rem;
            border: 1px solid #ced4da;
            border-radius: 4px;
            font-family: inherit;
            font-size: 1rem;
        }
        
        footer {
            background-color: #1a2a6c;
            color: white;
            padding: 3rem 0 1.5rem;
        }
        
        .footer-content {
            display: flex;
            justify-content: space-between;
            gap: 2rem;
            margin-bottom: 2rem;
        }
        
        .footer-column {
            flex: 1;
        }
        
        .footer-column h3 {
            font-family: 'Montserrat', sans-serif;
            font-size: 1.4rem;
            margin-bottom: 1.2rem;
            position: relative;
            padding-bottom: 0.5rem;
        }
        
        .footer-column h3::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 50px;
            height: 2px;
            background-color: #ff6b6b;
        }
        
        .footer-column p {
            margin-bottom: 1rem;
        }
        
        .footer-links {
            list-style: none;
        }
        
        .footer-links li {
            margin-bottom: 0.6rem;
        }
        
        .footer-links a {
            color: #adb5bd;
            text-decoration: none;
            transition: color 0.3s ease;
        }
        
        .footer-links a:hover {
            color: white;
        }
        
        .social-links {
            display: flex;
            gap: 1rem;
            margin-top: 1rem;
        }
        
        .social-links a {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 40px;
            height: 40px;
            background-color: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            color: white;
            text-decoration: none;
            transition: all 0.3s ease;
        }
        
        .social-links a:hover {
            background-color: #ff6b6b;
            transform: translateY(-3px);
        }
        
        .copyright {
            text-align: center;
            padding-top: 1.5rem;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            color: #adb5bd;
            font-size: 0.9rem;
        }
        
        /* Responsive design */
        @media (max-width: 900px) {
            .main-content {
                flex-direction: column;
            }
            
            .footer-content {
                flex-direction: column;
            }
            
            nav ul {
                gap: 1rem;
            }
        }
        
        @media (max-width: 768px) {
            .header-content {
                flex-direction: column;
                gap: 1rem;
            }
            
            nav ul {
                flex-wrap: wrap;
                justify-content: center;
            }
            
            .hero h2 {
                font-size: 2.2rem;
            }
            
            .hero {
                height: 350px;
            }
        }
        
        @media (max-width: 480px) {
            .post-meta {
                flex-direction: column;
                gap: 0.3rem;
            }
            
            .post-title {
                font-size: 1.5rem;
            }
            
            .hero h2 {
                font-size: 1.8rem;
            }
            
            .hero p {
                font-size: 1rem;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container">
            <div class="header-content">
                <div class="logo">
                    <div class="logo-icon">
                        <i class="fas fa-shipping-fast"></i>
                    </div>
                    <h1>Global Express</h1>
                </div>
                <nav>
                    <ul>
                        <li><a href="#"><i class="fas fa-home"></i> Accueil</a></li>
                        <li><a href="#"><i class="fas fa-newspaper"></i> Blog</a></li>
                        <li><a href="#"><i class="fas fa-tags"></i> Services</a></li>
                        <li><a href="#"><i class="fas fa-info-circle"></i> À propos</a></li>
                        <li><a href="#"><i class="fas fa-envelope"></i> Contact</a></li>
                    </ul>
                </nav>
            </div>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="hero-content">
            <h2>Le Blog Global Express</h2>
            <p>Découvrez les dernières actualités, conseils et innovations dans le domaine de la logistique express et du transport international.</p>
            <a href="#" class="btn">S'abonner à la newsletter</a>
        </div>
    </section>

    <!-- Main Content -->
    <div class="container">
        <div class="main-content">
            <!-- Articles Section -->
            <div class="articles">
                <!-- Article 1 -->
                <article class="blog-post">
                    <img src="https://images.unsplash.com/photo-1605656816944-971cd5c1407f?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1170&q=80" 
                         alt="Logistique moderne" class="post-img">
                    <div class="post-content">
                        <div class="post-meta">
                            <span><i class="far fa-calendar"></i> 23 mai 2025</span>
                            <span><i class="far fa-user"></i> Richard José </span>
                            <span><i class="far fa-comments"></i> 12 commentaires</span>
                        </div>
                        <h2 class="post-title">L'avenir de la logistique express en 2025</h2>
                        <p class="post-excerpt">
                            Découvrez comment les nouvelles technologies révolutionnent le secteur de la logistique express. 
                            Des drones de livraison aux entrepôts automatisés, le futur est déjà là. 
                            Nous explorons les tendances qui façonneront l'industrie dans les années à venir...
                        </p>
                        <a href="#" class="read-more">Lire la suite <i class="fas fa-arrow-right"></i></a>
                    </div>
                </article>

                <!-- Article 2 -->
                <article class="blog-post">
                    <img src="https://images.unsplash.com/photo-1533750349088-cd871a92f312?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1170&q=80" 
                         alt="Emballage écologique" class="post-img">
                    <div class="post-content">
                        <div class="post-meta">
                            <span><i class="far fa-calendar"></i> 18 mai 2025</span>
                            <span><i class="far fa-user"></i> Marie Leroy</span>
                            <span><i class="far fa-comments"></i> 8 commentaires</span>
                        </div>
                        <h2 class="post-title">Emballages écologiques : Notre engagement pour la planète</h2>
                        <p class="post-excerpt">
                            Chez Global Express, nous avons fait le choix de l'écologie. Découvrez notre nouvelle gamme 
                            d'emballages 100% recyclables et biodégradables. Comment ces innovations réduisent notre empreinte 
                            carbone tout en garantissant une protection optimale de vos colis...
                        </p>
                        <a href="#" class="read-more">Lire la suite <i class="fas fa-arrow-right"></i></a>
                    </div>
                </article>

                <!-- Article 3 -->
                <article class="blog-post">
                    <img src="https://images.unsplash.com/photo-1551830820-330a71b99659?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1170&q=80" 
                         alt="Suivi de colis" class="post-img">
                    <div class="post-content">
                        <div class="post-meta">
                            <span><i class="far fa-calendar"></i> 12 mai 2025</span>
                            <span><i class="far fa-user"></i> Thomas Martin</span>
                            <span><i class="far fa-comments"></i> 15 commentaires</span>
                        </div>
                        <h2 class="post-title">Optimisez votre chaîne d'approvisionnement avec notre nouvelle plateforme</h2>
                        <p class="post-excerpt">
                            Notre nouvelle plateforme de gestion logistique est désormais disponible. Suivi en temps réel, 
                            analytics avancés, intégration API : tous les outils pour optimiser votre supply chain. 
                            Découvrez comment cette solution peut transformer votre entreprise...
                        </p>
                        <a href="#" class="read-more">Lire la suite <i class="fas fa-arrow-right"></i></a>
                    </div>
                </article>
            </div>

            <!-- Sidebar -->
            <aside class="sidebar">
                <!-- About Widget -->
                <div class="sidebar-widget">
                    <h3 class="widget-title">À propos</h3>
                    <p>Global Express est un leader dans le secteur de la logistique express, offrant des solutions innovantes pour le transport national et international.</p>
                    <p>Notre mission : livrer rapidement, efficacement et de manière durable.</p>
                </div>

                <!-- Popular Posts -->
                <div class="sidebar-widget">
                    <h3 class="widget-title">Articles populaires</h3>
                    <div class="popular-posts">
                        <div class="popular-post">
                            <img src="https://images.unsplash.com/photo-1519501025264-65ba15a82390?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=400&q=80" 
                                 alt="Entrepôt automatisé" class="popular-post-img">
                            <div class="popular-post-content">
                                <h4>Automatisation des entrepôts : Ce qui change</h4>
                                <p><i class="far fa-calendar"></i> 5 mai 2025</p>
                            </div>
                        </div>
                        <div class="popular-post">
                            <img src="https://images.unsplash.com/photo-1592921870789-04563d55041c?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=400&q=80" 
                                 alt="Livraison drone" class="popular-post-img">
                            <div class="popular-post-content">
                                <h4>Les drones de livraison : Rêve ou réalité?</h4>
                                <p><i class="far fa-calendar"></i> 28 avril 2025</p>
                            </div>
                        </div>
                        <div class="popular-post">
                            <img src="https://images.unsplash.com/photo-1450101499163-c8848c66ca85?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=400&q=80" 
                                 alt="Emballage durable" class="popular-post-img">
                            <div class="popular-post-content">
                                <h4>5 façons de rendre vos emballages plus durables</h4>
                                <p><i class="far fa-calendar"></i> 20 avril 2025</p>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Categories -->
                <div class="sidebar-widget categories">
                    <h3 class="widget-title">Catégories</h3>
                    <ul>
                        <li><a href="#">Innovations technologiques <span>(12)</span></a></li>
                        <li><a href="#">Développement durable <span>(8)</span></a></li>
                        <li><a href="#">Conseils pratiques <span>(15)</span></a></li>
                        <li><a href="#">Actualités de l'entreprise <span>(6)</span></a></li>
                        <li><a href="#">Transport international <span>(9)</span></a></li>
                    </ul>
                </div>

                <!-- Tags -->
                <div class="sidebar-widget">
                    <h3 class="widget-title">Tags populaires</h3>
                    <div class="tag-cloud">
                        <a href="#" class="tag">logistique</a>
                        <a href="#" class="tag">express</a>
                        <a href="#" class="tag">livraison</a>
                        <a href="#" class="tag">durabilité</a>
                        <a href="#" class="tag">technologie</a>
                        <a href="#" class="tag">supply chain</a>
                        <a href="#" class="tag">emballage</a>
                        <a href="#" class="tag">international</a>
                    </div>
                </div>

                <!-- Newsletter -->
                <div class="sidebar-widget newsletter">
                    <h3 class="widget-title">Newsletter</h3>
                    <p>Inscrivez-vous pour recevoir nos dernières actualités et conseils.</p>
                    <form>
                        <input type="text" placeholder="Votre nom">
                        <input type="email" placeholder="Votre email">
                        <button type="submit" class="btn">S'abonner</button>
                    </form>
                </div>
            </aside>
        </div>
    </div>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-column">
                    <h3>Global Express</h3>
                    <p>Votre partenaire de confiance pour des solutions logistiques rapides, fiables et durables à l'échelle mondiale.</p>
                    <div class="social-links">
                        <a href="#"><i class="fab fa-facebook-f"></i></a>
                        <a href="#"><i class="fab fa-twitter"></i></a>
                        <a href="#"><i class="fab fa-instagram"></i></a>
                        <a href="#"><i class="fab fa-linkedin-in"></i></a>
                        <a href="#"><i class="fab fa-youtube"></i></a>
                    </div>
                </div>
                
                <div class="footer-column">
                    <h3>Liens rapides</h3>
                    <ul class="footer-links">
                        <li><a href="#"><i class="fas fa-chevron-right"></i> Accueil</a></li>
                        <li><a href="#"><i class="fas fa-chevron-right"></i> Services</a></li>
                        <li><a href="#"><i class="fas fa-chevron-right"></i> Solutions</a></li>
                        <li><a href="#"><i class="fas fa-chevron-right"></i> À propos</a></li>
                        <li><a href="#"><i class="fas fa-chevron-right"></i> Blog</a></li>
                        <li><a href="#"><i class="fas fa-chevron-right"></i> Contact</a></li>
                    </ul>
                </div>
                
                <div class="footer-column">
                    <h3>Nos services</h3>
                    <ul class="footer-links">
                        <li><a href="#"><i class="fas fa-chevron-right"></i> Livraison express</a></li>
                        <li><a href="#"><i class="fas fa-chevron-right"></i> Transport international</a></li>
                        <li><a href="#"><i class="fas fa-chevron-right"></i> Logistique sur mesure</a></li>
                        <li><a href="#"><i class="fas fa-chevron-right"></i> Stockage et entreposage</a></li>
                        <li><a href="#"><i class="fas fa-chevron-right"></i> Solutions e-commerce</a></li>
                        <li><a href="#"><i class="fas fa-chevron-right"></i> Suivi en temps réel</a></li>
                    </ul>
                </div>
                
                <div class="footer-column">
                    <h3>Contact</h3>
                    <p><i class="fas fa-map-marker-alt"></i> 123 Rue de la Logistique, 75000 Paris</p>
                    <p><i class="fas fa-phone"></i> +509</p>
                    <p><i class="fas fa-envelope"></i> contact@glexal-express.fr</p>
                    <p><i class="fas fa-clock"></i> Lun-Ven: 8h-19h | Sam: 9h-13h</p>
                </div>
            </div>
            
            <div class="copyright">
                <p>&copy; 2025 Global Express. Tous droits réservés. | Conçu avec <i class="fas fa-heart" style="color:#ff6b6b;"></i> pour une logistique meilleure</p>
            </div>
        </div>
    </footer>
</body>
</html>