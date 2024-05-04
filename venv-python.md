<!--
title: 'venv-python.md'
author: 'Elias Albuquerque'
created: '2024-05-04'
update: '2024-05-04'
-->




# Criar um ambiente virtual (venv) em Python:

1. Abra um terminal.

2. Navegue até o diretório onde você deseja criar o ambiente virtual. Você pode 
   fazer isso usando o comando `cd`. Por exemplo, se você quiser criar o 
   ambiente virtual no diretório `meu_projeto`, você pode usar o comando:

   ```terminal-windows
   cd \caminho\para\meu_projeto
   ``` 

3. Uma vez no diretório correto, você pode criar o ambiente virtual usando o 
   módulo `venv` do Python. O comando é o seguinte:

   ```terminal-windows
   python -m venv nome_do_ambiente_virtual
   ```

   Substitua `nome_do_ambiente_virtual` pelo nome que você deseja dar ao seu 
   ambiente virtual.

   Use `pyhon3` no Linux ou MacOS.

4. Agora você tem um ambiente virtual criado! Para começar a usá-lo, você 
   precisa ativá-lo. No Windows, você pode fazer isso com o comando:

   ```terminal-windows
   nome_do_ambiente_virtual\Scripts\activate
   ```

   No Unix ou MacOS, use:

   ```terminal
   source nome_do_ambiente_virtual/bin/activate
   ```

5. Com o ambiente virtual ativado, você pode instalar pacotes Python nele 
   usando o `pip`. Esses pacotes serão isolados do restante do seu sistema.
