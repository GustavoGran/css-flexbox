# css-flexbox

This is a repository to test basic configurations of flexbox and css grid

### Display Flex
- Basicamente o que ativa o Flexbox para funcionar em determinados elementos
- Para ativar display flex preciso ativar propriedade display flex para esses elementos.
- Ao posicionar todos os elementos do `body` dentro de um container e adicionar essa propriedade, você consegue o que deseja
```
.container {
    height: 100vh; //100 of viewport height makes the element fill the whole screen vertically (vh stands for viewport height)
    display: flex
}
```
### Flex direction
- Diz a ordem que os elementos filhos do container vão ser alinhados
- Ordens disponíveis
    - `row`
    - `column`
    - `row-reverse` na ordem contrária declarada no html
    - `column-reverse` na ordem contrária declarada no html
### Flex wrap
- Indica o que o elemento pai deveria fazer quando o espaço não é suficiente para alinhar no `flex-direction` indicado
- Deveria fazer um overflow + scroll do usuário?
- Deveria quebrar em mais uma linha? 
- tag `<p>` tem width de 100%, então a não ser que você especifique o width do `content` do `container`, ele ocupará tudo
- Ao diminuir para 250px por exemplo, é possível que a quebra exista
- chave para responsividade
- pode ser um nowrap ou wrapreverse

### Flex flow
- Serve como um híbrido entre flex-wrap e direction
- aceita na orderm "direction" "wrap"

### Justify-content
- Ajuda a alinhar elementos dentro do container na linha sobre os quais os elementos estão ordenados
- Row: alinha ao centro no eixo horizontal
- Column: alinha ao centro no eixo vertical
- Options: `center`, `left`, `right`
- `flex-start` e `flex-end` ajudam a alinhar no começo / fim da linha/coluna
- `space-between` mantém elementos igualmente espaçados com maior espaço possível, joga elemntos para o canto
- `space-around` espaça, mas mantém espaçamento das bordas
- `space-evenly` usa mesmo espaçamento entre elementos e nas bordas

### align-items
- Funciona numa alinhamento no sentido contrário daquele que o `flex-direction` aponta
- Não tem todas as options de `space`, mas tem uma option de `stretch` que funciona de maneira similar

### align-content
- Determina como as linhas estão espaçadas
- Funciona basicamente como o justify-content, mas no cross axis, ao invés do main axis

### gap
- Adiciona um gap 
- `gap: <row-gap> <column-gap>` row and column gap in px, vh, %
- `row-gap`, `column-gap`

### order
- Propriedade que dá ordem dos elementos
- Podemos mudar a ordem usando essa prop
- `order: 0;` seggue a ordem exatamente igual ao HTML
- Colocar numeros negativos ou positivos vai mudar a ordem dos elementos para aparecer acima ou abaixo da ordem padrão `0`

### flex-grow
- Determina habilidade do item de crescer conforme as dimensões da tela permitem
- default: `flex-grow: 0;`
- usamos proporção de quanto o bloco vai crescer vs outros
- blocos vão ocupar espaço desejado crescendo
- essa variável determina a proporção de crescimento dado um espaço disponivel

### flex-shrink
- Encolhem para caber no container
- Necessidades do container
    - Precisa ter uma largura máxima (para saber quando encolher)
    - Precisa de uma tag `nowrap`, para não escorregar para a linha de baixo 
- Default: `flex-shrink: 1`
- Encolhem se nosso container tem limite máximo de largura
- Encolhem 2x, 3x mais que os demais, apesar do tamanho não ser 2x/3x

### flex-basis
- Define o tamanho dos items
- default: `flex-basis: auto;`
- `flex-basis:0;` vs `flex-basis: auto;`
    - 0 vai sempre travar no tamanho do conteudo
    - auto pode crescer um pouco com o `flex-grow`

### flex
- Permite configurar flex-basis, flex-grow e flex-shrink de uma vez só
- ordem: grow, shrink, basis

### align-self
- Relacionado com o `align-items`
- Podemos mudar especificamente um bloco usando o `align-self`
- Apenas esse bloco
