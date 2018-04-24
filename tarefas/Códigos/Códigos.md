# Padrões de Projeto
[retornar](../../README.md)

Aqui documentarei todos os novos padrões.

## <a name="BEM">BEM</a>
o intuito mais conhecido do Block Element Modifier (BEM) é melhorar o desempenho do navegador aplicar o CSS,
mas incluo também a vantagem de fazer o seletor ser facilmente sobrescrito. Não usaremos este como bala de prata,
combinaremos com aninhamento para assim criar seletores mais fortes, exemplo:
Então será usado BEM em todos os componentes para que cada marca possa adicionar sobre as suas características.

**SCSS do componente:**
```
.modal {
    &__container {
        width: 200px;
        height: 200px;
    }

    &__background {
        black;
    }
}
```

**SCSS da loja:** sem sobrepor, peso: 1
```
.modal {
    &__container {
        background-color: white;
    }
}
```

**SCSS da loja:** com sopreposição, peso: 2
```
.modal {
    .modal {
        &modal__container {
            width: 300px;
        }

        &modal__background {
            green;
        }
    }
}
```


**SCSS da loja:** com modificador, peso: 3
```
.modal {
    &.modal--login {
        .modal {
            &__container {
                width: 400px;
            }

            &modal__background {
                blue;
            }
        }
    }
}
```

[retornar](../../README.md)