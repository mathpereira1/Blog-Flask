# microblog
 trying out Flask
Parte 1:
Os primeiros passos incluíram a instalação do Python, Flask e um lembrete rápido da importância dos ambientes virtuais, afinal, caso você tenha os direitos administrativos do seu computador, instalar um pacote python como o Flask para todos os usuários poderá causar dor de cabeça mais tarde, pois você pode construir sua aplicação com o Flask 1.x e quando for construir uma outra no futuro, e atualizar o flask para 2.x ou outra release, poderá quebrar o funcionamento da anterior.

Assim com VENVs, é possível administrar versões diferentes de pacotes para cada aplicação

criei o venv, ativei e instalei o flask nele,

fiz o aplicativo ser um pacote callavel com o __init__.py, e nele escrevi um código na ordem em que o routes fique abaixo, para evitar o problema de circular imports, algo comum em aplicações flask

e no módulo de rotas, estabeleci as URLS que chamariam a função/view index, que entrega um simples hello, world

a apresentação de conceitos de decorators, algo nativo do python

e por fim, fim o modulo da aplicação principal no top level do projeto, microblog.py

para rodar a primeira vez, foi importante setar uma variavel de ambiente que indicasse FLASK_APP=microblog.py e depois apenas flask run, tudo dentro do meu cmd com venv ativo

de qualquer forma, é util instalar o pacote python-dotenv para salvarmos as variaveis de ambiente em um arquivo .flaskenv separado, assim as variaveis perduraram e não serão esquecidas ao fechar o cmd

Mock objects: Você pode forjar objetos de teste para que não haja preocupações com possíveis dependências de features futuras, por exemplo
Você quer programar uma tela de início que dê as boas vindas ao seu usuário,
em vez de se preocupar com um sistema de registros de usuário para começar, você pode fazer um mock user *user = {'username': 'Miguel'}*

é muito importante deixar os templates separados da lógica do seu projeto, afinal quando você precisar fazer uma mudança no HTML, não precisará alterar manualmente todas as view functions já existentes, para isso teremos um diretório exclusivo para esses templates

{{}} são placeholders que ao invocar a função render_template que é built-in do Flask, ela usará a engine Jinja2 para buildar o template HTML e substituir o conteúdo dinâmico nestes placeholders

Herança de templates, muitas páginas possuem uma aba de navegação que se repete em várias abas, como um Home, Sobre Nós, etc, e para isso podemos repetir ela em vários templates, escrevendo apenas uma vez a partir de uma herança de template