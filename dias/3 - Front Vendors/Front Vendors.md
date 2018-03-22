#Front Vendors

Criamos um projeto chamado Front Vendors, lá colocamos todos os códigos que são comuns para todas as lojas. O objetivo é tirar todo o conteúdo genérico das lojas para ali, assim não teremos repetição de código.
Todas as lojas importam no package.json o "front-vendors", no caso dos scripts apenas precisamos escolher em que tela será importado o código.

## FranchiseePopUp
As lojas Arezzo, Anacapri, Fiever e Schutz adotaram uma nova tela de "Seja um franqueado", resolvi tirar o conteúdo repetido de duas páginas que já tinham sido feitas e adicionei o código ao front vendors.
O script colocado lá tem escuta se há clique na classe "open-pop-up".
Para carregamento mais rápido da primeira tela retirei o "import" dos "genéricos" (colocamos aqui tudo que usamos em todas as telas), pois só precisaremos na "Seja um franqueado".
