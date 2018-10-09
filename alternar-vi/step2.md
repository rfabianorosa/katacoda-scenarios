Alternando o editor vi para o editor vim.

Existe diversas formas de realizar esta tarefa, a que seguirei simplesmente será remover o binário do editor vi e colocarmos um link simbólico para o editor vim.

## Solução número 01

Remover o editor vi: **command**

`sudo rm -f /usr/bin/vi`{{execute}}

Adicionando o link simbólico do novo editor (vim): **command**

`sudo ln -s /usr/bin/vim /usr/vin/vi`{{execute}}

 
## Solução número 02
