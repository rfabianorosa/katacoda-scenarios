Alternando o editor vi para o editor vim.

Existe diversas formas de realizar esta tarefa, a que seguirei simplesmente será remover o binário do editor vi e colocarmos um link simbólico para o editor vim.

## Solução número 01

Remover o editor vi: 

`sudo rm -f /usr/bin/vi`{{execute}}

Adicionando o link simbólico do novo editor (vim): 

`sudo ln -s /usr/bin/vim /usr/bin/vi`{{execute}}

    obs: o Comando ln criará um link simbólico do comando vim para o vi é como se fosse um atalho, para visualizar a ligação pode-se utilizar o comando ls -l
