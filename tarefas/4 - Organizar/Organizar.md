# Refatorar Códigos
[retornar](../../README.md)

Além de refatorar os códigos pretendo documentar práticas de limpeza periódica.

## Limpeza e documentação
Com as modificações muitos arquivos, códigos e trechos de códigos ficam para trás. Uma limpeza periódica para retirar esses é necessário. Abaixo uma lista de pontos comuns:
Todos os itens abaixo serão executados e documentados para futuras limpezas.
- Remover _class=""_
- Remover _id=""_
- Remover _console.log(_ desnecessários

## Resolução de imagens
Verificando o network das lojas descobrirei o tamanho das imagens carregadas e se correspondem a sua resolução. Se houver exagero vou corrigir.

### Imagens do Instagram em Anacapri
Na home de Anacapri temos um seção das últimas fotos colocas no seu instagram, verifiquei que a maior imagem da página (+90kB) está ali e que o container força a imagem a um tamanho de 330px X 330px, logo é um exagero uma imagem deste tamanho com esta resolução.
Encontrei o script que importa elas, há um atributo: ```resolution: "standard_resolution"``` e troquei para ```resolution: "low_resolution"``` a imagem de "low resolution" tem 306px, se isso não interferir muito na qualidade poderá ser usada.
Após aplicado a imagem "problemática" passou a ter 27kB e as demais também diminuiram seu tamanho.

### Trocar @include por @extend
Aqui usamos SASS para compilar o CSS e as vezes por falta de conhecimento ou costume usam os mixins para uma determinada classe ter um comportamento, mas em muitos casos o "@extend" é mais eficiente, pois não gera repetição de código no ".css".

### Pastas do projeto
As pastas de JS/CSS da lojas não seguem um padrão, alguns códigos estão dentro de "/assets", outros dentro de "/src"

[retornar](../../README.md)