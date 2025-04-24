**Lição 1: O que é Docker e por que usar?**

Nesta lição, nosso objetivo é introduzir o conceito de Docker e motivar seu uso, especialmente no contexto do trabalho com R. Podemos usar uma combinação de texto informativo e perguntas conceituais.

```R
# Lição 1: O que é Docker e por que usar?

lesson_name("Introdução ao Docker para Programadores R - Lição 1")

info("Bem-vindo ao curso 'Introdução ao Docker para Programadores R'! Nesta primeira lição, vamos entender o que é o Docker e por que ele se tornou uma ferramenta tão importante no mundo do desenvolvimento de software e, cada vez mais, na ciência de dados.")

info("Imagine que você desenvolveu um projeto incrível em R, com várias dependências de pacotes específicos e talvez até uma versão particular do R. Agora, você precisa compartilhar esse projeto com um colega ou implantá-lo em um servidor. Quais desafios você pode enfrentar?")

question("Qual dos seguintes problemas é mais provável de acontecer ao tentar executar seu projeto R em um computador diferente?")
answer("O código R terá erros de sintaxe.")
answer("A estrutura de diretórios do projeto será diferente.")
answer("O computador de destino não terá todos os pacotes R necessários ou terá versões diferentes.")
answer("A função principal do seu script R mudará de nome.")
correct_answer("O computador de destino não terá todos os pacotes R necessários ou terá versões diferentes.")
explanation("Exatamente! A falta ou versões incompatíveis de pacotes R são problemas comuns ao compartilhar ou implantar projetos.")

info("O Docker surge como uma solução elegante para esses problemas. Ele permite 'empacotar' seu aplicativo R (juntamente com todas as suas dependências, bibliotecas do sistema e configurações) em uma unidade isolada chamada **contêiner**.")

info("Pense em um contêiner como uma caixa padronizada que contém tudo o que seu aplicativo precisa para rodar, garantindo que ele funcione da mesma forma em qualquer ambiente que suporte Docker.")

question("Qual a principal vantagem de usar contêineres Docker para seus projetos R?")
answer("Eles tornam o código R mais rápido.")
answer("Eles garantem que o ambiente de execução seja consistente em diferentes máquinas.")
answer("Eles reduzem o tamanho dos seus arquivos de código R.")
answer("Eles permitem usar linguagens de programação diferentes dentro do mesmo projeto.")
correct_answer("Eles garantem que o ambiente de execução seja consistente em diferentes máquinas.")
explanation("Correto! A consistência do ambiente é um dos maiores benefícios do Docker.")

info("As 'receitas' para criar esses contêineres são chamadas de **imagens Docker**. Uma imagem é um modelo estático que define o ambiente e o software dentro do contêiner.")

info("Podemos pensar em uma imagem como um molde e em um contêiner como algo que é criado a partir desse molde. Você pode criar vários contêineres idênticos a partir da mesma imagem.")

question("Qual a relação entre uma imagem Docker e um contêiner Docker?")
answer("Um contêiner é usado para criar uma imagem.")
answer("Uma imagem é uma instância em execução de um contêiner.")
answer("Uma imagem é um modelo para criar um ou mais contêineres.")
answer("Não há relação direta entre imagens e contêineres.")
correct_answer("Uma imagem é um modelo para criar um ou mais contêineres.")
explanation("Isso mesmo! A imagem serve como base para criar os contêineres.")

info("No contexto da ciência de dados e do R, o Docker pode ser extremamente útil para:")
info("- Garantir a **reprodutibilidade** de análises, pois o ambiente é sempre o mesmo.")
info("- Facilitar a **implantação** de aplicações Shiny ou APIs construídas em R.")
info("- Isolar diferentes projetos com **dependências conflitantes**.")
info("- Criar **ambientes de desenvolvimento consistentes** para toda a equipe.")

info("Na próxima lição, vamos mergulhar nos conceitos fundamentais do Docker, como imagens e Dockerfiles. Continue!")

# Fim da Lição 1
```

