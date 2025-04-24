# Lição 2: Conceitos Fundamentais do Docker
# Nesta lição, vamos aprofundar nos pilares do Docker: imagens, contêineres, Dockerfiles e Docker Hub.

```R
# Lição 2: Conceitos Fundamentais do Docker

lesson_name("Introdução ao Docker para Programadores R - Lição 2")

info("Na lição anterior, introduzimos brevemente os conceitos de imagens e contêineres. Agora, vamos explorá-los em mais detalhes, além de conhecer os Dockerfiles e o Docker Hub.")

info("Começando pelas **imagens Docker**, lembre-se que elas são como moldes ou templates estáticos. Uma imagem contém tudo o que é necessário para executar um aplicativo: o código, as bibliotecas, as ferramentas do sistema e as configurações.")

question("Qual das seguintes analogias melhor descreve uma imagem Docker?")
answer("Um programa de computador em execução.")
answer("Uma cópia de um sistema operacional.")
answer("Um modelo estático para criar contêineres.")
answer("Um arquivo de dados.")
correct_answer("Um modelo estático para criar contêineres.")
explanation("Correto! A imagem serve como base para criar instâncias executáveis, que são os contêineres.")

info("As imagens são construídas usando um arquivo de texto chamado **Dockerfile**. Este arquivo contém uma série de instruções que o Docker segue para montar a imagem, camada por camada.")

info("Pense no Dockerfile como uma receita para criar sua imagem. Cada linha no Dockerfile adiciona uma camada ao sistema de arquivos da imagem.")

question("O que é um Dockerfile?")
answer("Um contêiner Docker em formato de arquivo.")
answer("Um arquivo de configuração para o Docker Engine.")
answer("Um arquivo de texto com instruções para construir uma imagem Docker.")
answer("Um repositório de imagens Docker.")
correct_answer("Um arquivo de texto com instruções para construir uma imagem Docker.")
explanation("Exatamente! O Dockerfile é essencial para a criação automatizada de imagens.")

info("Um Dockerfile possui uma estrutura básica com algumas instruções comuns, como:")
info("- `FROM`: Define a imagem base a partir da qual sua imagem será construída (por exemplo, `ubuntu:latest` ou `r-base:latest`).")
info("- `RUN`: Executa comandos dentro da imagem (por exemplo, instalar software, criar diretórios).")
info("- `COPY`: Copia arquivos e diretórios do seu host para dentro da imagem.")
info("- `WORKDIR`: Define o diretório de trabalho dentro da imagem para os comandos subsequentes.")
info("- `CMD` ou `ENTRYPOINT`: Especifica o comando a ser executado quando um contêiner é iniciado a partir da imagem.")

question("Qual instrução em um Dockerfile é usada para definir a imagem base?")
answer("RUN")
answer("COPY")
answer("FROM")
answer("WORKDIR")
correct_answer("FROM")
explanation("Correto! A instrução `FROM` é sempre a primeira em um Dockerfile.")

info("Agora, vamos falar sobre **contêineres Docker**. Um contêiner é uma instância em execução de uma imagem. Ele é um ambiente isolado que contém tudo o que o aplicativo precisa para rodar.")

info("Quando você executa uma imagem com o comando `docker run`, o Docker cria um contêiner a partir dessa imagem. Você pode ter múltiplos contêineres em execução a partir da mesma imagem.")

question("O que acontece quando você usa o comando `docker run` com uma imagem?")
answer("Uma nova imagem é criada.")
answer("Um contêiner em execução é criado a partir da imagem.")
answer("A imagem é modificada.")
answer("O Dockerfile da imagem é exibido.")
correct_answer("Um contêiner em execução é criado a partir da imagem.")
explanation("Isso mesmo! O `docker run` é o comando para iniciar contêineres.")

info("Os contêineres têm um **ciclo de vida**: eles podem ser criados, iniciados, parados, reiniciados e, finalmente, removidos.")

question("Em qual estado um contêiner está quando ele foi criado mas ainda não está executando?")
answer("Running (Executando)")
answer("Stopped (Parado)")
answer("Created (Criado)")
answer("Removed (Removido)")
correct_answer("Created (Criado)")
explanation("Correto! Após a criação, o contêiner precisa ser iniciado para executar.")

info("Finalmente, temos o **Docker Hub**. Pense nele como uma biblioteca pública ou uma loja de aplicativos para imagens Docker. Milhares de imagens prontas para uso, mantidas por desenvolvedores e comunidades de todo o mundo, estão disponíveis lá.")

info("Você pode usar o comando `docker pull` (que vimos na lição anterior) para baixar imagens pré-construídas do Docker Hub para sua máquina.")

question("Para que serve o Docker Hub?")
answer("Para armazenar seus Dockerfiles localmente.")
answer("Para compartilhar contêineres em execução.")
answer("Para encontrar e baixar imagens Docker pré-construídas.")
answer("Para gerenciar seus contêineres em execução.")
correct_answer("Para encontrar e baixar imagens Docker pré-construídas.")
explanation("Exatamente! O Docker Hub é uma fonte valiosa de imagens prontas para usar.")

info("Na próxima lição, vamos aprender como instalar o Docker no seu sistema. Prepare-se para começar a interagir com o Docker de verdade!")

# Fim da Lição 2
```

Esta lição aborda os conceitos fundamentais do Docker, mantendo o formato de texto informativo e perguntas conceituais dentro do ambiente `swirl`. Na próxima lição, focaremos na instalação do Docker, que será mais informativa, com links para a documentação oficial.
