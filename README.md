<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>INKDAYS - Agendas Personalizadas</title>
    <style>

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Stack Sans Text', sans-serif;
            font-weight: 400;
            color: #333;
            line-height: 1.6;
        }

        h1, h2, h3, .logo {
            font-family: 'Playfair Display', serif;
        }

        /* Header */
        header {
            background: linear-gradient(135deg, #2c3e50 0%, #496886 100%);
            color: white;
            padding: 1rem 0;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }

        nav {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 2rem;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: bold;
            letter-spacing: 2px;
        }

        .nav-links {
            display: flex;
            gap: 2rem;
            list-style: none;
        }

        .nav-links a {
            color: white;
            text-decoration: none;
            transition: color 0.3s;
            font-weight: 500;
        }

        .nav-links a:hover {
            color: #f39c12;
        }

        /* Hero Section */
        .hero {
            margin-top: 70px;
            background-image: url('https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRPpid3l6kfkUoLixiXv2r8FxC5oa7qccVs6h_a6pPzpXPgkU_L3gUIGE00KUD9Jtlve3g&usqp=CAU');
            color: white;
            padding: 6rem 2rem;
            text-align: center;
        }

        .hero h1 {
            font-size: 3rem;
            margin-bottom: 1rem;
            animation: fadeInUp 1s ease;
        }

        .hero p {
            font-size: 1.3rem;
            margin-bottom: 2rem;
            animation: fadeInUp 1.2s ease;
        }

        .btn {
            display: inline-block;
            padding: 1rem 2.5rem;
            background: #f39c12;
            color: white;
            text-decoration: none;
            border-radius: 50px;
            font-weight: bold;
            transition: all 0.3s;
            border: none;
            cursor: pointer;
            font-size: 1rem;
        }

        .btn:hover {
            background: #e67e22;
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(0,0,0,0.2);
        }

        /* Productos */
        .productos {
            max-width: 1200px;
            margin: 4rem auto;
            padding: 0 2rem;
        }

        .section-title {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 3rem;
            color: #2c3e50;
        }

        .productos-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .producto-card {
            background: white;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            transition: transform 0.3s, box-shadow 0.3s;
            cursor: pointer;
        }

        .producto-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0,0,0,0.2);
        }

        .producto-img {
            width: 100%;
            height: 300px;
            background-size: cover;
            background-position: center;
            background-repeat: no-repeat;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .producto-info {
            padding: 1.5rem;
        }

        .producto-info h3 {
            font-size: 1.5rem;
            margin-bottom: 0.5rem;
            color: #2c3e50;
        }

        .producto-info p {
            color: #7f8c8d;
            margin-bottom: 1rem;
        }

        .precio {
            font-size: 1.8rem;
            color: #27ae60;
            font-weight: bold;
            margin-bottom: 1rem;
        }

        /* Características */
        .caracteristicas {
            background: #9fc4e9;
            padding: 4rem 2rem;
        }

        .caracteristicas-grid {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .caracteristica {
            text-align: center;
            padding: 2rem;
            background: white;
            border-radius: 10px;
            transition: transform 0.3s;
        }

        .caracteristica:hover {
            transform: scale(1.05);
        }

        .caracteristica-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
        }

        .caracteristica h3 {
            margin-bottom: 1rem;
            color: #2c3e50;
        }

        /* Testimonios */
        .testimonios {
            max-width: 1200px;
            margin: 4rem auto;
            padding: 0 2rem;
        }

        .testimonios-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .testimonio {
            background: #fff;
            padding: 2rem;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }

        .testimonio-texto {
            font-style: italic;
            margin-bottom: 1rem;
            color: #555;
        }

        .testimonio-autor {
            font-weight: bold;
            color: #2c3e50;
        }

        /* CTA Final */
        .cta-final {
            background: linear-gradient(135deg, #2c3e50 0%, #496886 100%);
            color: white;
            padding: 4rem 2rem;
            text-align: center;
        }

        .cta-final h2 {
            font-size: 2.5rem;
            margin-bottom: 1rem;
        }

        .cta-final p {
            font-size: 1.2rem;
            margin-bottom: 2rem;
        }

        /* Footer */
        footer {
            background: #2c3e50;
            color: white;
            padding: 2rem;
            text-align: center;
        }

        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 2rem;
            margin-bottom: 2rem;
        }

        .footer-section h3 {
            margin-bottom: 1rem;
        }

        .footer-section ul {
            list-style: none;
        }

        .footer-section ul li {
            margin-bottom: 0.5rem;
        }

        .footer-section a {
            color: #ecf0f1;
            text-decoration: none;
            transition: color 0.3s;
        }

        .footer-section a:hover {
            color: #f39c12;
        }

        .copyright {
            margin-top: 2rem;
            padding-top: 2rem;
            border-top: 1px solid #34495e;
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Responsive */
        @media (max-width: 768px) {
            .hero h1 {
                font-size: 2rem;
            }
            
            .hero p {
                font-size: 1rem;
            }
            
            .nav-links {
                gap: 1rem;
            }
            
            .section-title {
                font-size: 2rem;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <nav>
            <div class="logo">INKDAYS</div>
            <ul class="nav-links">
                <li><a href="#inicio">Inicio</a></li>
                <li><a href="#productos">Productos</a></li>
                <li><a href="#sobre-nosotros">Sobre Nosotros</a></li>
                <li><a href="#contacto">Contacto</a></li>
            </ul>
        </nav>
    </header>

    <!-- Hero Section -->
    <section class="hero" id="inicio">
        <h1>Organiza tu vida con estilo</h1>
        <p>Agendas personalizadas diseñadas para reflejar tu personalidad única</p>
        <a href="#productos" class="btn">Ver Colección</a>
    </section>

    <!-- Productos -->
    <section class="productos" id="productos">
        <h2 class="section-title">Nuestras Agendas</h2>
        <div class="productos-grid">
            <div class="producto-card">
                <div class="producto-img" style="background-image: url('https://wongfood.vtexassets.com/arquivos/ids/788499/AGENDA-2026-STITCH-1-351704471.jpg?v=638920103859900000');"></div>
                <div class="producto-info">
                    <h3>Agenda 2026 - Stich</h3>
                    <p>Agenda resistente con portada ilustrada de Stitch; ideal para apuntes diarios y notas rápidas.</p>
                    <div class="precio">S/.49.90</div>
                    <button class="btn">Comprar Ahora</button>
                </div>
            </div>

            <div class="producto-card">
                <div class="producto-img" style="background-image: url('https://media.falabella.com/falabellaPE/133224608_01/w=1500,h=1500,fit=pad');"></div>
                <div class="producto-info">
                    <h3>Agenda 2026 - Spiderman</h3>
                    <p>Agenda compacta con portada de Spiderman y cierre lateral; perfecta para organizar tareas y recordatorios.</p>
                    <div class="precio">S/.35.90</div>
                    <button class="btn">Comprar Ahora</button>
                </div>
            </div>

            <div class="producto-card">
                <div class="producto-img" style="background-image: url('https://www.dgnottas.com/cdn/shop/files/19_30f2a94c-d54d-4cc3-8681-647e8892a122_1445x.png?v=1759429597');"></div>
                <div class="producto-info">
                    <h3>Agenda 2026 - Hello Kitty</h3>
                    <p>Agenda de acabado brillante con diseño de Hello Kitty; incluye secciones prácticas para tu planificación.</p>
                    <div class="precio">S/.45.90</div>
                    <button class="btn">Comprar Ahora</button>
                </div>
            </div>

            <div class="producto-card">
                <div class="producto-img" style="background-image: url('https://m.media-amazon.com/images/I/51-3PFwWQBL.jpg');"></div>
                <div class="producto-info">
                    <h3>Agenda 2026 - CR7</h3>
                    <p>Con diseño inspirado en Cristiano Ronaldo, incluye páginas de acuarela y espacio ideal para tus bocetos.</p>
                    <div class="precio">S/52.90</div>
                    <button class="btn">Comprar Ahora</button>
                </div>
            </div>

            <div class="producto-card">
                <div class="producto-img" style="background-image: url('https://down-br.img.susercontent.com/file/br-11134207-7r98o-m5qelr3rzdjkf3');"></div>
                <div class="producto-info">
                    <h3>Agenda 2026 - Neymar Jr.</h3>
                    <p>Con portada de Neymar Jr., con páginas de acuarela y secciones perfectas para dibujos y apuntes.</p>
                    <div class="precio">S/49.90</div>
                    <button class="btn">Comprar Ahora</button>
                </div>
            </div>

            <div class="producto-card">
                <div class="producto-img" style="background-image: url('https://acdn-us.mitiendanube.com/stores/002/291/038/products/mockup-agenda-messi-101-ead1d1d26babe7e33f16722403666222-480-0.webp');"></div>
                <div class="producto-info">
                    <h3>Agenda 2026 - Messi</h3>
                    <p>Diseño basado en la camiseta albiceleste del 10. Contiene páginas de acuarela y espacio para crear tus propios bocetos.</p>
                    <div class="precio">S/52.90</div>
                    <button class="btn">Comprar Ahora</button>
                </div>
            </div>

            <div class="producto-card">
                <div class="producto-img" style="background-image: url('https://lumen.com.mx/Content/Images/productPics/agenda-snoopy-13x18cm-dia-por-pagina-26-sku-354049.jpg');"></div>
                <div class="producto-info">
                    <h3>Agenda 2026 - Snoopy</h3>
                    <p>Un toque tierno y relajado con Snoopy. Ideal para quienes quieren una agenda divertida que inspire buen humor cada día.</p>
                    <div class="precio">S/42.90</div>
                    <button class="btn">Comprar Ahora</button>
                </div>
            </div>

            <div class="producto-card">
                <div class="producto-img" style="background-image: url('https://production-tailoy-repo-magento-statics.s3.amazonaws.com/imagenes/872x872/productos/i/b/r/brief-planner-2026-kuromi-103004-default-1.jpg');"></div>
                <div class="producto-info">
                    <h3>Agenda 2026 - Kuromi</h3>
                    <p>Perfecta para los que aman el estilo rebelde-cute. Kuromi le da personalidad a tus notas y te acompaña en cada plan.</p>
                    <div class="precio">S/39.90</div>
                    <button class="btn">Comprar Ahora</button>
                </div>
            </div>

            <div class="producto-card">
                <div class="producto-img" style="background-image: url('https://img.elo7.com.br/product/zoom/473F057/agenda-escolar-my-melody-2023-1-dia-por-pag-turma-da-hello-kitty.jpg');"></div>
                <div class="producto-info">
                    <h3>Agenda 2026 - My Melody</h3>
                    <p>Suaves tonos rosados y ternura total. My Melody convierte tu planificación en un espacio dulce y lleno de encanto.</p>
                    <div class="precio">S/39.90</div>
                    <button class="btn">Comprar Ahora</button>
                    
                    
                </div>
            </div>
        </div>
    </section>

    <!-- Características -->
    <section class="caracteristicas">
        <h2 class="section-title">¿Por qué elegir InkDays?</h2>
        <div class="caracteristicas-grid">
            <div class="caracteristica">
                <div class="caracteristica-icon">✨</div>
                <h3>100% Personalizable</h3>
                <p>Elige colores, diseños y agrega tu nombre o logo</p>
            </div>
            <div class="caracteristica">
                <div class="caracteristica-icon">🚚</div>
                <h3>Envío Gratis</h3>
                <p>En compras mayores a S/.30.00</p>
            </div>
            <div class="caracteristica">
                <div class="caracteristica-icon">🌱</div>
                <h3>Eco-Friendly</h3>
                <p>Papel reciclado y procesos sostenibles</p>
            </div>
            <div class="caracteristica">
                <div class="caracteristica-icon">💎</div>
                <h3>Calidad Premium</h3>
                <p>Materiales de primera calidad garantizados</p>
            </div>
        </div>
    </section>

    <!-- Testimonios -->
    <section class="testimonios">
        <h2 class="section-title">Lo que dicen nuestros clientes</h2>
        <div class="testimonios-grid">
            <div class="testimonio">
                <p class="testimonio-texto">"La mejor agenda que he tenido. La personalización es increíble y la calidad supera mis expectativas."</p>
                <p class="testimonio-autor">- Keyla Carhuapoma</p>
            </div>
            <div class="testimonio">
                <p class="testimonio-texto">"Perfecto para mi negocio. La agenda ejecutiva tiene todo lo que necesito para organizar mi día."</p>
                <p class="testimonio-autor">- Hendrix Bilkowskij</p>
            </div>
            <div class="testimonio">
                <p class="testimonio-texto">"Me encanta poder diseñar mi propia agenda. Es única y refleja mi estilo personal."</p>
                <p class="testimonio-autor">- Jeremy Gamboa</p>
            </div>
        </div>
    </section>

    <!-- CTA Final -->
    <section class="cta-final">
        <h2>Comienza a organizar tu vida hoy</h2>
        <p>Descubre la agenda perfecta para ti</p>
        <a href="#productos" class="btn">Explorar Productos</a>
    </section>

    <!-- Footer -->
    <footer>
        <div class="footer-content">
            <div class="footer-section">
                <h3>InkDays</h3>
                <p>Agendas personalizadas que inspiran</p>
            </div>
            <div class="footer-section">
                <h3>Enlaces Rápidos</h3>
                <ul>
                    <li><a href="#inicio">Inicio</a></li>
                    <li><a href="#productos">Productos</a></li>
                    <li><a href="#sobre-nosotros">Sobre Nosotros</a></li>
                </ul>
            </div>
            <div class="footer-section">
                <h3>Soporte</h3>
                <ul>
                    <li><a href="#">Preguntas Frecuentes</a></li>
                    <li><a href="#">Envíos</a></li>
                    <li><a href="#">Devoluciones</a></li>
                </ul>
            </div>
            <div class="footer-section">
                <h3>Contacto</h3>
                <ul>
                    <li>Email: info@inkdays.com</li>
                    <li>Telefono: +51 918 623 518</li>
                    <li>Horario: Lun-Vie 8AM-6PM</li>
                </ul>
            </div>
        </div>
        <div class="copyright">
            <p>&copy; 2025 InkDays.</p>
        </div>
    </footer>

    <script>
        // Smooth scroll para los enlaces
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });

        // Animación al hacer scroll
        const observerOptions = {
            threshold: 0.1
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.animation = 'fadeInUp 0.8s ease';
                }
            });
        }, observerOptions);

        document.querySelectorAll('.producto-card, .caracteristica, .testimonio').forEach(el => {
            observer.observe(el);
        });
    </script>
</body>
</html>
