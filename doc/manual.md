# Manual

## Passo-a-Passo para Instalação e Primeira Execução do Curso no SWIRL

### Introdução ao Docker para Programadores R

Este guia assume que você já tem o **R** e o pacote **swirl** instalados no seu computador. Se ainda não os tem, siga as instruções de instalação para R em [https://cran.r-project.org/](https://cran.r-project.org/) e para o swirl dentro do R, execute `install.packages("swirl")`.

**Passo 1: Instalar o pacote `swirlify` (necessário para instalar cursos do GitHub)**

O pacote `swirlify` facilita a instalação de cursos Swirl diretamente de repositórios GitHub. Abra o R (ou RStudio) e execute o seguinte comando:

```R
install.packages("swirlify")
```

**Passo 2: Carregar o pacote `swirlify`**

Após a instalação, carregue o pacote `swirlify` na sua sessão R:

```R
library(swirlify)
```

**Passo 3: Instalar o curso do GitHub**

Agora, use a função `install_course_github()` do pacote `swirlify` para instalar o curso diretamente do GitHub. Execute o seguinte comando, substituindo a URL do repositório:

```R
install_course_github("pedrokarneiro/swirl-docker-intro-course", course_name = "Introducao ao Docker para Programadores R")
```

* `"pedrokarneiro/swirl-docker-intro-course"`: É o nome do usuário e o nome do repositório no GitHub, no formato `usuario/repositorio`.
* `course_name = "Introducao ao Docker para Programadores R"`: Define o nome que o curso terá dentro do Swirl. Este nome aparecerá no menu de seleção de cursos.

O R irá baixar os arquivos do curso do GitHub e instalá-los na sua biblioteca Swirl local. Você verá mensagens no console indicando o progresso da instalação.

**Passo 4: Iniciar o Swirl**

Após a instalação bem-sucedida, inicie o Swirl na sua sessão R:

```R
library(swirl)
swirl()
```

**Passo 5: Selecionar o curso "Introducao ao Docker para Programadores R"**

O Swirl irá apresentar um menu com os cursos instalados. Procure por "Introducao ao Docker para Programadores R" na lista e digite o número correspondente para selecioná-lo. Pressione Enter.

**Passo 6: Selecionar a primeira lição**

Após selecionar o curso, o Swirl mostrará um menu com as lições disponíveis:

```
Bem-vindo ao curso: Introducao ao Docker para Programadores R

Por favor, selecione uma lição ou digite 0 para sair.

1: O que é Docker e por que usar?
2: Conceitos Fundamentais do Docker
3: Instalando o Docker (Instruções Genéricas)
4: Trabalhando com Imagens
5: Trabalhando com Contêineres
6: Docker e R (Exemplos)
```

Para começar, digite `1` e pressione Enter para iniciar a primeira lição: "O que é Docker e por que usar?".

**Próximos passos:**

Siga as instruções e responda às perguntas dentro do ambiente Swirl. O curso irá guiá-lo pelos conceitos básicos do Docker, com instruções para executar comandos no seu terminal quando necessário e perguntas para verificar sua compreensão.

Lembre-se que algumas lições exigirão que você execute comandos no seu terminal (fora do R/Swirl) e depois responda perguntas sobre o resultado dentro do Swirl.

Aproveite o aprendizado! Se encontrar algum problema durante a instalação ou execução, verifique as mensagens de erro no console do R ou procure por soluções online específicas para o Swirl e instalação de cursos do GitHub.

**Feedback, Erros e Melhorias**

Se você encontrar algum erro, tiver sugestões de melhoria ou qualquer outro feedback sobre este curso, por favor, entre em contato comigo. A melhor maneira de fazer isso é através do repositório no GitHub: [https://github.com/pedrokarneiro/swirl-docker-intro-course](https://github.com/pedrokarneiro/swirl-docker-intro-course).

Sinta-se à vontade para abrir uma Issue relatando o problema ou sua sugestão. Se você se sentir à vontade para contribuir diretamente, ficarei muito feliz em receber Pull Requests com correções ou novas ideias para aprimorar este material.

A colaboração da comunidade é fundamental para tornar este curso ainda melhor e mais útil para outros programadores R que desejam aprender sobre Docker. Sua contribuição é muito bem-vinda!