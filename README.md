# 🗒 Formulários

## O que é um formulário?

* Tem o papel de receber dados do usuário e enviar para um servidor;
* Permite validar dados;
* As tags mais usadas são: **FORM, LABEL e INPUT**.

### Elemento FORM

* Cria o formulário e o delimita.

### Elemento LABEL

* Descreve os inputs.

### Elemento INPUT

* Aonde inserimos dados, temos vários tipos: **NUMBER, EMAIL, TEXT** e etc.

## Criando um formulário

{% code lineNumbers="true" %}
```html
<form>
    <label>Nome:</label>
    <input type="text"/>
</form>
```
{% endcode %}

## Atributos do FORM

### ACTION

* O arquivo/página que os dados serão enviados.

### METHOD

* GET ou POST.

{% code lineNumbers="true" %}
```html
<form action="register.php" method="POST">
    <label>Nome:</label>
    <input type="text"/>
</form>
```
{% endcode %}

## Atributos do INPUT

### NAME

* Este atributo serve para pegar o valor quando o formulário é enviado para o servidor.

{% code lineNumbers="true" %}
```html
<form>
    <label>Nome:</label>
    <input type="text" name="age"/>
</form>
```
{% endcode %}

## Tipos de INPUT

### PASSWORD

* O texto passa a ser exibido com \*, para mascarar os dígitos.

### RESET

* Feito através de um INPUT do tipo RESET, que funciona como o botão de SUBMIT;

### RADIO

* É utilizado para selecionar apenas uma opção de várias possibilidades;

### CHECKBOX

* Para selecionar uma ou mais opções, e também cancelar a seleção de uma opção;

{% code lineNumbers="true" %}
```html
<div>
    <label for="optionals">Opcionais do carro:</label>
    <div class="radio">
    <!-- Têm que colocar colchete no NAME pra poder enviar mais de uma opção -->
        <input type="checkbox" name="optionals[]" value="big_tires"/>
        <label for="big_tires">Pneus Grandes</label>
    </div>
</div>
```
{% endcode %}

### DATE

<pre class="language-html" data-line-numbers><code class="lang-html">&#x3C;div>
    &#x3C;label for="birthday">Data de nascimento:&#x3C;/label>
<strong>    &#x3C;input type="date" name="birthday"/>
</strong>&#x3C;/div>
</code></pre>

## Atributos da LABEL

### FOR

* Usado para linkar com um input;
* O valor deve ser o mesmo que o atributo NAME do INPUT que corresponde a aquela LABEL;
* Ajuda o site a ser melhor ranqueado no Google.

{% code lineNumbers="true" %}
```html
<form>
    <label for="age">Nome:</label>
    <input type="text" name="age"/>
</form>
```
{% endcode %}

## Enviando o Formulário

* Podemos enviar pelo botão de SUBMIT;
* O botão é um INPUT, porém mudamos o TYPE para SUBMIT;
* Os dados serão enviados através de uma requisição HTTP;
* Precisamos de uma integração com o back-end, para aproveitar os dados do formulário.

{% code lineNumbers="true" %}
```html
<form>
    <input type="submit" value="Enviar"/>
</form>
```
{% endcode %}

## Elemento SELECT

* A tag SELECT têm suas opções representadas por tags de OPTION;
* Também têm um atributo NAME;

{% code lineNumbers="true" %}
```html
<div>
    <label for="job">Seleciona sua profissão:</label>
    <select name="job">
        <option value="programador">Programador</select>
        <option value="tester">Tester / QA</select>
    </select>
</div>
```
{% endcode %}

### Atributo SELECTED

* Podemos iniciar o SELECT com uma opção já selecionada;
* Abordagem interessante quando temos uma opção muito provável.

{% code lineNumbers="true" %}
```html
<div>
    <label for="contract">Você leu os termos do contrato?</label>
    <select name="contract">
        <option value="sim">Sim</select>
        <option value="nao" selected>Não</select>
    </select>
</div>
```
{% endcode %}

## Múltiplas Seleções

* Interessante quando queremos aceitar um ou mais dados;
* Precisamos apenas inserir o atributo MULTIPLE na tag SELECT.

{% code lineNumbers="true" %}
```xml
<div>
    <label for="itens">Selecione os itens desejados:</label>
    <select name="itens" multiple>
        <option value="pera">Pêra</select>
        <option value="feijao" selected>Feijão</select>
        <option value="arroz" selected>Arroz</select>
    </select>
</div>
```
{% endcode %}

## Elemento TEXTAREA

* Semelhante ao INPUT de tipo TEXT;
* Utilizado para textos maiores, como a bio do Instagram.

{% code lineNumbers="true" %}
```html
<div>
    <label for="comment">Comentário:</label>
    <textarea name="comment" cols="30" rows="10"></textarea>
    <!-- COLS = Colunas | ROWS = Linhas -->
</div>
```
{% endcode %}

## Elementos FIELDSET e LEGEND

* FIELDSET é usado para agrupar INPUTS, principalmente quando os dados possuem relação entre si;
* LEGEND é como uma LABEL, que descreve os INPUTS agrupados.

{% code lineNumbers="true" %}
```html
<div>
    <fieldset>
        <legend>Preencha as suas informações:</legend>
        <label for="firstname">Nome:</label>
        <input type="text" name="firstname"/>
        <label for="lastname">Sobrenome:</label>
        <input type="text" name="lastname"/>
    </fieldset>
</div>
```
{% endcode %}

## Elemento DATALIST

* É como um SELECT, mas com um AUTOCOMPLETE;
* Podemos pesquisar por possíveis valores para preencher o INPUT;

{% code lineNumbers="true" %}
```html
<div>
    <label for="flavor">Escolha o sabor:</label>
    <input type="text" name="flavor" list="flavors"/>
    
    <datalist id="flavors">
        <option value="morango">Morango</option>
        <option value="chocolate">Chocolate</option>
    </datalist>
</div>
```
{% endcode %}

