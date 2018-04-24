#Front Vendors

Criamos um projeto chamado Front Vendors, lá colocamos todos os códigos que são comuns para todas as lojas. O objetivo é tirar todo o conteúdo genérico das lojas para ali, assim não teremos repetição de código.
Todas as lojas importam no package.json o "front-vendors", no caso dos scripts apenas precisamos escolher em que tela será importado o código.

Encontrei aqui a melhor forma de melhor os códigos do ecommerce, pois todo o conteúdo é importado na forma de plugin, logo
são módulos independentes das lojas, e poderei aplicar boas práticas que atualmente não usamos nos códigos legados que
trabalhamos.

### Lista de boas práticas que serão aplicadas:
- **Mobile First:**
  - Será aplicado primeiro o CSS que servirá ao mobile e depois sobrescrito conforme aumenta a resolução.
  - Se usado imagens háverá uma imagem para mobile de menor tamanho.
  - Em JS é usado a verificação ```isMobile()``` e aí sobrescrito novos valores ao objeto, da forma mais eficiente
  não haverá sobrescrita e sim adiciona um valor ou outro.
- **Class:**
  - Aos poucos estamos substituindo "Backbone.js" por classes Ecma6 graças ao Babel.
  - **Atributos privados:** com JS pode-se criar atributos/métodos privados colocando-os no mesmo escopo da classe, porém
  fora dela.
  - **Getters/Setters:** os atributos que podem ser alterados ou obtidos externamente e possuem alguma regra para isto podem
  ser protegidos com ```get``` e ```set```, assim quando houver a acesso ao atributo o método é que será chamado.
- **Documentar:**
  - Com Annotation ou no "README.md" podemos descrever cada componente e como utilizá-lo.


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

## Tooltip
Tooltip é a caixa de dicas que situacionalmente aparece e é usado em quase todas as páginas. O código dele foi melhorado a cada loja criada, utilizei a versão final criada e fiz algumas adaptações para poder reproduzir em todas as lojas igualmente. Este novo Tooltip deve ter todo seu javascript e também parte do CSS como genérico.
Uma amostra de como estava em uma das lojas e como será o novo, (apenas o template, sem todos os métodos envolvidos):

**antigo:**
```
creditCardValue1: _.template(`
    <div class="tooltip-credit-card-value-1" data-js="tooltip-content">
        <div class="tooltip-content">
            <div class="tooltip-inner">
            <div class="tooltip-arrow"></div>
            <div class="tooltip-title">
                <span>IMPORTANTE</span>
            </div>
            <div class="tooltip-msg">
                <p>
                    O valor do segundo cartão será calculado automaticamente a partir do valor escolhido para este cartão e do valor total do pedido.
                </p>
            </div>
            </div>
        </div>
    </div>`
),
```

**novo:**
```
const renderTooltip = ({
    id, title, message, position, after, className, align
}) => {
    const $tooltip = $(`
    <div id="${id}" class="tooltip ${className} js-tooltip tooltip-show tooltip--${position} tooltip--${align}">
        <div class="tooltip__content">
            ${title && `<h3 class="tooltip__title">${title}</h3>`}
            ${message && `<div class="tooltip__message">${message}</div>`}
        </div>
    </div>
    `);
    if (after) $tooltip.insertAfter(after);
};
```

Podemos ver que a versão antiga possuia vários valores fixados no template, logo precisava de 1 para cada tooltip.
Na nova versão que peguei na útltima loja criada adicionei o "align" para diminuir a quantidade de CSS específico e adicionei também o "className" para enviar 1 ou mais classes.



