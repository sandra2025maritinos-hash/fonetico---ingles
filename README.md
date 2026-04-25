<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Gabaritando Humanas - VemAprenderComigo</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        .custom-scrollbar::-webkit-scrollbar { width: 8px; }
        .custom-scrollbar::-webkit-scrollbar-track { background: #faf5ff; }
        .custom-scrollbar::-webkit-scrollbar-thumb { background: #c084fc; border-radius: 4px; }
        .custom-scrollbar::-webkit-scrollbar-thumb:hover { background: #a855f7; }
        
        .fade-in { animation: fadeIn 0.5s ease-out forwards; }
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        .quiz-option { transition: all 0.3s ease; }
        .quiz-option:hover:not(:disabled) { transform: translateX(5px); }
        
        /* NOVO TEMA DE CORES: Roxo Suave Pastel com alta legibilidade */
        .gradient-bg {
            background: linear-gradient(135deg, #e9d5ff 0%, #d8b4fe 100%);
        }
        .gradient-card {
            background: linear-gradient(135deg, #faf5ff 0%, #f3e8ff 100%);
        }
    </style>
</head>
<body class="bg-slate-50 text-slate-800 font-sans h-screen overflow-hidden flex flex-col md:flex-row">

    <!-- ================= TELA DE LOGIN INSTITUCIONAL ================= -->
    <div id="login-screen" class="fixed inset-0 bg-slate-900 z-50 flex items-center justify-center p-4 sm:p-8 transition-opacity duration-500 overflow-y-auto">
        <div class="bg-white rounded-3xl shadow-2xl max-w-6xl w-full flex flex-col md:flex-row overflow-hidden my-auto max-h-full">
            
            <!-- Painel Esquerdo: Filosofia da Plataforma (Agora claro e legível) -->
            <div class="w-full md:w-3/5 gradient-bg p-8 md:p-12 text-slate-800 flex flex-col">
                <h1 class="text-3xl md:text-4xl font-black mb-6 border-b border-purple-400/50 pb-4 flex items-center text-purple-950">
                    <i class="fa-solid fa-graduation-cap mr-3 text-purple-700"></i> VemAprenderComigo
                </h1>
                
                <div class="space-y-6 overflow-y-auto custom-scrollbar pr-4 pb-4">
                    <div>
                        <h3 class="text-xl font-bold text-amber-700 mb-2 flex items-center"><i class="fa-solid fa-rocket mr-2"></i> MISSÃO</h3>
                        <p class="text-sm md:text-base leading-relaxed text-slate-800 font-medium">Promover uma forma de aprender que seja fácil, continua e gere crescimento humano e técnico. Que traga habilidades para um futuro consciente e mais preparado para uma sociedade cada vez mais plural e diversa. Que gera uma transformação, uma virada de chave social.</p>
                    </div>
                    
                    <div>
                        <h3 class="text-xl font-bold text-amber-700 mb-2 flex items-center"><i class="fa-solid fa-heart mr-2"></i> VALORES E FORMAÇÃO HUMANA</h3>
                        <p class="text-sm md:text-base leading-relaxed text-slate-800 font-medium">A plataforma VemAprenderComigo foi criada para criar uma forma de ensino intuitiva e com uma proximidade entre a idealizadora "Sandra (eu)" e o estudante. Onde ele aprende me contando sobre a aula, sobre a experiência e a gente sempre adapta novas formas de aumentar a curva de aprendizado. Aqui, a intenção é apresentar valores, comunidades, diversidade, práticas técnicas e auxiliar nas questões escolares.</p>
                    </div>
                    
                    <div>
                        <h3 class="text-xl font-bold text-amber-700 mb-2 flex items-center"><i class="fa-solid fa-brain mr-2"></i> FILOSOFIA</h3>
                        <p class="text-sm md:text-base leading-relaxed text-slate-800 font-medium">Uma forma de ensino diferente para pessoas diferentes. Entender que cada cérebro aprende de um jeito único. É ascender em um estudante disperso o interesse de aprender mais, pois gostou da 'cobrança', do Ranking, das medalhas, do diário e o feedback presente todos os dias. Acredito que a <b class="text-purple-900">PROXIMIDADE</b> faz toda a diferença.</p>
                    </div>
                    
                    <div>
                        <h3 class="text-xl font-bold text-amber-700 mb-2 flex items-center"><i class="fa-solid fa-eye mr-2"></i> VISÃO</h3>
                        <p class="text-sm md:text-base leading-relaxed text-slate-800 font-medium">Tornar a plataforma em um HUB de conhecimento em João Pessoa, onde o aluno possa vir estudar, onde possamos nos reunir e debater sobre Bullying, Prevenção a Drogas, o que aprendeu no curso de Digitação, como é legal o Inglês Fonético. Planos para um futuro breve!</p>
                    </div>
                </div>
            </div>

            <!-- Painel Direito: Acesso -->
            <div class="w-full md:w-2/5 p-8 md:p-10 flex flex-col justify-center items-center bg-white relative">
                <div class="bg-purple-100 w-24 h-24 rounded-full flex items-center justify-center mb-6 shadow-inner border border-purple-200">
                    <i class="fa-solid fa-masks-theater text-4xl text-purple-600"></i>
                </div>
                <h2 class="text-3xl font-black text-gray-800 mb-2 text-center">Área Restrita</h2>
                <p class="text-gray-500 mb-8 font-medium text-center">Insira o seu código para acessar o módulo de Humanas.</p>
                
                <input type="text" id="access-code-input" placeholder="CÓDIGO DE ACESSO" class="w-full text-center text-xl font-bold uppercase tracking-widest p-4 rounded-xl border-2 border-gray-200 focus:border-purple-500 focus:ring-4 focus:ring-purple-100 outline-none transition-all mb-4 text-slate-800" onkeypress="if(event.key === 'Enter') validateCode()">
                
                <p id="login-error" class="text-red-500 font-bold text-sm mb-6 hidden animate-bounce"><i class="fa-solid fa-triangle-exclamation mr-1"></i> Código inválido. Tente novamente.</p>
                
                <button onclick="validateCode()" class="w-full bg-purple-600 hover:bg-purple-700 text-white font-bold text-lg py-4 rounded-xl transition-colors shadow-md">
                    Entrar na Plataforma <i class="fa-solid fa-arrow-right ml-2"></i>
                </button>
            </div>
            
        </div>
    </div>

    <!-- Mobile Header -->
    <header class="md:hidden gradient-bg text-purple-950 p-4 flex justify-between items-center shadow-md z-20 border-b border-purple-300">
        <h1 class="text-xl font-bold"><i class="fa-solid fa-book-journal-whills mr-2 text-purple-700"></i> Humanas ENEM</h1>
        <button id="mobileMenuBtn" class="text-purple-900 text-2xl focus:outline-none">
            <i class="fa-solid fa-bars"></i>
        </button>
    </header>

    <!-- Sidebar / Navigation -->
    <aside id="sidebar" class="bg-white w-full md:w-80 h-full shadow-2xl flex-shrink-0 absolute md:relative z-10 transform -translate-x-full md:translate-x-0 transition-transform duration-300 ease-in-out overflow-y-auto custom-scrollbar flex flex-col border-r border-slate-200">
        <div class="p-6 gradient-bg text-slate-800 hidden md:block sticky top-0 z-10 border-b border-purple-300">
            <h1 class="text-2xl font-bold tracking-tight text-purple-950"><i class="fa-solid fa-lightbulb mr-2 text-amber-600"></i> Gabaritando Humanas</h1>
            <p class="text-purple-800 text-sm mt-2 font-bold opacity-90">Filosofia, Sociologia, Literatura e Artes descomplicadas.</p>
        </div>
        
        <nav id="navMenu" class="p-4 flex-grow">
            <!-- Menu items will be injected here via JS -->
        </nav>
    </aside>

    <!-- Main Content Area -->
    <main class="flex-grow h-full overflow-y-auto custom-scrollbar bg-slate-50 relative w-full">
        <!-- Header da página -->
        <div class="bg-white border-b border-gray-200 h-16 flex items-center justify-between px-6 shrink-0 shadow-sm sticky top-0 z-10">
            <div class="flex items-center gap-2 text-sm font-medium text-gray-500">
                <i class="fa-solid fa-book-open"></i> VemAprenderComigo
            </div>
            <div class="flex items-center gap-3">
                <button onclick="logout()" class="text-xs font-bold text-gray-400 hover:text-red-500 transition-colors mr-2 uppercase tracking-wider"><i class="fa-solid fa-right-from-bracket mr-1"></i>Sair</button>
                <div class="w-8 h-8 rounded-full bg-purple-100 text-purple-700 flex items-center justify-center font-bold text-xs border border-purple-200">AL</div>
            </div>
        </div>

        <div id="mobileOverlay" class="fixed inset-0 bg-slate-900 bg-opacity-50 z-0 hidden md:hidden"></div>
        
        <div class="max-w-4xl mx-auto p-4 md:p-8 relative z-0" id="mainContent">
            <!-- Placeholder -->
            <div class="flex flex-col items-center justify-center h-full text-center mt-24 text-slate-400">
                <i class="fa-solid fa-masks-theater text-8xl mb-6 text-purple-300"></i>
                <h2 class="text-4xl font-bold text-slate-700 mb-4">A Matrix do Conhecimento</h2>
                <p class="text-lg max-w-lg">Esqueça a decoreba. Aqui nós vamos traduzir os maiores pensadores e artistas da história para a realidade do seu dia a dia.</p>
                <p class="mt-4 text-purple-600 font-bold">Selecione uma aula no menu lateral para expandir sua mente!</p>
            </div>
        </div>
    </main>

    <script>
        // ==========================================
        // SISTEMA DE LOGIN (20 DIAS)
        // ==========================================
        const validCodes = [
            "HUMANAS01", "HUMANAS02", "HUMANAS03", "HUMANAS04", "HUMANAS05",
            "ENEM2026_01", "ENEM2026_02", "ENEM2026_03", "ENEM2026_04", "ENEM2026_05",
            "SOCIOLOGIA1", "SOCIOLOGIA2", "FILOSOFIA1", "FILOSOFIA2", "ARTES1",
            "VEMAPRENDER1", "VEMAPRENDER2", "VEMAPRENDER3", "VEMAPRENDER4", "VEMAPRENDER5"
        ];

        function checkAuth() {
            const isAuth = localStorage.getItem('humanasAuth');
            const expiryStr = localStorage.getItem('humanasExpiry');
            const loginScreen = document.getElementById('login-screen');
            const errorMsg = document.getElementById('login-error');

            if (isAuth === 'true') {
                const now = new Date().getTime();
                const expiry = parseInt(expiryStr || '0');

                if (now > expiry) {
                    localStorage.removeItem('humanasAuth');
                    localStorage.removeItem('humanasExpiry');
                    loginScreen.style.display = 'flex';
                    errorMsg.innerHTML = '<i class="fa-solid fa-clock-rotate-left mr-1"></i> O seu tempo de acesso (20 dias) terminou. Insira um novo código.';
                    errorMsg.classList.remove('hidden', 'text-red-500');
                    errorMsg.classList.add('text-amber-600', 'block');
                } else {
                    loginScreen.style.display = 'none'; 
                }
            } else {
                loginScreen.style.display = 'flex'; 
            }
        }

        function validateCode() {
            const inputEl = document.getElementById('access-code-input');
            const code = inputEl.value.trim().toUpperCase(); 
            const errorMsg = document.getElementById('login-error');

            if (validCodes.includes(code)) {
                const now = new Date().getTime();
                const vinteDiasEmMs = 20 * 24 * 60 * 60 * 1000;
                const dataExpiracao = now + vinteDiasEmMs;

                localStorage.setItem('humanasAuth', 'true');
                localStorage.setItem('humanasExpiry', dataExpiracao.toString());
                
                const loginScreen = document.getElementById('login-screen');
                loginScreen.style.opacity = '0';
                setTimeout(() => {
                    loginScreen.style.display = 'none';
                }, 500); 
            } else {
                errorMsg.innerHTML = '<i class="fa-solid fa-triangle-exclamation mr-1"></i> Código inválido. Tente novamente.';
                errorMsg.classList.remove('text-amber-600', 'hidden');
                errorMsg.classList.add('text-red-500', 'block');
                inputEl.classList.add('border-red-400', 'bg-red-50');
                setTimeout(() => {
                    inputEl.classList.remove('border-red-400', 'bg-red-50');
                }, 1000);
            }
        }

        function logout() {
            if(confirm("Deseja realmente sair e bloquear a plataforma? Você precisará do código de acesso novamente.")) {
                localStorage.removeItem('humanasAuth');
                localStorage.removeItem('humanasExpiry');
                location.reload(); 
            }
        }

        // --- DADOS DO CURSO (O "Material Denso e de Fácil Associação") ---
        const curriculum = [
            {
                id: 'mod_filosofia',
                title: 'Filosofia: Descomplicando a Mente',
                icon: 'fa-brain',
                lessons: [
                    {
                        id: 'platao_caverna',
                        title: '1. O Mito da Caverna (Platão)',
                        theory: `
                            <h3 class="text-2xl font-bold text-purple-900 mb-4">A Teoria de Platão</h3>
                            <p class="mb-4 text-lg text-slate-800 font-medium">Platão, um dos maiores filósofos gregos da antiguidade, criou uma alegoria para explicar como o ser humano adquire conhecimento verdadeiro. Ele imaginou prisioneiros acorrentados no fundo de uma caverna desde que nasceram, olhando apenas para uma parede.</p>
                            <p class="mb-4 text-lg text-slate-800 font-medium">Atrás deles, há uma fogueira e pessoas passando com objetos. A luz da fogueira projeta as <b>sombras</b> desses objetos na parede. Como os prisioneiros nunca viram o mundo real, eles acreditam que as sombras são a realidade absoluta (Mundo Sensível).</p>
                            <p class="mb-4 text-lg text-slate-800 font-medium">Um prisioneiro consegue se soltar, sai da caverna, sente a luz do sol (que dói os olhos no início) e descobre o mundo real (Mundo das Ideias). Ao voltar para avisar os outros, eles o chamam de louco e o rejeitam.</p>
                        `,
                        analogy: `
                            <h4 class="font-bold text-amber-800 text-lg mb-2"><i class="fa-solid fa-mobile-screen-button mr-2"></i> Traduzindo para o Mundo Real: A Bolha do Algoritmo</h4>
                            <p class="text-amber-950 font-medium leading-relaxed">Imagine que a "Caverna" é o seu feed do TikTok ou Instagram. O algoritmo só te mostra vídeos de pessoas que pensam igual a você (as Sombras). Você começa a acreditar que o mundo inteiro pensa assim e que aquela é a realidade absoluta.</p>
                            <p class="text-amber-950 font-medium leading-relaxed mt-2">Sair da caverna é desligar o celular, ler um livro diferente, conversar com pessoas que discordam de você ou pesquisar os fatos em sites confiáveis. O "Mundo das Ideias" é a realidade lá fora. E, assim como na história, quando você tenta avisar seus amigos que a fofoca do Twitter era mentira, eles brigam com você e preferem continuar acreditando na "sombra" (Fake News).</p>
                        `,
                        quiz: [
                            {
                                question: "No Mito da Caverna de Platão, o que representam as 'sombras' projetadas na parede?",
                                options: [
                                    "A verdade absoluta revelada pelos deuses.",
                                    "A ignorância, as ilusões e o conhecimento superficial baseado apenas nos sentidos.",
                                    "A ciência moderna e a tecnologia da época.",
                                    "A luz do sol que guia os filósofos."
                                ],
                                answer: 1,
                                explanation: "As sombras representam o 'Mundo Sensível', ou seja, o conhecimento falso baseado em aparências, fofocas e crenças sem questionamento crítico. Platão defendia que a verdade só é alcançada pelo uso da razão (o mundo fora da caverna)."
                            }
                        ]
                    },
                    {
                        id: 'sartre_existencialismo',
                        title: '2. Sartre e o Existencialismo',
                        theory: `
                            <h3 class="text-2xl font-bold text-purple-900 mb-4">A Angústia da Liberdade</h3>
                            <p class="mb-4 text-lg text-slate-800 font-medium">Jean-Paul Sartre foi um filósofo francês do século XX famoso pela frase: <b>"A existência precede a essência"</b>. Mas o que diabos isso significa?</p>
                            <p class="mb-4 text-lg text-slate-800 font-medium">Pense em uma tesoura. Antes de existir, alguém pensou nela, desenhou o projeto e definiu para que ela serviria (cortar). Ou seja, a sua essência (cortar) veio antes da sua existência física.</p>
                            <p class="mb-4 text-lg text-slate-800 font-medium">Sartre dizia que com o ser humano é o contrário! Nós primeiro <i>existimos</i> (nascemos, somos jogados no mundo), e só depois, através das nossas escolhas e atitudes, nós criamos a nossa <i>essência</i> (quem somos). Por isso, somos "condenados a ser livres" e totalmente responsáveis pelo nosso destino.</p>
                        `,
                        analogy: `
                            <h4 class="font-bold text-amber-800 text-lg mb-2"><i class="fa-solid fa-face-dizzy mr-2"></i> Traduzindo para o Mundo Real: A Crise do Terceirão</h4>
                            <p class="text-amber-950 font-medium leading-relaxed">Você está no 3º ano do Ensino Médio e precisa escolher um curso de faculdade. Você sente uma pressão no peito, uma ansiedade terrível. Sabe o que é isso? Sartre chamava isso de <b>"A Angústia"</b>.</p>
                            <p class="text-amber-950 font-medium leading-relaxed mt-2">A angústia bate porque você percebe que não existe um "destino escrito nas estrelas" para você. Não há um manual. Se você escolher Medicina, Engenharia ou virar Youtuber, a responsabilidade de dar certo ou errado é 100% sua. Sartre te diria: 'Para de colocar a culpa no seu signo, nos seus pais ou na escola. Você é a soma das suas escolhas. Escolha logo e faça a sua vida acontecer!'</p>
                        `,
                        quiz: [
                            {
                                question: "O que Sartre queria dizer com a frase 'o homem está condenado a ser livre'?",
                                options: [
                                    "Que a liberdade é ruim e deveríamos ser controlados pelo governo.",
                                    "Que o ser humano já nasce com um destino totalmente definido, mas tem a ilusão de liberdade.",
                                    "Que a liberdade é algo dado por lei em todas as sociedades.",
                                    "Que, como não temos um destino pré-definido, não podemos fugir da obrigação e do peso de fazer nossas próprias escolhas."
                                ],
                                answer: 3,
                                explanation: "Para o existencialismo, a liberdade não é apenas 'fazer o que quiser', mas sim o peso insuportável de ser o único responsável pela própria vida. Você não pode não escolher, pois omitir-se já é uma escolha."
                            }
                        ]
                    }
                ]
            },
            {
                id: 'mod_sociologia',
                title: 'Sociologia: A Matrix da Sociedade',
                icon: 'fa-people-group',
                lessons: [
                    {
                        id: 'marx_capitalismo',
                        title: '1. Karl Marx (Luta de Classes)',
                        theory: `
                            <h3 class="text-2xl font-bold text-purple-900 mb-4">O Motor da História</h3>
                            <p class="mb-4 text-lg text-slate-800 font-medium">Karl Marx olhou para a sociedade capitalista e viu duas peças principais jogando um xadrez eterno: a <b>Burguesia</b> (os donos das fábricas e dos meios de produção) e o <b>Proletariado</b> (os trabalhadores que só têm a sua própria força para vender em troca de salário).</p>
                            <p class="mb-4 text-lg text-slate-800 font-medium">Ele criou o conceito de <b>Mais-Valia</b>. Basicamente: um trabalhador produz 100 reais de riqueza em 2 horas de trabalho. Mas ele trabalha 8 horas por dia e só recebe 50 reais pelo dia todo. A enorme riqueza que ele produziu (e não recebeu) fica para o dono da fábrica. Para Marx, a história da humanidade é a história da luta (conflito) entre essas duas classes.</p>
                        `,
                        analogy: `
                            <h4 class="font-bold text-amber-800 text-lg mb-2"><i class="fa-solid fa-motorcycle mr-2"></i> Traduzindo para o Mundo Real: O Entregador de iFood</h4>
                            <p class="text-amber-950 font-medium leading-relaxed">Imagine um grande aplicativo de entregas de comida. A "Burguesia" atual não é mais dona de fábricas cheias de fumaça, mas é dona da tecnologia, do aplicativo e dos servidores (os Meios de Produção).</p>
                            <p class="text-amber-950 font-medium leading-relaxed mt-2">O "Proletariado" é o entregador de moto. Ele gasta sua gasolina, corre riscos no trânsito, entrega dezenas de lanches debaixo de chuva e ganha uma pequena taxa. Enquanto isso, os donos do aplicativo ganham bilhões em taxas de lucro (A Mais-Valia). Segundo Marx, esse sistema gera desigualdade porque quem realmente suou para fazer o negócio andar foi o trabalhador, mas quem enriqueceu foi quem detém o controle do sistema.</p>
                        `,
                        quiz: [
                            {
                                question: "Na teoria de Karl Marx, o que explica a geração de lucro no sistema capitalista?",
                                options: [
                                    "A bondade dos empresários que doam dinheiro para as fábricas.",
                                    "O conceito de 'Mais-Valia', que é o trabalho não pago ao proletário e apropriado pelo dono dos meios de produção.",
                                    "Apenas a venda de produtos importados de outros países.",
                                    "A lei de oferta e procura que ocorre naturalmente na natureza."
                                ],
                                answer: 1,
                                explanation: "A 'Mais-valia' é a diferença entre o que o trabalhador de fato produz de riqueza e o que ele recebe como salário. É dessa diferença (trabalho excedente não pago) que surge o lucro do capitalista."
                            }
                        ]
                    },
                    {
                        id: 'bauman_modernidade',
                        title: '2. Zygmunt Bauman (Modernidade Líquida)',
                        theory: `
                            <h3 class="text-2xl font-bold text-purple-900 mb-4">Tudo Derrete</h3>
                            <p class="mb-4 text-lg text-slate-800 font-medium">O sociólogo contemporâneo Zygmunt Bauman criou o conceito de <b>Modernidade Líquida</b>. Ele dizia que as gerações passadas viviam em uma "modernidade sólida": empregos para a vida toda, casamentos que não acabavam, certezas rígidas.</p>
                            <p class="mb-4 text-lg text-slate-800 font-medium">Hoje, tudo se transformou em líquido. O líquido não tem forma fixa, ele escorre pelos dedos, se adapta a qualquer recipiente e evapora rápido. Na nossa sociedade atual, as relações, os empregos e os valores são instáveis, fluidos e mudam o tempo todo. Nada é feito para durar.</p>
                        `,
                        analogy: `
                            <h4 class="font-bold text-amber-800 text-lg mb-2"><i class="fa-solid fa-heart-crack mr-2"></i> Traduzindo para o Mundo Real: Tinder e Cultura do Cancelamento</h4>
                            <p class="text-amber-950 font-medium leading-relaxed">Bauman explica perfeitamente as redes sociais. Você está no Tinder, não gosta do detalhe do sapato da pessoa na foto e dá 'Swipe Left' (descartando-a em 1 segundo). Isso é o que ele chama de <b>'Amores Líquidos'</b>: relações frágeis que podem ser "desconectadas" com o apertar de um botão, sem esforço para consertar problemas.</p>
                            <p class="text-amber-950 font-medium leading-relaxed mt-2">O mesmo vale para tendências e carreiras. Hoje você ama um influenciador; amanhã ele diz algo que você não gosta e ele é "cancelado" para sempre. Sua profissão dos sonhos muda a cada 6 meses. É a sociedade do descarte: tudo, inclusive pessoas, virou produto descartável.</p>
                        `,
                        quiz: [
                            {
                                question: "O que caracteriza a 'Modernidade Líquida' descrita por Bauman?",
                                options: [
                                    "A dependência global pelo uso da água e do meio ambiente.",
                                    "A criação de leis mais rígidas para controlar os jovens.",
                                    "A solidez das tradições passadas sendo respeitadas na era digital.",
                                    "A fragilidade, a falta de vínculos duradouros, o consumismo e a instabilidade constante nas relações sociais e profissionais."
                                ],
                                answer: 3,
                                explanation: "Bauman usa o estado físico dos 'líquidos' como metáfora perfeita para nossos dias: fluidos, sem forma, que não conseguem manter a forma por muito tempo. Tudo muda rapidamente e nada é feito para durar."
                            }
                        ]
                    }
                ]
            },
            {
                id: 'mod_literatura',
                title: 'Literatura: Fofoca e Drama Histórico',
                icon: 'fa-feather',
                lessons: [
                    {
                        id: 'romantismo',
                        title: '1. O Romantismo',
                        theory: `
                            <h3 class="text-2xl font-bold text-purple-900 mb-4">O Drama como Estilo de Vida</h3>
                            <p class="mb-4 text-lg text-slate-800 font-medium">O Romantismo foi um movimento do século XIX movido pela emoção exagerada, fuga da realidade, nacionalismo (idealização do índio e da pátria) e foco absoluto no "EU" (egocentrismo).</p>
                            <p class="mb-4 text-lg text-slate-800 font-medium">Eles são divididos em três gerações no Brasil: a 1ª (Nacionalista, foca na natureza e no índio como herói), a 2ª (Ultrarromântica ou "Mal do Século", marcada por pessimismo, morte, sofrência profunda) e a 3ª (Condoreira, com foco em crítica social e na luta abolicionista com Castro Alves).</p>
                        `,
                        analogy: `
                            <h4 class="font-bold text-amber-800 text-lg mb-2"><i class="fa-solid fa-guitar mr-2"></i> Traduzindo para o Mundo Real: Sofrência e Playlist Triste</h4>
                            <p class="text-amber-950 font-medium leading-relaxed">Sabe quando você termina um namoro que durou duas semanas, tranca a porta do quarto, coloca o fone de ouvido ouvindo a playlist mais triste do Spotify, chora abraçado ao travesseiro e acha que sua vida acabou e que você nunca mais vai amar ninguém?</p>
                            <p class="text-amber-950 font-medium leading-relaxed mt-2">Parabéns, você agiu exatamente como os escritores da <b>Segunda Geração Romântica (O Mal do Século)</b>. Eles idealizavam a mulher amada de forma inatingível (como um crush que nem sabe que você existe) e escreviam poemas sobre morrer de tristeza. O Romantismo é o ápice do exagero emocional, do drama adolescente e de fugir dos problemas do mundo real focando apenas nos próprios sentimentos.</p>
                        `,
                        quiz: [
                            {
                                question: "Qual é a principal característica da Segunda Geração Romântica (também conhecida como Ultrarromântica)?",
                                options: [
                                    "A luta pelo fim da escravidão.",
                                    "A valorização do índio brasileiro como o grande herói nacional.",
                                    "O pessimismo extremo, o fascínio pela morte, melancolia e o sofrimento amoroso exagerado.",
                                    "A análise científica, fria e sem sentimentos do comportamento humano."
                                ],
                                answer: 2,
                                explanation: "A Segunda Geração é a geração do 'Mal do Século'. Os jovens poetas fugiam da realidade mergulhando na depressão, idealização inalcançável da mulher e um flerte com a morte como solução para a dor existencial."
                            }
                        ]
                    },
                    {
                        id: 'realismo',
                        title: '2. Realismo e Machado de Assis',
                        theory: `
                            <h3 class="text-2xl font-bold text-purple-900 mb-4">O Fim da Ilusão</h3>
                            <p class="mb-4 text-lg text-slate-800 font-medium">Se o Romantismo era o sonho, o <b>Realismo</b> (final do século XIX) é o balde de água fria. Os autores realistas queriam mostrar a sociedade exatamente como ela era: hipócrita, interesseira, corrupta e movida a dinheiro e status.</p>
                            <p class="mb-4 text-lg text-slate-800 font-medium">Machado de Assis, o maior gênio da literatura brasileira, inaugurou o Realismo no Brasil com <i>Memórias Póstumas de Brás Cubas</i> e depois publicou o famoso <i>Dom Casmurro</i>. Ele faz análises psicológicas profundas dos personagens, mostrando que todo mundo tem uma face sombria ou interesseira por trás das aparências educadas.</p>
                        `,
                        analogy: `
                            <h4 class="font-bold text-amber-800 text-lg mb-2"><i class="fa-solid fa-masks-theater mr-2"></i> Traduzindo para o Mundo Real: O Maior 'Exposed' da História</h4>
                            <p class="text-amber-950 font-medium leading-relaxed">O Realismo é o <b>"Exposed"</b> no Twitter. Sabe aquelas pessoas que parecem ter o casamento perfeito nas fotos do Instagram, mas na vida real se odeiam ou traem? O Realismo é o movimento que pega o celular dessa pessoa e posta os prints da verdade!</p>
                            <p class="text-amber-950 font-medium leading-relaxed mt-2">No livro <i>Dom Casmurro</i>, temos a maior fofoca literária do Brasil: Capitu traiu ou não traiu Bentinho? Machado de Assis escreve o livro sob a visão de Bentinho (um homem ciumento e possessivo). O autor nos obriga a ser os detetives, mostrando que a mente humana mente e distorce fatos por ciúmes. O Realismo te diz: "Não confie em ninguém, todo mundo tem segredos".</p>
                        `,
                        quiz: [
                            {
                                question: "Em oposição ao Romantismo, qual era o objetivo central do movimento Realista na literatura?",
                                options: [
                                    "Exaltar a beleza das paisagens rurais e focar nos sonhos puros de amor.",
                                    "Fazer uma crítica fria, objetiva e psicológica da sociedade, denunciando a hipocrisia, o egoísmo e o casamento por interesse.",
                                    "Defender a Monarquia e criar histórias de ficção científica.",
                                    "Promover textos de autoajuda e conselhos morais positivos."
                                ],
                                answer: 1,
                                explanation: "O Realismo é 'anti-romântico'. Ele tira as máscaras da alta sociedade burguesa, usando a razão para mostrar que, muitas vezes, as relações humanas (como os casamentos da época) eram baseadas em interesse financeiro e status social, não em amor."
                            }
                        ]
                    }
                ]
            },
            {
                id: 'mod_artes',
                title: 'Artes: Quebrando Padrões',
                icon: 'fa-palette',
                lessons: [
                    {
                        id: 'vanguardas',
                        title: '1. Vanguardas Europeias',
                        theory: `
                            <h3 class="text-2xl font-bold text-purple-900 mb-4">A Revolta dos Pincéis</h3>
                            <p class="mb-4 text-lg text-slate-800 font-medium">No início do século XX, com a invenção da fotografia e a eclosão da Primeira Guerra Mundial, os artistas europeus pensaram: "Por que pintar a realidade como ela é, se uma câmera fotográfica já faz isso em 1 segundo?". Surgiram as <b>Vanguardas</b> (o pelotão de frente que ataca primeiro na guerra), quebrando todas as regras da arte clássica.</p>
                            <ul class="list-disc pl-6 mb-4 space-y-3 text-slate-800 font-medium">
                                <li><b>Cubismo:</b> Pablo Picasso fragmentou as imagens, mostrando todos os lados de um rosto ao mesmo tempo, parecendo vidro quebrado.</li>
                                <li><b>Surrealismo:</b> Salvador Dalí pintou o inconsciente. Relógios derretendo, animais com pernas de pau. É a arte que parece saída dos sonhos (ou pesadelos).</li>
                                <li><b>Dadaísmo:</b> A arte do "absurdo" para chocar e provocar a sociedade (ex: colocar um mictório num museu e chamar de "A Fonte" de Marcel Duchamp).</li>
                            </ul>
                        `,
                        analogy: `
                            <h4 class="font-bold text-amber-800 text-lg mb-2"><i class="fa-solid fa-camera-retro mr-2"></i> Traduzindo para o Mundo Real: Filtros Bizarros e IA</h4>
                            <p class="text-amber-950 font-medium leading-relaxed">Você já usou aqueles filtros de TikTok que deformam o seu rosto, colocam seus olhos no lugar da boca, ou já pediu para uma Inteligência Artificial criar a imagem de "um cachorro andando de skate no espaço"? As Vanguardas faziam exatamente isso, só que com tintas em 1910!</p>
                            <p class="text-amber-950 font-medium leading-relaxed mt-2">O <b>Surrealismo</b> é aquele sonho sem pé nem cabeça que você tenta contar pros seus amigos quando acorda. O <b>Cubismo</b> é como se você tirasse uma selfie panorâmica e mexesse a câmera no meio da foto, deixando tudo distorcido e com vários ângulos. Eles queriam chocar os adultos engravatados da época, assim como memes sem sentido (Shitpost) confundem as gerações mais velhas hoje.</p>
                        `,
                        quiz: [
                            {
                                question: "O que motivou o surgimento de movimentos como o Cubismo e o Surrealismo no início do século XX?",
                                options: [
                                    "A ordem do Papa para que a arte fosse mais estranha.",
                                    "O desejo de copiar perfeitamente a natureza, pois a fotografia havia sido proibida.",
                                    "A necessidade de romper com a arte clássica e realista, já que a invenção da fotografia tornou inútil apenas 'copiar' a realidade, passando a representar as emoções, a velocidade e os sonhos.",
                                    "A falta de tintas coloridas por causa da Guerra, o que forçou o uso de formas feias."
                                ],
                                answer: 2,
                                explanation: "As Vanguardas (como Cubismo, Surrealismo, Futurismo) foram movimentos de ruptura. Com a câmera fotográfica capturando a realidade perfeitamente, o artista se viu livre para distorcer as formas, usar cores irreais e pintar o que estava dentro da mente, não o que os olhos viam na rua."
                            }
                        ]
                    }
                ]
            }
        ];

        // --- Variáveis Globais ---
        const navMenu = document.getElementById('navMenu');
        const mainContent = document.getElementById('mainContent');
        const mobileMenuBtn = document.getElementById('mobileMenuBtn');
        const sidebar = document.getElementById('sidebar');
        const mobileOverlay = document.getElementById('mobileOverlay');

        // --- Inicializar Menu ---
        function initNav() {
            let html = '';
            curriculum.forEach(module => {
                html += `
                    <div class="mb-6">
                        <h2 class="text-xs font-bold text-purple-700 uppercase tracking-widest mb-3 pl-2 flex items-center">
                            <i class="fa-solid ${module.icon} mr-2"></i> ${module.title}
                        </h2>
                        <ul class="space-y-1">
                `;
                module.lessons.forEach(lesson => {
                    html += `
                        <li>
                            <button onclick="loadLesson('${module.id}', '${lesson.id}')" 
                                id="btn-${lesson.id}"
                                class="w-full text-left px-4 py-3 rounded-lg text-sm text-slate-700 hover:bg-purple-100 hover:text-purple-800 transition-all duration-200 focus:outline-none border-l-4 border-transparent hover:border-purple-400 font-bold">
                                ${lesson.title}
                            </button>
                        </li>
                    `;
                });
                html += `</ul></div>`;
            });
            navMenu.innerHTML = html;
        }

        // --- Leitor de Texto ---
        function playAudio(text) {
            if ('speechSynthesis' in window) {
                window.speechSynthesis.cancel();
                const cleanText = text.replace(/<[^>]*>?/gm, '');
                const utterance = new SpeechSynthesisUtterance(cleanText);
                utterance.lang = 'pt-BR';
                utterance.rate = 1.0;
                window.speechSynthesis.speak(utterance);
            } else {
                alert("Seu navegador não suporta leitura de áudio.");
            }
        }

        // --- Carregar Lição e Renderizar HTML ---
        function loadLesson(moduleId, lessonId) {
            const module = curriculum.find(m => m.id === moduleId);
            const lesson = module.lessons.find(l => l.id === lessonId);

            // Atualiza visual do menu ativo
            document.querySelectorAll('button[id^="btn-"]').forEach(btn => {
                btn.classList.remove('bg-purple-100', 'text-purple-900', 'border-purple-500', 'font-bold');
                btn.classList.add('border-transparent');
            });
            const activeBtn = document.getElementById(`btn-${lessonId}`);
            if (activeBtn) {
                activeBtn.classList.remove('border-transparent');
                activeBtn.classList.add('bg-purple-100', 'text-purple-900', 'border-purple-500', 'font-bold');
            }

            if(window.innerWidth < 768) toggleMobileMenu();

            let html = `
                <div class="fade-in bg-white rounded-2xl shadow-xl shadow-slate-200/50 border border-slate-200 overflow-hidden">
                    <!-- Cabeçalho -->
                    <div class="gradient-bg p-8 md:p-10 text-slate-900 relative overflow-hidden border-b border-purple-200">
                        <div class="absolute -right-4 -top-4 opacity-20 text-9xl text-purple-600">
                            <i class="fa-solid ${module.icon}"></i>
                        </div>
                        <div class="flex justify-between items-start relative z-10">
                            <div>
                                <span class="inline-block px-3 py-1 bg-purple-100 text-purple-900 rounded-full text-xs font-bold uppercase tracking-wider mb-4 border border-purple-300 shadow-sm">${module.title}</span>
                                <h1 class="text-3xl md:text-5xl font-extrabold leading-tight text-slate-900">${lesson.title}</h1>
                            </div>
                            <button onclick="playAudio(\`${lesson.theory} ${lesson.analogy}\`)" class="hidden md:flex flex-col items-center justify-center bg-white/60 hover:bg-white/90 border border-purple-300 p-3 rounded-xl transition-colors shrink-0 ml-4 shadow-sm text-purple-900" title="Ouvir a aula">
                                <i class="fa-solid fa-headphones text-2xl mb-1 text-purple-700"></i>
                                <span class="text-[10px] font-bold uppercase tracking-wider">Ouvir Aula</span>
                            </button>
                        </div>
                    </div>

                    <div class="p-6 md:p-10">
                        <!-- Teoria Clássica -->
                        <section class="mb-10">
                            <div class="prose max-w-none text-slate-800">
                                ${lesson.theory}
                            </div>
                        </section>

                        <!-- Traduzindo para o Mundo Real (A Sacada!) -->
                        <section class="mb-12 gradient-card p-6 md:p-8 rounded-2xl border border-purple-200 shadow-inner">
                            ${lesson.analogy}
                        </section>

                        <!-- Quiz / Conhecimento -->
                        <section class="bg-slate-50 p-6 md:p-8 rounded-2xl border border-slate-200 shadow-inner">
                            <h2 class="text-2xl font-bold text-slate-800 mb-2 flex items-center">
                                <i class="fa-solid fa-list-check text-purple-600 mr-3 text-3xl"></i> Desafio ENEM
                            </h2>
                            <p class="text-slate-600 font-medium mb-8">Baseado na analogia e na teoria, veja se consegue resolver essa questão de prova!</p>
                            
                            <div id="quizContainer" class="space-y-8">
                                ${lesson.quiz.map((q, qIndex) => `
                                    <div class="bg-white p-6 md:p-8 rounded-xl border border-slate-200 shadow-sm transition-all" id="questionBlock-${qIndex}">
                                        <div class="flex items-start gap-4 mb-5">
                                            <div class="bg-purple-100 text-purple-800 w-10 h-10 rounded-full flex items-center justify-center font-bold text-lg flex-shrink-0 border border-purple-200">
                                                ?
                                            </div>
                                            <p class="font-bold text-slate-800 text-lg pt-1">${q.question}</p>
                                        </div>
                                        
                                        <div class="space-y-3 pl-0 md:pl-14">
                                            ${q.options.map((opt, optIndex) => `
                                                <button onclick="handleAnswer('${module.id}', '${lesson.id}', ${qIndex}, ${optIndex}, ${q.answer})"
                                                    id="optBtn-${qIndex}-${optIndex}"
                                                    class="quiz-option w-full text-left p-4 border-2 border-slate-100 rounded-xl bg-slate-50 text-slate-800 font-semibold hover:border-purple-400 hover:bg-purple-50 focus:outline-none transition-all">
                                                    ${opt}
                                                </button>
                                            `).join('')}
                                        </div>
                                        
                                        <div id="feedback-${qIndex}" class="mt-5 ml-0 md:ml-14 p-4 rounded-lg hidden"></div>
                                    </div>
                                `).join('')}
                            </div>
                        </section>
                    </div>
                </div>
            `;

            mainContent.innerHTML = html;
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        // --- Lógica do Quiz ---
        function handleAnswer(moduleId, lessonId, questionIndex, selectedOptionIndex, correctOptionIndex) {
            const module = curriculum.find(m => m.id === moduleId);
            const lesson = module.lessons.find(l => l.id === lessonId);
            const explanationText = lesson.quiz[questionIndex].explanation;

            const qBlock = document.getElementById(`questionBlock-${questionIndex}`);
            const buttons = qBlock.querySelectorAll('button');
            buttons.forEach(btn => btn.disabled = true); 
            
            const isCorrect = selectedOptionIndex === correctOptionIndex;
            const selectedBtn = document.getElementById(`optBtn-${questionIndex}-${selectedOptionIndex}`);
            const correctBtn = document.getElementById(`optBtn-${questionIndex}-${correctOptionIndex}`);
            const feedbackEl = document.getElementById(`feedback-${questionIndex}`);

            selectedBtn.classList.remove('border-slate-100', 'hover:border-purple-400', 'bg-slate-50', 'hover:bg-purple-50');

            if (isCorrect) {
                selectedBtn.classList.add('border-emerald-500', 'bg-emerald-50', 'text-emerald-800', 'font-bold');
                selectedBtn.innerHTML = `<div class="flex justify-between items-center w-full"><span>${selectedBtn.innerHTML}</span> <i class="fa-solid fa-circle-check text-emerald-500 text-xl"></i></div>`;
                qBlock.classList.add('border-emerald-200', 'bg-emerald-50/20');
                
                feedbackEl.innerHTML = `
                    <div class="flex items-start gap-3">
                        <i class="fa-solid fa-award text-2xl text-emerald-600 mt-1"></i>
                        <div>
                            <h4 class="font-bold text-emerald-800 text-lg">Gabartitou!</h4>
                            <p class="text-emerald-700 mt-1 leading-relaxed font-medium">${explanationText}</p>
                        </div>
                    </div>
                `;
                feedbackEl.className = "mt-5 ml-0 md:ml-14 p-5 rounded-xl border border-emerald-200 bg-emerald-100/50 block fade-in";
            } else {
                selectedBtn.classList.add('border-rose-500', 'bg-rose-50', 'text-rose-800', 'opacity-70');
                selectedBtn.innerHTML = `<div class="flex justify-between items-center w-full"><span>${selectedBtn.innerHTML}</span> <i class="fa-solid fa-circle-xmark text-rose-500 text-xl"></i></div>`;
                
                if (correctBtn) {
                    correctBtn.classList.remove('border-slate-100', 'bg-slate-50');
                    correctBtn.classList.add('border-emerald-500', 'bg-emerald-50', 'text-emerald-800', 'font-bold');
                    correctBtn.innerHTML = `<div class="flex justify-between items-center w-full"><span>${correctBtn.innerHTML}</span> <i class="fa-solid fa-arrow-left text-emerald-500 text-xl"></i></div>`;
                }
                
                qBlock.classList.add('border-rose-200');

                feedbackEl.innerHTML = `
                    <div class="flex items-start gap-3">
                        <i class="fa-solid fa-circle-info text-2xl text-rose-500 mt-1"></i>
                        <div>
                            <h4 class="font-bold text-rose-800 text-lg">Pega essa visão:</h4>
                            <p class="text-rose-700 mt-1 font-bold">A alternativa correta está destacada em verde.</p>
                            <div class="mt-3 pt-3 border-t border-rose-200">
                                <span class="text-xs uppercase font-extrabold text-rose-600 tracking-wider">Explicação Oficial:</span>
                                <p class="text-rose-900 mt-1 leading-relaxed text-sm md:text-base font-medium">${explanationText}</p>
                            </div>
                        </div>
                    </div>
                `;
                feedbackEl.className = "mt-5 ml-0 md:ml-14 p-5 rounded-xl border border-rose-200 bg-rose-50 block fade-in";
            }
        }

        // --- Menu Mobile Toggle ---
        function toggleMobileMenu() {
            sidebar.classList.toggle('-translate-x-full');
            mobileOverlay.classList.toggle('hidden');
            
            const icon = mobileMenuBtn.querySelector('i');
            if(sidebar.classList.contains('-translate-x-full')) {
                icon.classList.remove('fa-times');
                icon.classList.add('fa-bars');
            } else {
                icon.classList.remove('fa-bars');
                icon.classList.add('fa-times');
            }
        }

        mobileMenuBtn.addEventListener('click', toggleMobileMenu);
        mobileOverlay.addEventListener('click', toggleMobileMenu);

        // --- Start App ---
        initNav();
        
        if(window.innerWidth >= 768) {
            loadLesson('mod_filosofia', 'platao_caverna');
        }

    </script>
</body>
</html>
