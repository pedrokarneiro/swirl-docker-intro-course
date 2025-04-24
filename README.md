# Introdução ao Docker para Programadores R

Este curso tem como objetivo introduzir o mundo da conteinerização para programadores que já possuem familiaridade com a linguagem R.

> **💡 Para informações detalhadas sobre como instalar e iniciar este curso, consulte o arquivo [`doc/manual.md`](doc/manual.md).**

> **💡 Para informações detalhadas sobre a estrutura de arquivos deste curso, consulte o arquivo [`doc/estrutura.md`](doc/estrutura.md).**

## Importante: Entendendo a Abordagem no Ambiente SWIRL

É crucial compreender que este curso é desenvolvido dentro do ambiente R SWIRL, que é primariamente focado no aprendizado da linguagem R e seus conceitos relacionados. O SWIRL opera dentro do R (console ou RStudio) e sua interação principal envolve a execução de comandos R com feedback imediato.

O **Docker**, por outro lado, é uma tecnologia de conteinerização que opera no nível do sistema operacional. Seus comandos são executados diretamente no terminal (fora do R) e abrangem a criação e o gerenciamento de contêineres, imagens, redes, etc.

## Limitações do SWIRL para um Curso de Docker

Devido à sua natureza, o SWIRL apresenta algumas limitações para um curso prático de Docker:

* **Execução de Comandos Docker:** O SWIRL não consegue executar comandos do sistema operacional diretamente. Ele espera e interpreta apenas comandos em R.
* **Interação com o Sistema Operacional:** O aprendizado efetivo de Docker envolve interações com o sistema de arquivos, rede e outros aspectos do SO, o que está além do escopo do R e do SWIRL.
* **Visualização de Contêineres:** A criação e a execução de contêineres são processos externos ao ambiente R.

## Nossa Abordagem para o Aprendizado de Docker no SWIRL

Para superar essas limitações e proporcionar um aprendizado eficaz, adotaremos a seguinte abordagem:

1.  **Apresentação Conceitual:** Explicaremos os fundamentos do Docker utilizando o formato textual e interativo do SWIRL.
2.  **Exemplos Práticos (Externos):** Forneceremos exemplos claros de comandos Docker que você deverá executar **manualmente** no seu terminal.
3.  **Validação do Aprendizado:** Faremos perguntas no SWIRL sobre os conceitos apresentados e sobre os resultados esperados ao executar os comandos Docker no terminal.

## Estrutura do Curso "Introdução ao Docker para Usuários de R"

O curso está organizado nas seguintes lições:

**Lição 1: O que é Docker e por que usar?**

* Problemas que o Docker soluciona: dependências, ambientes consistentes, implantação.
* Analogias para facilitar a compreensão: contêineres como caixas, imagens como moldes.
* Vantagens do Docker no contexto da ciência de dados e do R.

**Lição 2: Conceitos Fundamentais do Docker**

* **Imagens:** Definição e processo de criação (Dockerfiles).
* **Contêineres:** Definição, criação a partir de imagens e ciclo de vida.
* **Dockerfiles:** Introdução à estrutura básica (FROM, RUN, COPY, WORKDIR, CMD/ENTRYPOINT).
* **Docker Hub:** O que é e como utilizá-lo para encontrar imagens prontas.

**Lição 3: Instalando o Docker (Instruções Genéricas)**

* Observação sobre a variação da instalação por sistema operacional.
* Links para a documentação oficial do Docker (Linux, macOS, Windows).
* Instrução para verificar a instalação (`docker --version`).

**Lição 4: Trabalhando com Imagens**

* `docker pull`: Baixando imagens do Docker Hub.
* `docker images`: Listando imagens locais.
* `docker rmi`: Removendo imagens.

**Lição 5: Trabalhando com Contêineres**

* `docker run`: Criando e iniciando contêineres.
* Opções importantes do `docker run`: `-d`, `-p`, `-v`, `-name`.
* `docker ps`: Listando contêineres em execução.
* `docker ps -a`: Listando todos os contêineres (ativos e inativos).
* `docker stop <container_id_or_name>`: Parando contêineres.
* `docker start <container_id_or_name>`: Iniciando contêineres parados.
* `docker rm <container_id_or_name>`: Removendo contêineres.

**Lição 6: Docker e R (Exemplos)**

* Utilização do Docker para executar aplicações R de forma consistente.
* Exemplo de um Dockerfile para executar um script R.
* Explicação detalhada de cada linha do Dockerfile.
* Instruções para criar um script R simples (`print("Olá do Docker com R!")`).
* Construção da imagem (`docker build -t r-app .` - execução no terminal).
* Execução do contêiner (`docker run r-app` - execução no terminal).
* Perguntas no SWIRL sobre o processo e os resultados.

**Implementação Interativa no SWIRL**

Em cada lição, o SWIRL será utilizado para:

* Apresentar informações e conceitos de forma clara e concisa.
* Formular perguntas de múltipla escolha e de resposta curta para testar sua compreensão.
* **Instruir explicitamente quando e como executar comandos Docker no seu terminal (fora do R).**
* **Questionar sobre os resultados e as observações obtidas ao executar esses comandos no terminal.**

**Exemplo de Interação no SWIRL:**

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

**Desafios e Considerações**

- **Dependência do Ambiente Externo:** O aprendizado prático depende da instalação e do correto funcionamento do Docker no sistema operacional do usuário. O SWIRL não tem mecanismos para verificar isso diretamente.

- **Interatividade Limitada:** A interação com o ambiente Docker real ocorre fora do SWIRL. A interatividade dentro do SWIRL se concentra em perguntas sobre os resultados esperados.

- **Clareza das Instruções:** Buscamos fornecer instruções o mais claras possível sobre quando e o que executar no terminal para minimizar confusões.

**Conclusão**

Apesar das limitações inerentes ao uso do SWIRL para ensinar uma tecnologia que opera no nível do sistema operacional como o Docker, esperamos oferecer ao programador R uma introdução valiosa com este curso. Ao combinar a estrutura de aprendizado interativo do SWIRL com a prática manual de comandos Docker no terminal, também esperamos fornecer aos usuários de R um ponto de partida sólido para explorar o mundo da conteinerização.