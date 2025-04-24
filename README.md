*Introdução ao Docker para Programadores R*

O objetivo deste curso é alcançar um público que já está familiarizado com o R e quer expandir seus conhecimentos para o mundo da conteinerização.

**Importante:**
Por ser desenvolvido dentro do ambiente R SWIRL, é importante lembrarmos que buscamos vencer as limitações deste ambiente sendo mais informativos e validando o aprendizado. A prática, todavia, deve ser feita no prompt de comando do sistema operacional, fora do ambiente R. O **SWIRL é focado no aprendizado da linguagem R e conceitos relacionados diretamente ao R**. Ele opera dentro do ambiente do R (console ou RStudio) e, o mais comum é ele ser usado para interagir com o usuário pedindo para executar comandos em R e fornecendo feedback sobre o código R.

**O Docker, por outro lado, é uma tecnologia de conteinerização que opera no nível do sistema operacional.** Os comandos do Docker são executados no terminal (fora do R) e envolvem a criação e gerenciamento de contêineres, imagens, redes, etc.

**Limitações:**

As limitações de criar um curso de Docker "dentro" do SWIRL são:

* **Execução de comandos Docker:** O SWIRL não tem a capacidade de executar comandos do sistema operacional diretamente. Ele espera comandos em R.
* **Interação com o sistema:** O aprendizado de Docker envolve a interação com o sistema de arquivos, a rede e outros aspectos do sistema operacional, o que está fora do escopo do R e do SWIRL.
* **Visualização de contêineres:** A criação e execução de contêineres são processos que ocorrem fora do ambiente R.

**Abordagem:**

Embora não seja possível uma prática plena neste curso de Docker, efetivamente executando comandos Docker *dentro* do SWIRL, nós iremos:

1.  **Apresentar os conceitos básicos do Docker usando texto e explicações no formato do SWIRL.**
2.  **Fornecer exemplos de comandos Docker que o usuário pode executar *manualmente* no seu terminal.**
3.  **Fazer perguntas sobre os conceitos e os resultados esperados dos comandos Docker.**

**Estrutura do curso "Introdução ao Docker para Usuários de R":**

O curso está estruturado em lições que abordam os seguintes tópicos:

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
* Comando `docker images`: como listar as imagens locais.
* Comando `docker rmi`: como remover imagens.

**Lição 5: Trabalhando com Contêineres**

* Comando `docker run`: como criar e iniciar contêineres.
* Opções importantes do `docker run`.
* Comando `docker ps`: como listar contêineres em execução.
* Comando `docker ps -a`: como listar todos os contêineres (em execução e parados).
* Comando `docker stop <container_id_or_name>`: como parar um contêiner.
* Comando `docker start <container_id_or_name>`: como iniciar um contêiner parado.
* Comando `docker rm <container_id_or_name>`: como remover um contêiner parado.

**Lição 6: Docker e R (Exemplos)**

* Discussão sobre como o Docker pode ser usado para executar aplicações R de forma consistente.
* Exemplo de um Dockerfile simples para executar um script R.
* Explicação de cada linha do Dockerfile.
* Instrução para criar um arquivo `script.R` simples (ex: `print("Olá do Docker com R!")`).
* Instrução para construir a imagem (`docker build -t r-app .` - executar *no terminal*).
* Instrução para executar o contêiner (`docker run r-app` - executar *no terminal*).
* Perguntas no SWIRL sobre o processo.

**Implementação no SWIRL:**

Para cada lição, usamos as funções do SWIRL para apresentar informações, fazer perguntas de múltipla escolha, perguntas de resposta curta e, crucialmente, **instruimos o usuário a executar comandos no seu terminal e, em seguida, fazemos perguntas sobre o que eles observaram ou aprenderam.**

**Exemplo de interação no SWIRL:**

```R
# Dentro de uma lição do SWIRL

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

* **Dependência do ambiente externo:** O aprendizado depende do usuário ter o Docker instalado e funcionando corretamente no seu sistema. O SWIRL não pode verificar isso diretamente.
* **Limitação da interatividade:** A interatividade se limita a perguntar sobre os resultados dos comandos executados fora do R. Não é possível uma interação direta com o ambiente Docker dentro do SWIRL.
* **Instruções claras:** Esperamos ter fornecido instruções claras sobre quando e o que executar no terminal.

**Conclusão:**

Embora este curso introdutório de Docker *puramente* dentro do SWIRL seja dificultado pelas limitações do ambiente R, ele é eficaz por **combinar a apresentação de conceitos no formato do SWIRL com a instrução para executar comandos Docker no terminal e a subsequente avaliação da compreensão dentro do SWIRL.**

Este tipo de curso será valioso para usuários de R que desejam dar os primeiros passos no mundo do Docker, aproveitando a familiaridade que já possuem com o ambiente de aprendizado do SWIRL.
