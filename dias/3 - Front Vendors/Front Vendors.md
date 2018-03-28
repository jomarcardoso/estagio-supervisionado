#Front Vendors

Criamos um projeto chamado Front Vendors, lá colocamos todos os códigos que são comuns para todas as lojas. O objetivo é tirar todo o conteúdo genérico das lojas para ali, assim não teremos repetição de código.
Todas as lojas importam no package.json o "front-vendors", no caso dos scripts apenas precisamos escolher em que tela será importado o código.

## FranchiseePopUp
As lojas Arezzo, Anacapri, Fiever e Schutz adotaram uma nova tela de "Seja um franqueado", resolvi tirar o conteúdo repetido de duas páginas que já tinham sido feitas e adicionei o código ao front vendors.
O script colocado lá tem escuta se há clique na classe "open-pop-up".
Para carregamento mais rápido da primeira tela retirei o "import" dos "genéricos" (colocamos aqui tudo que usamos em todas as telas), pois só precisaremos na "Seja um franqueado".


## Browser
Métodos para verificação de browser e sistema operacional, alguns desses são executados ao carregar cada página.
Em algumas lojas essa classe estava em um arquivo separado, em outras estava no com o "utils.js".
Quando instanciado em algumas lojas ele adicionava uma classe na tag "html" com as siglas do browser + OS, noutras colocava duas classes, browser-{browserName} + os-{osType}, resolvi isso adicionando as três classes. No futuro podemos padronizar isso.

## Modal
Modal foi simples, apenas extraí das lojas e chamei a dependência, não tinha diferença alguma.

## Geolocation
Também não possui diferenças de uma loja para outra.
Temos 2 lojas que são apenas online e não precisam dessa classe, mas como a criação de uma loja herda os códigos de outra a Outstore tinha traços de código de geolocalização que removi.

## LazyLoad
Classe usada para atrasar o carregamento de imagens para diminuir o carregamento inicial.
Apenas na loja Arezzo precisei atirar os seletores de elementos DOM, fui nos arquivos JSP que possuiam essas "class" e alterei o nome para o padrão das outras lojas.