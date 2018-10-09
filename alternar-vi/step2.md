Alternando o editor vi para o editor vim.

Existe diversas formas de realizar esta tarefa, a que seguirei simplesmente será remover o binário do editor vi e colocarmos um link simbólico para o editor vim.

## Solução número 01

Remover o editor vi: 

`sudo rm -f /usr/bin/vi`{{execute}}

Adicionando o link simbólico do novo editor (vim): 

`sudo ln -s /usr/bin/vim /usr/bin/vi`{{execute}}

    obs: o Comando ln criará um link simbólico do comando vim para o vi é como se fosse um atalho, para visualizar a ligação pode-se utilizar o comando ls -l

## Solução número 02

Geralmente após a instalação do pacote vim o mesmo já fica disponível para utilização no lugar do vi, para confirmar basta verificar o link no /etc/alternatives, onde deve respeitar a seguinte ordem:

    /usr/bin/vi -> /etc/alternatives/vi
    /etc/alternatives/vi -> /usr/bin/vim.basic

Ou seja o arquivo binário **/usr/bin/vi** é um link simbólico para o arquivo **/etc/alternatives/vi** e também é um link apontando para o binário **/usr/bin/vim.basic**. Desta forma quando atualizar o sistema operacional ou houver uma reinstalação de pacotes não será substituído o link do alternatives.

Para recriar o link basta seguir os seguintes passos:

`sudo rm -f /etc/alternatives/vi`
`sudo ln -s /usr/bin/vim.basic /etc/alternatives/vi`

Pronto está feito.

lembrando:

| Comando | Descrição |
|---------|-----------|
| rm | remover um arquivo | 
| -f | forçar a remoção sem aviso prévio |

| Comando | Descrição |
|---------|-----------|
| ln | Criar link | 
| -s | link simbólico |
| /usr/bin/vim.basic | Arquivo Origem |
| /etc/alternatives/vi | Link Destino |
