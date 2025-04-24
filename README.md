*Introdução ao Docker para Programadores R*

O objetivo deste curso é alcançar um público que já está familiarizado com o R e quer expandir seus conhecimentos para o mundo da conteinerização.

**Importante:**
Por ser desenvolvido dentro do ambiente R Swirl, é importante lembrarmos que buscamos vencer as limitações deste ambiente sendo mais informativos e validando o aprendizado. A prática, todavia, deve ser feita no prompt de comando do sistema operacional, fora do ambiente R. O **swirl é focado no aprendizado da linguagem R e conceitos relacionados diretamente ao R**. Ele opera dentro do ambiente do R (console ou RStudio) e, o mais comum é ele ser usado para interagir com o usuário pedindo para executar comandos em R e fornecendo feedback sobre o código R.

**O Docker, por outro lado, é uma tecnologia de conteinerização que opera no nível do sistema operacional.** Os comandos do Docker são executados no terminal (fora do R) e envolvem a criação e gerenciamento de contêineres, imagens, redes, etc.

**Limitações:**

As limitações de criar um curso de Docker "dentro" do swirl são:

* **Execução de comandos Docker:** O swirl não tem a capacidade de executar comandos do sistema operacional diretamente. Ele espera comandos em R.
* **Interação com o sistema:** O aprendizado de Docker envolve a interação com o sistema de arquivos, a rede e outros aspectos do sistema operacional, o que está fora do escopo do R e do swirl.
* **Visualização de contêineres:** A criação e execução de contêineres são processos que ocorrem fora do ambiente R.

**Abordagem:**

Embora não seja possível uma prática plena neste curso de Docker, efetivamente executando comandos Docker *dentro* do swirl, nós iremos:

1.  **Apresentar os conceitos básicos do Docker usando texto e explicações no formato do swirl.**
2.  **Fornecer exemplos de comandos Docker que o usuário pode executar *manualmente* no seu terminal.**
3.  **Fazer perguntas sobre os conceitos e os resultados esperados dos comandos Docker.**

**Estrutura do curso "Introdução ao Docker para Usuários de R":**

Podemos estruturar o curso em lições que abordem os seguintes tópicos:

**Lição 1: O que é Docker e por que usar?**

* Explicação dos problemas que o Docker resolve (dependências, ambientes consistentes, implantação).
* Analogias para facilitar a compreensão (contêineres como caixas, imagens como moldes).
* Vantagens do Docker no contexto da ciência de dados e do R.

**Lição 2: Conceitos Fundamentais do Docker**

* **Imagens:** O que são, como são criadas (Dockerfiles).
* **Contêineres:** O que são, como são criados a partir de imagens, ciclo de vida.
* **Dockerfiles:** Introdução à estrutura básica de um Dockerfile (FROM, RUN, COPY, WORKDIR, CMD/ENTRYPOINT).
* **Docker Hub:** O que é e como usar para encontrar imagens prontas.

**Lição 3: Instalando o Docker (Instruções Genéricas)**

* Observação de que a instalação varia dependendo do sistema operacional.
* Fornecimento de links para a documentação oficial do Docker para diferentes plataformas (Linux, macOS, Windows).
* Instrução para verificar a instalação no terminal (`docker --version`).

**Lição 4: Trabalhando com Imagens**

* Comando `docker pull`: como baixar imagens do Docker Hub.
    * Exemplo: `docker pull ubuntu:latest` (Instrução para executar *no terminal*).
    * Pergunta no swirl: "Qual comando você usaria para baixar a imagem mais recente do Ubuntu do Docker Hub?"
* Comando `docker images`: como listar as imagens locais.
    * Instrução para executar *no terminal*.
    * Pergunta no swirl sobre as informações exibidas (REPOSITORY, TAG, IMAGE ID, CREATED, SIZE).
* Comando `docker rmi`: como remover imagens.
    * Aviso sobre remover imagens em uso.
    * Exemplo: `docker rmi <IMAGE ID>` (Instrução para executar *no terminal*).
    * Pergunta no swirl sobre o que acontece ao executar este comando.

**Lição 5: Trabalhando com Contêineres**

* Comando `docker run`: como criar e iniciar contêineres.
    * Exemplos básicos:
        * `docker run ubuntu:latest echo "Olá do contêiner"`
        * `docker run -it ubuntu:latest /bin/bash` (Modo interativo - instrução para sair com `exit`).
    * Pergunta no swirl sobre a diferença entre os dois comandos.
* Opções importantes do `docker run`:
    * `-d`: executar em segundo plano (detached).
    * `-p <host_port>:<container_port>`: mapeamento de portas.
    * `-v <host_path>:<container_path>`: montagem de volumes.
    * `-name <container_name>`: dar um nome ao contêiner.
    * Exemplos com essas opções (instrução para executar *no terminal*).
    * Perguntas no swirl sobre o propósito de cada opção.
* Comando `docker ps`: como listar contêineres em execução.
    * Instrução para executar *no terminal*.
    * Pergunta no swirl sobre as informações exibidas (CONTAINER ID, IMAGE, COMMAND, CREATED, STATUS, PORTS, NAMES).
* Comando `docker ps -a`: como listar todos os contêineres (em execução e parados).
    * Instrução para executar *no terminal*.
    * Pergunta no swirl sobre a diferença entre `docker ps` e `docker ps -a`.
* Comando `docker stop <container_id_or_name>`: como parar um contêiner.
    * Instrução para executar *no terminal*.
    * Pergunta no swirl sobre o que acontece com o contêiner.
* Comando `docker start <container_id_or_name>`: como iniciar um contêiner parado.
    * Instrução para executar *no terminal*.
    * Pergunta no swirl sobre o estado do contêiner após este comando.
* Comando `docker rm <container_id_or_name>`: como remover um contêiner parado.
    * Aviso sobre a perda de dados se não houver volumes.
    * Instrução para executar *no terminal*.
    * Pergunta no swirl sobre a diferença entre parar e remover um contêiner.

**Lição 6: Docker e R (Exemplos)**

* Discussão sobre como o Docker pode ser usado para executar aplicações R de forma consistente.
* Exemplo de um Dockerfile simples para executar um script R.
    ```dockerfile
    FROM r-base:latest
    COPY script.R /app/
    WORKDIR /app
    CMD ["Rscript", "script.R"]
    ```
    * Explicação de cada linha do Dockerfile.
    * Instrução para criar um arquivo `script.R` simples (ex: `print("Olá do Docker com R!")`).
    * Instrução para construir a imagem (`docker build -t r-app .` - executar *no terminal*).
    * Instrução para executar o contêiner (`docker run r-app` - executar *no terminal*).
    * Perguntas no swirl sobre o processo.

**Implementação no swirl:**

Para cada lição, usamos as funções do swirl para apresentar informações, fazer perguntas de múltipla escolha, perguntas de resposta curta e, crucialmente, **instruir o usuário a executar comandos no seu terminal e, em seguida, fazer perguntas sobre o que eles observaram ou aprenderam.**

**Exemplo de interação no swirl:**

```R
# Dentro de uma lição do swirl

info("Nesta lição, vamos aprender a baixar imagens do Docker Hub.")
info("O comando para baixar uma imagem é 'docker pull'.")
info("Por exemplo, para baixar a imagem mais recente do sistema operacional Ubuntu, você executaria o seguinte comando no seu terminal:")
code_output("docker pull ubuntu:latest")
readline("Pressione Enter depois de executar o comando no seu terminal...")

question("Depois de executar o comando, qual mensagem você viu indicando que a imagem foi baixada com sucesso?")
answer("Downloaded newer image for ubuntu:latest")
answer("Status: Downloaded newer image for ubuntu:latest")
answer("Successfully pulled ubuntu:latest")
correct_answer("Status: Downloaded newer image for ubuntu:latest")
explanation("Você deve ter visto uma mensagem indicando que a imagem foi baixada.")

# Próxima pergunta
question("Agora, use o comando 'docker images' no seu terminal. Quantas imagens você tem listadas agora (pode variar)?")
numeric_answer(1:100) # Ajuste o range conforme necessário
explanation("O número de imagens listadas dependerá do que você já tem no seu sistema.")
```

**Desafios:**

* **Dependência do ambiente externo:** O aprendizado depende do usuário ter o Docker instalado e funcionando corretamente no seu sistema. O swirl não pode verificar isso diretamente.
* **Limitação da interatividade:** A interatividade se limita a perguntar sobre os resultados dos comandos executados fora do R. Não é possível uma interação direta com o ambiente Docker dentro do swirl.
* **Instruções claras:** É crucial fornecer instruções muito claras sobre quando e o que executar no terminal.

**Conclusão:**

Embora este curso introdutório de Docker *puramente* dentro do swirl seja dificultado pelas limitações do ambiente R, ele é eficaz por **combinar a apresentação de conceitos no formato do swirl com a instrução para executar comandos Docker no terminal e a subsequente avaliação da compreensão dentro do swirl.**

Este tipo de curso será valioso para usuários de R que desejam dar os primeiros passos no mundo do Docker, aproveitando a familiaridade que já possuem com o ambiente de aprendizado do swirl.
