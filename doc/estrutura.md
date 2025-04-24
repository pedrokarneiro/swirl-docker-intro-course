Para que o SWIRL reconheça nosso curso e suas lições, precisamos seguir uma estrutura de diretórios específica. Vamos imaginar que você criou um diretório chamado `swirl-docker-intro-course` onde você quer armazenar os arquivos do nosso curso. Dentro desse diretório, a estrutura seria a seguinte:

```
SWIRL-docker-intro-course/
├── course.yaml        # Arquivo principal de metadados do curso
└── lessons/
    ├── lesson1.yaml   # Lição 1: O que é Docker e por que usar?
    ├── lesson2.yaml   # Lição 2: Conceitos Fundamentais do Docker
    ├── lesson3.yaml   # Lição 3: Instalando o Docker (Instruções Genéricas)
    ├── lesson4.yaml   # Lição 4: Trabalhando com Imagens
    ├── lesson5.yaml   # Lição 5: Trabalhando com Contêineres
    └── lesson6.yaml   # Lição 6: Docker e R (Exemplos)
```

**Detalhes dos arquivos:**

1.  **`course.yaml`:** Este é o arquivo que contém os metadados do nosso curso, como o nome do curso que aparecerá no menu principal do SWIRL e a ordem das lições. O conteúdo deste arquivo é:

    ```yaml
    name: "Introdução ao Docker para Programadores R"
    lessons:
    - lesson1.yaml
    - lesson2.yaml
    - lesson3.yaml
    - lesson4.yaml
    - lesson5.yaml
    - lesson6.yaml
    ```

    Aqui, `name` define o título do curso no menu inicial do SWIRL, e `lessons` é uma lista dos arquivos `.yaml` que definem cada lição, na ordem em que devem aparecer no menu do curso.

2.  **`lessons/` directory:** Este diretório contém os arquivos `.yaml` para cada uma das nossas lições. Cada arquivo (por exemplo, `lesson1.yaml`) contém o código SWIRL que definimos para aquela lição específica (as informações, as perguntas, as respostas, etc.).

**Como o menu aparece no SWIRL:**

1.  **Ao iniciar o SWIRL (`swirl()`):** O usuário vê uma lista de cursos instalados. Por exemplo, o nosso curso apareceria como um dos itens listados ao lado do seu respectivo número:

    ```
    ...
    1: R Programming
    2: Data Analysis
    3: Introdução ao Docker para Programadores R
    ...
    ```

    O número ao lado do nome do curso pode variar dependendo de outros cursos instalados. O usuário digita o número correspondente a "Introdução ao Docker para Programadores R" e pressiona Enter para selecionar o nosso curso.

2.  **Ao selecionar o nosso curso:** O SWIRL então lê o arquivo `course.yaml` dentro do diretório do nosso curso e exibe o menu das lições na ordem especificada:

    ```
    Bem-vindo ao curso: Introdução ao Docker para Programadores R

    Por favor, selecione uma lição ou digite 0 para sair.

    1: O que é Docker e por que usar?
    2: Conceitos Fundamentais do Docker
    3: Instalando o Docker (Instruções Genéricas)
    4: Trabalhando com Imagens
    5: Trabalhando com Contêineres
    6: Docker e R (Exemplos)
    ```

    O usuário então digita o número da lição que deseja fazer (por exemplo, `1` para começar pela primeira lição) e pressiona Enter. O SWIRL carrega o conteúdo de `lesson1.yaml` e inicia a lição.

**A estrutura de diretórios com o arquivo `course.yaml` e os arquivos `.yaml` das lições dentro de um subdiretório `lessons/` é o que define o menu e a organização do nosso curso no ambiente SWIRL.**

Para que o SWIRL encontre o nosso curso, o diretório `swirl-docker-intro-course` (ou o nome que escolhermos) precisa ser colocado em um local onde o SWIRL procura por cursos instalados. Geralmente, isso envolve um diretório dentro da biblioteca do R do usuário, mas o SWIRL também oferece funções para instalar cursos a partir de arquivos zipados ou URLs.
