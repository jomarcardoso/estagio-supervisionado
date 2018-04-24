# Hotsites Template

A Tarefa aqui constitui-se em melhorar a plataforma para desenvolvimento de dos hotsites.

### NECESSIDADES:

## Prazo
O prazo é sempre curto, então tudo que eu puder deixar adiantado é lucro. O que será feito:
 - **Fonts:** arquivos fonts e css de fonts para todas as marcas;
 - **Resets CSS**;
 - **Criar um Framework CSS:** vi a necessidade, pois alguns hotsites são muito simples e parecidos, logo poderia só adicionar classes no HTML e mal mexer no CSS;
 - **Mixin para Grid-layout:** os layouts estão cada vez mais complexos e preparar um mixin compatível com internet explorer para gerar grid pode facilitar para os colegas que não usa essa tecnologia.

 ## Esforço repetido
 O intuito dos sites promocionais quase sempre são os mesmo: fazer os cliente se inscrever para receber emails, mostrar uma promoção que está por vir, mostrar contagem regressiva para um evento... Esses "mecanismos" javascript não precisam ser recriados, porém é trabalhoso ir nos outros hotsites pegar isso isolado e justar para o atual, para isso resolvi documentar todos esses:
 - **Contador de contagem regressiva**;
 - **Carrossel slick**;
 - **Registro de email**;
 - **Rolagem suave:** efeito que leva para uma âncora no site de forma suave;

### Rolagem suave
Achei uma solução fácil no stackoverflow que usa jquery, apenas adicionei o mecânismo de componentização padrão que usamos.

**Horas trabalhadas:** 1

### Registro de email:
Fiz aproveitamento dos que já tinham, removi tudo que era específico da página onde peguei. Criei o componente e adicionei um "start" para esse componente, que constitui em enviar o id do formulário e o nome da campanha.

**Horas trabalhadas:** 2.5

### Contador de contagem regressiva
Fiz aproveitamento dos que já tinham, removi tudo que era específico da página onde peguei. Criei o componente e adicionei um "start" para esse componente, que constitui em adicionar o tempo final, e o id onde será adicionado os dados do contador.

**Horas trabalhadas:** 1.5

### Mixin para Grid-layout
Criei 4 mixins para grid layout que são, a maior complexidade estava em conhecer a sintaxe do SASS e no cálculo dos tamanhos que envolvia uma lógica de pegar todos os tamanhos e transformar em porcentagem.
- altura das linhas
- largura das colunas
- espaço horizonta da célula
- espaço vertical da célula

Incluí na documentação a forma de uso e um exemplo.

**Horas trabalhadas:** 4

### Fonts
Inclui os @font-face de todas as marcas para não precisar procurar a cada vez que for criar um novo hotsite.

**Horas trabalhadas:** 2