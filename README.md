<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dra. Kiane Carvalho | Fisioterapia Pós-Operatória</title>
    <style>
        /* CSS: Estilos gerais da página */
        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Segoe UI', Roboto, Helvetica, Arial, sans-serif; }
        
        /* ROLAGEM SUAVE */
        html { scroll-behavior: smooth; scroll-padding-top: 60px; }
        body { line-height: 1.6; color: #333; background-color: #fdfdfd; }
        a { text-decoration: none; color: inherit; }

        /* SISTEMA DE IDIOMAS TRILINGUE (Esconde os idiomas inativos) */
        html[lang="pt-BR"] .lang-en, html[lang="pt-BR"] .lang-es { display: none !important; }
        html[lang="en"] .lang-pt, html[lang="en"] .lang-es { display: none !important; }
        html[lang="es"] .lang-pt, html[lang="es"] .lang-en { display: none !important; }

        /* Paleta de Cores Original + Dourado Premium */
        :root { 
            --primary: #00796b; 
            --secondary: #e0f2f1; 
            --accent: #004d40; 
            --gold: #d4af37; 
            --white: #ffffff;
        }

        /* 1. MENU DE NAVEGAÇÃO FIXO NO TOPO */
        .menu-topo {
            position: sticky; 
            top: 0;
            background-color: var(--primary);
            padding: 15px 20px;
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 30px;
            z-index: 1000; 
            box-shadow: 0 4px 10px rgba(0,0,0,0.1);
            flex-wrap: wrap;
        }
        .menu-topo a {
            color: var(--white);
            font-weight: bold;
            font-size: 1.1rem;
            transition: color 0.3s ease;
            text-transform: uppercase;
            letter-spacing: 1px;
        }
        .menu-topo a:hover { color: var(--secondary); }

        /* Menu Suspenso de Idiomas */
        .lang-switcher {
            margin-left: 20px;
            border-left: 1px solid rgba(255,255,255,0.3);
            padding-left: 20px;
        }
        .lang-switcher select {
            background-color: transparent;
            color: var(--white);
            border: 1px solid rgba(255,255,255,0.6);
            padding: 6px 12px;
            font-size: 0.95rem;
            font-weight: bold;
            border-radius: 6px;
            cursor: pointer;
            outline: none;
            transition: all 0.3s ease;
            appearance: none;
            -webkit-appearance: none;
            -moz-appearance: none;
            background-image: url("data:image/svg+xml;charset=US-ASCII,%3Csvg%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20width%3D%22292.4%22%20height%3D%22292.4%22%3E%3Cpath%20fill%3D%22%23FFFFFF%22%20d%3D%22M287%2069.4a17.6%2017.6%200%200%200-13-5.4H18.4c-5%200-9.3%201.8-12.9%205.4A17.6%2017.6%200%200%200%200%2082.2c0%205%201.8%209.3%205.4%2012.9l128%20127.9c3.6%203.6%207.8%205.4%2012.8%205.4s9.2-1.8%2012.8-5.4L287%2095c3.5-3.5%205.4-7.8%205.4-12.8%200-5-1.9-9.2-5.5-12.8z%22%2F%3E%3C%2Fsvg%3E");
            background-repeat: no-repeat;
            background-position: right 10px top 50%;
            background-size: 12px auto;
            padding-right: 30px;
        }
        .lang-switcher select:hover {
            border-color: var(--gold);
            color: var(--gold);
        }
        .lang-switcher select option {
            color: var(--accent);
            background-color: var(--white);
            font-weight: normal;
        }

        /* 2. APRESENTAÇÃO INICIAL */
        .apresentacao {
            text-align: center; 
            padding: 40px 20px 10px 20px;
            background-color: var(--white);
        }
        .apresentacao h1 { color: var(--accent); font-size: 2rem; margin-bottom: 5px; font-weight: 400; }
        .apresentacao p { color: var(--primary); font-size: 1.25rem; font-weight: 500; letter-spacing: 0.5px; }

        /* Estrutura Base das Secções */
        section { padding: 80px 20px; max-width: 1100px; margin: 0 auto; }
        
        #quem-sou { padding-top: 20px; }

        /* Título Premium */
        .titulo-premium {
            text-align: center; 
            margin-bottom: 35px; 
            color: var(--accent); 
            font-size: 2.2rem; 
            font-weight: 300; 
            text-transform: uppercase; 
            letter-spacing: 2px; 
            display: flex; 
            flex-direction: column; 
            align-items: center;
        }
        
        .titulo-premium::before {
            content: ""; 
            display: block; 
            width: 60px; 
            height: 3px; 
            background-color: var(--gold); 
            margin-bottom: 15px; 
            border-radius: 2px;
        }
        
        .titulo-premium strong {
            font-weight: 600; 
            display: block; 
            font-size: 1.8rem; 
            margin-top: 5px; 
            color: var(--primary); 
            letter-spacing: 1px;
        }
        
        h2 { text-align: center; margin-bottom: 50px; color: var(--accent); font-size: 2.2rem; }

        /* 3. Quem Sou */
        .quem-sou-container { display: flex; gap: 40px; align-items: center; flex-wrap: wrap; }
        .foto-perfil { flex: 1; min-width: 300px; display: flex; align-items: center; justify-content: center; }
        .foto-perfil img {
            width: 100%; max-height: 480px; object-fit: cover; 
            border-radius: 12px; box-shadow: 0 10px 30px rgba(0,0,0,0.15);
        }
        
        .texto-perfil { flex: 1.5; min-width: 300px; }
        .texto-perfil p { margin-bottom: 15px; font-size: 1.15rem; color: #444; text-align: justify; line-height: 1.7; }

        /* 4. Feedbacks - Textos */
        .bg-cinza { background-color: #f7f9f9; max-width: 100%; }
        .feedbacks-container { display: flex; gap: 30px; flex-wrap: wrap; justify-content: center; }
        .card-feedback { 
            background: var(--white); 
            padding: 30px; 
            border-radius: 12px; 
            box-shadow: 0 4px 15px rgba(0,0,0,0.05); 
            flex: 1; 
            min-width: 280px; 
            max-width: 330px; 
            border-top: 5px solid var(--primary); 
            display: flex;
            flex-direction: column;
        }
        .estrelas { color: var(--gold); margin-bottom: 15px; font-size: 1.2rem; }
        .card-feedback p { font-style: italic; margin-bottom: 20px; color: #666; flex-grow: 1; }
        .nome-paciente { font-weight: bold; color: var(--accent); display: block; }

        /* 4.1 Feedbacks - Vídeo Destaque */
        .video-destaque {
            display: flex;
            align-items: center;
            gap: 40px;
            margin-top: 60px;
            background: var(--white);
            padding: 40px;
            border-radius: 12px;
            box-shadow: 0 8px 25px rgba(0,0,0,0.08);
            border-left: 5px solid var(--gold);
        }
        .video-texto { flex: 1; }
        .video-texto p { font-size: 1.25rem; color: #444; margin-bottom: 25px; line-height: 1.6; }
        .btn-premium {
            background-color: var(--accent); color: var(--gold); padding: 14px 30px; border-radius: 8px;
            font-size: 1.1rem; font-weight: bold; display: inline-block; text-transform: uppercase;
            letter-spacing: 1px; border: 2px solid var(--gold); transition: all 0.3s ease;
        }
        .btn-premium:hover { background-color: var(--gold); color: var(--white); }
        .video-imagem {
            flex: 1; position: relative; border-radius: 10px; overflow: hidden;
            box-shadow: 0 5px 15px rgba(0,0,0,0.15); transition: transform 0.3s ease;
            display: flex; align-items: center; justify-content: center; background: #000;
        }
        .video-imagem:hover { transform: scale(1.02); }
        .video-imagem img { width: 100%; display: block; opacity: 0.85; }
        .icone-play {
            position: absolute; font-size: 2.5rem; color: var(--white); background: rgba(0, 0, 0, 0.6);
            border-radius: 50%; width: 70px; height: 70px; display: flex; align-items: center;
            justify-content: center; padding-left: 5px; border: 2px solid var(--white); pointer-events: none;
        }

        /* 5. Orçamento Premium */
        .orcamento-box { 
            background: linear-gradient(135deg, var(--accent), #002e26); 
            padding: 70px 30px; 
            border-radius: 16px; 
            text-align: center;
            box-shadow: 0 15px 35px rgba(0,77,64,0.2); 
            border-top: 5px solid var(--gold);
        }
        .orcamento-box h3 { 
            color: var(--gold); 
            font-size: 2.2rem; 
            margin-bottom: 25px; 
            font-weight: 300; 
            text-transform: uppercase; 
            letter-spacing: 1px;
        }
        .orcamento-box p { 
            margin-bottom: 20px; 
            font-size: 1.15rem; 
            color: #f1f1f1; 
            max-width: 800px; 
            margin-left: auto; 
            margin-right: auto;
            line-height: 1.8;
        }
        .orcamento-box .destaque-orcamento {
            font-weight: 500;
            color: var(--white);
            margin-bottom: 40px;
        }
        .btn-whatsapp { 
            background: linear-gradient(135deg, #25D366, #1ebd57); 
            color: var(--white); 
            padding: 18px 45px; 
            border-radius: 50px; 
            font-size: 1.25rem; 
            font-weight: bold; 
            display: inline-block; 
            box-shadow: 0 10px 20px rgba(37, 211, 102, 0.3); 
            transition: all 0.3s ease;
            text-transform: uppercase;
            letter-spacing: 1px;
        }
        .btn-whatsapp:hover { 
            transform: translateY(-3px); 
            box-shadow: 0 15px 25px rgba(37, 211, 102, 0.4); 
        }

        /* 6. Footer & Redes Sociais */
        footer { 
            text-align: center; 
            padding: 40px 20px 20px 20px; 
            background: #00362c; 
            color: #e0e0e0; 
            font-size: 0.9rem; 
        }
        
        .redes-sociais {
            display: flex;
            justify-content: center;
            gap: 25px;
            margin-bottom: 25px;
            flex-wrap: wrap;
        }
        
        .redes-sociais a {
            display: flex;
            align-items: center;
            gap: 8px;
            color: var(--white);
            font-size: 1rem;
            font-weight: 500;
            transition: all 0.3s ease;
        }
        
        .redes-sociais a:hover {
            color: var(--gold);
            transform: translateY(-3px);
        }
        
        .redes-sociais svg {
            width: 24px;
            height: 24px;
            fill: currentColor;
        }
        
        /* Ajustes para telemóveis */
        @media (max-width: 768px) {
            .menu-topo { gap: 15px; padding: 15px 10px; }
            .menu-topo a { font-size: 0.85rem; }
            .lang-switcher { margin-left: 0; padding-left: 0; border-left: none; width: 100%; text-align: center; margin-top: 5px; }
            .apresentacao { padding-top: 30px; }
            .apresentacao h1 { font-size: 1.6rem; }
            .apresentacao p { font-size: 1.1rem; }
            .titulo-premium { font-size: 1.6rem; margin-bottom: 25px; }
            .titulo-premium strong { font-size: 1.3rem; }
            .video-destaque { flex-direction: column; text-align: center; padding: 25px; }
            .orcamento-box { padding: 40px 20px; }
            .orcamento-box h3 { font-size: 1.8rem; }
            .btn-whatsapp { font-size: 1.1rem; padding: 15px 30px; }
            .redes-sociais { flex-direction: column; gap: 15px; align-items: center; }
        }
    </style>
</head>
<body>

    <!-- MENU DE NAVEGAÇÃO FIXO -->
    <nav class="menu-topo">
        <a href="#quem-sou">
            <span class="lang-pt">Sobre</span>
            <span class="lang-en">About</span>
            <span class="lang-es">Sobre mí</span>
        </a>
        <a href="#feedbacks">
            <span class="lang-pt">Depoimentos</span>
            <span class="lang-en">Testimonials</span>
            <span class="lang-es">Testimonios</span>
        </a>
        <a href="#orcamento">
            <span class="lang-pt">Orçamento</span>
            <span class="lang-en">Booking</span>
            <span class="lang-es">Reservas</span>
        </a>
        
        <!-- Menu Suspenso de Idiomas -->
        <div class="lang-switcher">
            <select onchange="mudarIdioma(this.value)">
                <option value="pt-BR">🇧🇷 PT</option>
                <option value="en">🇺🇸 EN</option>
                <option value="es">🇪🇸 ES</option>
            </select>
        </div>
    </nav>

    <!-- APRESENTAÇÃO -->
    <div class="apresentacao">
        <h1>
            <span class="lang-pt">Fisioterapeuta | CREFITO 345203-F 🩺</span>
            <span class="lang-en">Physiotherapist | CREFITO 345203-F 🩺</span>
            <span class="lang-es">Fisioterapeuta | CREFITO 345203-F 🩺</span>
        </h1>
        <p>
            <span class="lang-pt">Lipedema & Pós-Operatório de Cirurgias Plásticas.</span>
            <span class="lang-en"> Lipedema & Plastic Surgery Post-Operative Care.</span>
            <span class="lang-es"> Lipedema y Cuidados Postoperatorios de Cirugías Plásticas.</span>
        </p>
    </div>

    <!-- QUEM SOU -->
    <section id="quem-sou">
        <h2 class="titulo-premium">
            <span class="lang-pt">Conheça a Especialista</span>
            <span class="lang-en">Meet the Specialist</span>
            <span class="lang-es">Conoce a la Especialista</span>
            <strong>Dra. Kiane Carvalho Martins</strong>
        </h2>
        <div class="quem-sou-container">
            <div class="foto-perfil">
                <img src="https://github.com/kiane-martins/fisioterapia_pos_operatorio/blob/main/kiane_carvalho.jpeg?raw=true" alt="Dra. Kiane Carvalho Martins">
            </div>
            <div class="texto-perfil">
                <p class="lang-pt">Sou fisioterapeuta graduada pela <strong>Faculdade UNINOVE</strong> em 2021 e pós-graduada pela <strong>Faculdade Inspirar Borba Gato</strong> em 2022. Atuo exclusivamente com a reabilitação em Pós-Operatório desde 2022, unindo fundamentação científica, biossegurança e um cuidado altamente humanizado.</p>
                <p class="lang-en">I am a physiotherapist graduated from <strong>UNINOVE University</strong> in 2021, with a postgraduate degree from <strong>Inspirar Borba Gato College</strong> in 2022. I have been working exclusively with Post-Operative rehabilitation since 2022, combining scientific foundation, biosafety, and highly humanized care.</p>
                <p class="lang-es">Soy fisioterapeuta graduada por la <strong>Facultad UNINOVE</strong> en 2021 y posgraduada por la <strong>Facultad Inspirar Borba Gato</strong> en 2022. Trabajo exclusivamente con la rehabilitación Postoperatoria desde 2022, uniendo fundamentación científica, bioseguridad y un trato altamente humanizado.</p>
                
                <p class="lang-pt">Minha prática clínica é focada no acompanhamento pré e pós-operatório especializado de <strong>cirurgias plásticas corporais e faciais</strong>, além da avaliação e tratamento integrativo do <strong>Lipedema</strong>.</p>
                <p class="lang-en">My clinical practice focuses on specialized pre- and post-operative care for <strong>body and facial plastic surgeries</strong>, as well as the evaluation and integrative treatment of <strong>Lipedema</strong>.</p>
                <p class="lang-es">Mi práctica clínica se centra en el seguimiento pre y postoperatorio especializado de <strong>cirugías plásticas corporales y faciales</strong>, además de la evaluación y el tratamiento integrativo del <strong>Lipedema</strong>.</p>
                
                <p class="lang-pt">O objetivo do meu trabalho vai além do aspecto estético: visa otimizar a recuperação, manejar o edema e a dor, e prevenir ou tratar intercorrências como fibroses, seromas e aderências teciduais. Tudo é planejado de forma individualizada para garantir a saúde, a funcionalidade e o melhor resultado para cada paciente.</p>
                <p class="lang-en">The goal of my work goes beyond the aesthetic aspect: it aims to optimize recovery, manage edema and pain, and prevent or treat complications such as fibrosis, seromas, and tissue adhesions. Everything is planned individually to ensure health, functionality, and the best result for each patient.</p>
                <p class="lang-es">El objetivo de mi trabajo va más allá del aspecto estético: busca optimizar la recuperación, manejar el edema y el dolor, y prevenir o tratar complicaciones como fibrosis, seromas y adherencias tisulares. Todo está planeado de forma individualizada para garantizar la salud, la funcionalidad y el mejor resultado para cada paciente.</p>
            </div>
        </div>
    </section>

    <!-- FEEDBACKS -->
    <section class="bg-cinza" id="feedbacks">
        <div style="max-width: 1100px; margin: 0 auto;">
            <h2>
                <span class="lang-pt">O que as minhas pacientes dizem</span>
                <span class="lang-en">What my patients say</span>
                <span class="lang-es">Lo que dicen mis pacientes</span>
            </h2>
            <div class="feedbacks-container">
                
                <div class="card-feedback">
                    <div class="estrelas">★★★★★</div>
                    <p class="lang-pt">"A Kiane fez meu acompanhamento de pós operatório de lipoaspiração de pernas por conta do lipedema, mini lipo na barriga e mamoplastia. Gostei muito do atendimento. Ela é super atenciosa e entende bastante sobre o lipedema. Me ajudou bastante, inclusive com dicas para facilitar meu dia a dia de pós."</p>
                    <p class="lang-en">"Kiane accompanied my post-op recovery from leg liposuction due to lipedema, mini tummy tuck, and mammoplasty. I really liked the service. She is super attentive and understands a lot about lipedema. She helped me a lot, including with tips to make my daily post-op life easier."</p>
                    <p class="lang-es">"Kiane me acompañó en mi recuperación postoperatoria de liposucción de piernas por lipedema, mini abdominoplastia y mamoplastia. Me gustó mucho el trato. Es muy atenta y entiende mucho sobre el lipedema. Me ayudó bastante, incluso con consejos para facilitar mi día a día postoperatorio."</p>
                    <span class="nome-paciente">— Gabi Nunes</span>
                </div>

                <div class="card-feedback">
                    <div class="estrelas">★★★★★</div>
                    <p class="lang-pt">"Fiz minha primeira cirurgia de lipedema em Março/24. Kiane cuidou do meu pos operatório durante 10 dias já iniciando o atendimento imediatamente após a cirurgia. Excelente profissional, calma, pontual e extremamente acessível até meses depois para alguma orientação. Tenho uma segunda etapa agendada para novembro deste ano e com certeza ela estará me acompanhando novamente. Super recomendo!"</p>
                    <p class="lang-en">"I had my first lipedema surgery in March/24. Kiane took care of my post-op for 10 days, starting care immediately after the surgery. Excellent professional, calm, punctual, and extremely accessible even months later for any guidance. I have a second stage scheduled for November this year and she will definitely be accompanying me again. Highly recommend!"</p>
                    <p class="lang-es">"Tuve mi primera cirugía de lipedema en Marzo/24. Kiane cuidó de mi postoperatorio durante 10 días, comenzando la atención inmediatamente después de la cirugía. Excelente profesional, tranquila, puntual y extremadamente accesible incluso meses después para cualquier orientación. Tengo una segunda etapa programada para noviembre de este año y definitivamente me acompañará nuevamente. ¡Súper recomendable!"</p>
                    <span class="nome-paciente">— Mariana Bianchi</span>
                </div>

                <div class="card-feedback">
                    <div class="estrelas">★★★★★</div>
                    <p class="lang-pt">"Minha experiência com a Kiane foi a mais incrível possível!! O atendimento dela vai além do profissional, sempre preocupada com o bem estar tanto físico qnto psicológico das pacientes!! Jamais esquecerei tudo o que ela fez por mim!! Quem passa por suas mãos não esquece jamais!! Ela é excelente profissional e uma pessoa maravilhosa!!!"</p>
                    <p class="lang-en">"My experience with Kiane was the most incredible possible!! Her care goes beyond professional, always concerned with both the physical and psychological well-being of the patients!! I will never forget everything she did for me!! Whoever passes through her hands never forgets!! She is an excellent professional and a wonderful person!!!"</p>
                    <p class="lang-es">"¡Mi experiencia con Kiane fue la más increíble posible! ¡Su atención va más allá de lo profesional, siempre preocupada por el bienestar tanto físico como psicológico de las pacientes! ¡Nunca olvidaré todo lo que hizo por mí! ¡Quien pasa por sus manos no lo olvida jamás! ¡Es una excelente profesional y una persona maravillosa!"</p>
                    <span class="nome-paciente">— Janaina Ravagnani Pereira</span>
                </div>

            </div>

            <!-- DEPOIMENTO EM VÍDEO -->
            <div class="video-destaque">
                <div class="video-texto">
                    <p class="lang-pt">Confira no YouTube a experiência real da paciente <strong>Camilli Viaja</strong> sobre sua cirurgia e os primeiros dias de recuperação no pós-operatório:</p>
                    <p class="lang-en">Check out on YouTube the real experience of patient <strong>Camilli Viaja</strong> about her surgery and the first days of post-operative recovery:</p>
                    <p class="lang-es">Mira en YouTube la experiencia real de la paciente <strong>Camilli Viaja</strong> sobre su cirugía y los primeros días de recuperación en el postoperatorio:</p>
                    
                    <a href="https://youtu.be/EHhS_kno02A?is=RqoqD708wJxP-MOv" target="_blank" class="btn-premium lang-pt">Assista o vídeo completo</a>
                    <a href="https://youtu.be/EHhS_kno02A?is=RqoqD708wJxP-MOv" target="_blank" class="btn-premium lang-en">Watch the full video</a>
                    <a href="https://youtu.be/EHhS_kno02A?is=RqoqD708wJxP-MOv" target="_blank" class="btn-premium lang-es">Mira el video completo</a>
                </div>
                <a href="https://youtu.be/EHhS_kno02A?is=RqoqD708wJxP-MOv" target="_blank" class="video-imagem">
                    <img src="https://github.com/kiane-martins/fisioterapia_pos_operatorio/blob/main/video_feedback.jpeg?raw=true" alt="Video">
                    <div class="icone-play">▶</div>
                </a>
            </div>

        </div>
    </section>

    <!-- ORÇAMENTO -->
    <section id="orcamento">
        <div class="orcamento-box">
            <h3>
                <span class="lang-pt">Planejamento Personalizado</span>
                <span class="lang-en">Personalized Planning</span>
                <span class="lang-es">Planificación Personalizada</span>
            </h3>
            
            <p class="lang-pt">Cada corpo é único e cada processo cirúrgico exige um olhar carinhoso e exclusivo. Por isso, o orçamento do seu tratamento é totalmente personalizado e individualizado, considerando o deslocamento até a sua residência ou hospedagem e as regiões do corpo que irão passar pelo processo cirúrgico (pernas, braços, mama, abdômen e etc).</p>
            <p class="lang-en">Every body is unique and each surgical process requires a caring and exclusive look. Therefore, your treatment plan is completely personalized and individualized, considering the travel to your residence or accommodation and the body regions that will undergo the surgical process (legs, arms, breasts, abdomen, etc.).</p>
            <p class="lang-es">Cada cuerpo es único y cada proceso quirúrgico requiere una mirada cuidadosa y exclusiva. Por eso, el presupuesto de su tratamiento es totalmente personalizado e individualizado, considerando el desplazamiento hasta su residencia o alojamiento y las regiones del cuerpo que pasarán por el proceso quirúrgico (piernas, brazos, mamas, abdomen, etc.).</p>
            
            <p class="destaque-orcamento lang-pt">Para que eu possa planejar seu atendimento com todo o carinho que você merece, entre em contato comigo informando a cirurgia pretendida e a sua localização.</p>
            <p class="destaque-orcamento lang-en">So that I can plan your care with all the affection you deserve, please contact me informing the intended surgery and your location.</p>
            <p class="destaque-orcamento lang-es">Para que pueda planificar su atención con todo el cariño que merece, póngase en contacto conmigo informando la cirugía prevista y su ubicación.</p>
            
            <!-- Botão WhatsApp em Português -->
            <a href="https://wa.me/5511914225051?text=Ol%C3%A1%20Dra.%20Kiane%2C%20gostaria%20de%20fazer%20um%20or%C3%A7amento%20para%20o%20meu%20p%C3%B3s-operat%C3%B3rio." target="_blank" class="btn-whatsapp lang-pt">
                Falar no WhatsApp
            </a>
            
            <!-- Botão WhatsApp em Inglês -->
            <a href="https://wa.me/5511914225051?text=Hello%20Dr.%20Kiane%2C%20I%20would%20like%20to%20request%20a%20quote%20for%20my%20post-operative%20care." target="_blank" class="btn-whatsapp lang-en">
                Contact via WhatsApp
            </a>

            <!-- Botão WhatsApp em Espanhol -->
            <a href="https://wa.me/5511914225051?text=Hola%20Dra.%20Kiane%2C%20me%20gustar%C3%ADa%20solicitar%20un%20presupuesto%20para%20mi%20postoperatorio." target="_blank" class="btn-whatsapp lang-es">
                Contactar por WhatsApp
            </a>
        </div>
    </section>

    <!-- FOOTER COM REDES SOCIAIS -->
    <footer>
        <div class="redes-sociais">
            <a href="https://www.instagram.com/kiane_fisioterapeuta?cplk=MTI3czljcW04bXFhZA%3D%3D&utm_source=qr" target="_blank">
                <svg viewBox="0 0 24 24"><path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"/></svg>
                Instagram
            </a>
            <a href="https://maps.app.goo.gl/kky7TPzmL4ntQTvj8?g_st=ic" target="_blank">
                <svg viewBox="0 0 24 24"><path d="M12.545,10.239v3.821h5.445c-0.712,2.315-2.647,3.972-5.445,3.972c-3.332,0-6.033-2.701-6.033-6.032s2.701-6.032,6.033-6.032c1.498,0,2.866,0.549,3.921,1.453l2.814-2.814C17.503,2.988,15.139,2,12.545,2C7.021,2,2.543,6.477,2.543,12s4.478,10,10.002,10c8.396,0,10.249-7.85,9.426-11.748L12.545,10.239z"/></svg>
                <span class="lang-pt">Avaliações</span>
                <span class="lang-en">Reviews</span>
                <span class="lang-es">Reseñas</span>
            </a>
            
            <a href="https://wa.me/5511914225051?text=Ol%C3%A1%20Dra.%20Kiane%2C%20gostaria%20de%20fazer%20um%20or%C3%A7amento%20para%20o%20meu%20p%C3%B3s-operat%C3%B3rio." target="_blank" class="lang-pt">
                <svg viewBox="0 0 24 24"><path d="M.057 24l1.687-6.163c-1.041-1.804-1.588-3.849-1.587-5.946.003-6.556 5.338-11.891 11.893-11.891 3.181.001 6.167 1.24 8.413 3.488 2.245 2.248 3.481 5.236 3.48 8.414-.003 6.557-5.338 11.892-11.893 11.892-1.99-.001-3.951-.5-5.688-1.448l-6.305 1.654zm6.597-3.807c1.676.995 3.276 1.591 5.392 1.592 5.448 0 9.886-4.434 9.889-9.885.002-5.462-4.415-9.89-9.881-9.892-5.452 0-9.887 4.434-9.889 9.884-.001 2.225.651 3.891 1.746 5.634l-.999 3.648 3.742-.981zm11.387-5.464c-.074-.124-.272-.198-.57-.347-.297-.149-1.758-.868-2.031-.967-.272-.099-.47-.149-.669.149-.198.297-.768.967-.941 1.165-.173.198-.347.223-.644.074-.297-.149-1.255-.462-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.297-.347.446-.521.151-.172.2-.296.3-.495.099-.198.05-.372-.025-.521-.075-.148-.669-1.611-.916-2.206-.242-.579-.487-.501-.669-.51l-.57-.01c-.198 0-.52.074-.792.347-.272.297-1.04 1.016-1.04 2.479 0 1.463 1.065 2.876 1.213 3.074.149.198 2.095 3.2 5.076 4.487.709.306 1.263.489 1.694.626.712.226 1.36.194 1.872.118.571-.085 1.758-.719 2.006-1.413.248-.695.248-1.29.173-1.414z"/></svg>
                WhatsApp
            </a>
            
            <a href="https://wa.me/5511914225051?text=Hello%20Dr.%20Kiane%2C%20I%20would%20like%20to%20request%20a%20quote%20for%20my%20post-operative%20care." target="_blank" class="lang-en">
                <svg viewBox="0 0 24 24"><path d="M.057 24l1.687-6.163c-1.041-1.804-1.588-3.849-1.587-5.946.003-6.556 5.338-11.891 11.893-11.891 3.181.001 6.167 1.24 8.413 3.488 2.245 2.248 3.481 5.236 3.48 8.414-.003 6.557-5.338 11.892-11.893 11.892-1.99-.001-3.951-.5-5.688-1.448l-6.305 1.654zm6.597-3.807c1.676.995 3.276 1.591 5.392 1.592 5.448 0 9.886-4.434 9.889-9.885.002-5.462-4.415-9.89-9.881-9.892-5.452 0-9.887 4.434-9.889 9.884-.001 2.225.651 3.891 1.746 5.634l-.999 3.648 3.742-.981zm11.387-5.464c-.074-.124-.272-.198-.57-.347-.297-.149-1.758-.868-2.031-.967-.272-.099-.47-.149-.669.149-.198.297-.768.967-.941 1.165-.173.198-.347.223-.644.074-.297-.149-1.255-.462-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.297-.347.446-.521.151-.172.2-.296.3-.495.099-.198.05-.372-.025-.521-.075-.148-.669-1.611-.916-2.206-.242-.579-.487-.501-.669-.51l-.57-.01c-.198 0-.52.074-.792.347-.272.297-1.04 1.016-1.04 2.479 0 1.463 1.065 2.876 1.213 3.074.149.198 2.095 3.2 5.076 4.487.709.306 1.263.489 1.694.626.712.226 1.36.194 1.872.118.571-.085 1.758-.719 2.006-1.413.248-.695.248-1.29.173-1.414z"/></svg>
               WhatsApp
            </a>

            <a href="https://wa.me/5511914225051?text=Hola%20Dra.%20Kiane%2C%20me%20gustar%C3%ADa%20solicitar%20un%20presupuesto%20para%20mi%20postoperatorio." target="_blank" class="lang-es">
                <svg viewBox="0 0 24 24"><path d="M.057 24l1.687-6.163c-1.041-1.804-1.588-3.849-1.587-5.946.003-6.556 5.338-11.891 11.893-11.891 3.181.001 6.167 1.24 8.413 3.488 2.245 2.248 3.481 5.236 3.48 8.414-.003 6.557-5.338 11.892-11.893 11.892-1.99-.001-3.951-.5-5.688-1.448l-6.305 1.654zm6.597-3.807c1.676.995 3.276 1.591 5.392 1.592 5.448 0 9.886-4.434 9.889-9.885.002-5.462-4.415-9.89-9.881-9.892-5.452 0-9.887 4.434-9.889 9.884-.001 2.225.651 3.891 1.746 5.634l-.999 3.648 3.742-.981zm11.387-5.464c-.074-.124-.272-.198-.57-.347-.297-.149-1.758-.868-2.031-.967-.272-.099-.47-.149-.669.149-.198.297-.768.967-.941 1.165-.173.198-.347.223-.644.074-.297-.149-1.255-.462-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.297-.347.446-.521.151-.172.2-.296.3-.495.099-.198.05-.372-.025-.521-.075-.148-.669-1.611-.916-2.206-.242-.579-.487-.501-.669-.51l-.57-.01c-.198 0-.52.074-.792.347-.272.297-1.04 1.016-1.04 2.479 0 1.463 1.065 2.876 1.213 3.074.149.198 2.095 3.2 5.076 4.487.709.306 1.263.489 1.694.626.712.226 1.36.194 1.872.118.571-.085 1.758-.719 2.006-1.413.248-.695.248-1.29.173-1.414z"/></svg>
                WhatsApp
            </a>
        </div>
        <p>
            <span class="lang-pt">&copy; 2026 Dra. Kiane Carvalho Martins. Todos os direitos reservados.</span>
            <span class="lang-en">&copy; 2026 Dr. Kiane Carvalho Martins. All rights reserved.</span>
            <span class="lang-es">&copy; 2026 Dra. Kiane Carvalho Martins. Todos los derechos reservados.</span>
        </p>
    </footer>

    <!-- SCRIPT DE TROCA DE IDIOMA -->
    <script>
        function mudarIdioma(idioma) {
            document.documentElement.lang = idioma;
        }
    </script>

</body>
</html>
