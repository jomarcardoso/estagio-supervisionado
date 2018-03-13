# HOTSITE - FESTIVAL SHOP (SHUTZ)

Recebido layout do novo Hotsite promocional da marca Schutz.

![HOTSITE](arquivos/hotsite-fs-desktop.jpg)

## Estruturando

Pelo fato das imagens das "prateleiras" de produtos estarem em uma ordem não convencional decidi usar grid-layout para organizar.

**Desenhei o grid no paint:**
![Grid 1](arquivos/grid-paint-1.png)


![Grid 2](arquivos/grid-paint-2.png)
Por precisar dar suporte ao Internet Explorer 11, fiz o mesmo de forma compatível

```
.fs-shelf {
    display: grid;
    display: -ms-grid;

    &--odd {
        -ms-grid-columns: 20% 10% 10% 10% 10% 10% 20% 10%;
        grid-template-columns: 2fr 1fr 1fr 1fr 1fr 1fr 2fr 1fr;
    }

    &--even {
        -ms-grid-columns: 10% 20% 10% 10% 10% 10% 10% 20%;
        grid-template-columns: 1fr 2fr 1fr 1fr 1fr 1fr 1fr 2fr;
    }

    -ms-grid-rows: 28.57% 14.2857% 28.57% 28.57%;
    grid-template-rows: 2fr 1fr 2fr 2fr;
}

.fs-shelf__product--1 {
    -ms-grid-row: 1;
    -ms-grid-row-span: 1;
    grid-row: 1 / span 1;
    -ms-grid-column: 8;
    -ms-grid-column-span: 1;
    grid-column: 8 / span 1;
}
```

Nesta forma de trabalhar cada item diz a sua posição e não o container.

**Resultado:**

![Versão 1](arquivos/versao-1.png)

**Horas de trabalhadas:** 5

## Versão Desktop
Continuado o trabalho, inserindo html e CSS.
Versão Desktop concluída, com alguns ajustes pendentes.


![Versão 1](arquivos/versao-2.jpg)

**Horas de trabalhadas:** 18

## Versão Mobile


![Layout Mobile](arquivos/hotsite-fs-mobile.jpg)

A versão mobile chegou depois da desktop, então eu não sabia como precisava organizar os elementos HTML, mas como optei por usar display: grid, a conversão foi mais simples.

Fiz novamente o grid no Paint:
![Layout Mobile](arquivos/grid-paint-3.jpg)

Não esperava que o botão de compra mudasse de lugar no grid, coloquei ele para baixo com position: absolute.

**Horas de trabalhadas:** 3