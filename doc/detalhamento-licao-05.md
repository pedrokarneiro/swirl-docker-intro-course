**Lição 5: Trabalhando com Contêineres**

Esta lição será bem prática, com vários comandos para o usuário executar no terminal.

```R
# Lição 5: Trabalhando com Contêineres

lesson_name("Introdução ao Docker para Programadores R - Lição 5")

info("Chegou a hora de colocar a mão na massa e trabalhar com contêineres! Lembre-se que contêineres são instâncias em execução de imagens Docker.")

info("O comando fundamental para criar e iniciar um contêiner é `docker run`.")

info("Abra o seu terminal e execute o seguinte comando:")
code_output("docker run ubuntu:latest echo \"Olá do contêiner\"")
readline("Pressione Enter depois de executar o comando...")

question("O que aconteceu quando você executou o comando `docker run ubuntu:latest echo \"Olá do contêiner\"`?")
answer("Nada, o Docker apenas baixou a imagem.")
answer("Um novo contêiner foi criado e executou o comando `echo \"Olá do contêiner\"`, imprimindo a mensagem no terminal.")
answer("Um erro ocorreu porque não especificamos um nome para o contêiner.")
answer("O Docker abriu um shell interativo dentro do contêiner.")
correct_answer("Um novo contêiner foi criado e executou o comando `echo \"Olá do contêiner\"`, imprimindo a mensagem no terminal.")
explanation("Correto! O Docker baixou a imagem `ubuntu:latest` (se ainda não estava localmente), criou um contêiner a partir dela, executou o comando `echo \"Olá do contêiner\"` dentro do contêiner e depois o contêiner parou.")

info("Agora, execute este outro comando:")
code_output("docker run -it ubuntu:latest /bin/bash")
readline("Pressione Enter depois de executar o comando...")

question("O que aconteceu de diferente desta vez ao executar `docker run -it ubuntu:latest /bin/bash`?")
answer("A mesma coisa que o comando anterior.")
answer("Você entrou em um shell interativo dentro do contêiner Ubuntu. O prompt deve ter mudado.")
answer("O Docker tentou executar o arquivo `/bin/bash` no seu computador local.")
answer("O contêiner foi iniciado em segundo plano.")
correct_answer("Você entrou em um shell interativo dentro do contêiner Ubuntu. O prompt deve ter mudado.")
explanation("Exatamente! As opções `-it` permitem uma sessão interativa com o contêiner, conectando seu terminal à linha de comando dentro do contêiner.")

info("Para sair deste shell interativo, digite `exit` no terminal do contêiner e pressione Enter.")
readline("Pressione Enter depois de sair do shell do contêiner...")

info("O comando `docker run` possui várias opções poderosas. Vamos explorar algumas das mais importantes:")

info("- `-d`: Executa o contêiner em segundo plano (detached). Você não verá a saída do processo diretamente no seu terminal.")
info("- `-p <porta_do_host>:<porta_do_contêiner>`: Mapeia uma porta do seu computador (host) para uma porta dentro do contêiner. Isso é útil para acessar serviços rodando no contêiner (como um servidor web).")
info("- `-v <caminho_no_host>:<caminho_no_contêiner>`: Cria um volume compartilhado entre o seu computador e o contêiner. Isso permite que os dados persistam mesmo após o contêiner ser removido e é útil para compartilhar arquivos.")
info("- `-name <nome_do_contêiner>`: Atribui um nome amigável ao seu contêiner, em vez do nome aleatório gerado pelo Docker.")

info("Execute o seguinte comando para iniciar um contêiner Ubuntu em segundo plano, nomeado 'meu_ubuntu':")
code_output("docker run -d --name meu_ubuntu ubuntu:latest sleep infinity")
readline("Pressione Enter depois de executar o comando...")

question("O que a opção `-d` fez ao executar o contêiner?")
answer("Exibiu informações detalhadas sobre a imagem Ubuntu.")
answer("Executou o contêiner em primeiro plano, mostrando a saída do comando `sleep infinity`.")
answer("Executou o contêiner em segundo plano, sem manter o seu terminal ocupado.")
answer("Removeu o contêiner após a sua criação.")
correct_answer("Executou o contêiner em segundo plano, sem manter o seu terminal ocupado.")
explanation("Correto! A opção `-d` é essencial para executar serviços em contêineres sem bloquear o seu terminal.")

info("Agora, vamos ver os contêineres que estão em execução. Execute o seguinte comando:")
code_output("docker ps")
readline("Pressione Enter depois de executar o comando...")

question("Na saída do comando `docker ps`, quais informações são exibidas sobre o contêiner 'meu_ubuntu'?")
answer("Apenas o nome e o ID do contêiner.")
answer("O ID do contêiner, a imagem usada, o comando em execução, o tempo de criação, o status, as portas mapeadas (se houver) e o nome.")
answer("Apenas o status ('Up' ou 'Exited').")
answer("Uma lista de todas as imagens disponíveis.")
correct_answer("O ID do contêiner, a imagem usada, o comando em execução, o tempo de criação, o status, as portas mapeadas (se houver) e o nome.")
explanation("Isso mesmo! `docker ps` fornece informações importantes sobre os contêineres em execução.")

info("Para ver todos os contêineres, incluindo aqueles que foram parados, use o comando:")
code_output("docker ps -a")
readline("Pressione Enter depois de executar o comando...")

question("Qual a principal diferença entre a saída de `docker ps` e `docker ps -a`?")
answer("`docker ps -a` mostra mais detalhes sobre os contêineres em execução.")
answer("`docker ps` mostra apenas os contêineres parados, enquanto `docker ps -a` mostra os em execução.")
answer("`docker ps -a` lista todos os contêineres (em execução e parados), enquanto `docker ps` lista apenas os em execução.")
answer("Não há diferença entre os dois comandos.")
correct_answer("`docker ps -a` lista todos os contêineres (em execução e parados), enquanto `docker ps` lista apenas os em execução.")
explanation("Correto! O `-a` significa 'all' (todos).")

info("Para parar um contêiner em execução, usamos o comando `docker stop` seguido pelo ID ou nome do contêiner. Vamos parar o contêiner 'meu_ubuntu':")
code_output("docker stop meu_ubuntu")
readline("Pressione Enter depois de executar o comando...")

question("Depois de executar `docker stop meu_ubuntu`, qual deve ser o status do contêiner quando você executar `docker ps` novamente?")
answer("'Up'")
answer("'Exited'")
answer("'Created'")
answer("Ele não aparecerá na lista.")
correct_answer("'Exited'")
explanation("Exatamente! O comando `docker stop` envia um sinal para o contêiner parar seus processos.")

info("Para iniciar um contêiner que foi parado, usamos o comando `docker start` seguido pelo ID ou nome do contêiner. Vamos iniciar 'meu_ubuntu' novamente:")
code_output("docker start meu_ubuntu")
readline("Pressione Enter depois de executar o comando...")

question("Após executar `docker start meu_ubuntu`, qual deve ser o status do contêiner quando você executar `docker ps`?")
answer("'Exited'")
answer("'Created'")
answer("'Running' ou 'Up'")
answer("Ele não aparecerá na lista.")
correct_answer("'Running' ou 'Up'")
explanation("Correto! O comando `docker start` reinicia os processos dentro do contêiner parado.")

info("Finalmente, para remover um contêiner (que deve estar parado), usamos o comando `docker rm` seguido pelo ID ou nome do contêiner. **Cuidado: a remoção de um contêiner é irreversível e você perderá quaisquer dados que não estejam em volumes.**")

info("Vamos remover o contêiner 'meu_ubuntu':")
code_output("docker rm meu_ubuntu")
readline("Pressione Enter depois de executar o comando...")

question("Qual a principal diferença entre parar (`docker stop`) e remover (`docker rm`) um contêiner?")
answer("Parar um contêiner exclui todos os seus dados, enquanto remover apenas o desativa.")
answer("Parar um contêiner o desativa temporariamente, permitindo reiniciá-lo, enquanto remover o exclui permanentemente.")
answer("Não há diferença significativa entre os dois comandos.")
answer("`docker stop` remove o contêiner, e `docker rm` remove a imagem associada.")
correct_answer("Parar um contêiner o desativa temporariamente, permitindo reiniciá-lo, enquanto remover o exclui permanentemente.")
explanation("Isso mesmo! `docker rm` exclui o contêiner e seus dados (a menos que estejam em volumes).")

info("Parabéns! Você aprendeu os comandos básicos para trabalhar com contêineres Docker: criar, iniciar, listar, parar e remover. Na próxima lição, veremos como o Docker pode ser usado especificamente com aplicações R.")

# Fim da Lição 5
```

Esta lição é bem densa e cobre os principais comandos de gerenciamento de contêineres. A interação com o terminal é fundamental aqui para que o usuário veja os resultados dos comandos em tempo real.
