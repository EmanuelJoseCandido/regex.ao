<h1 align="center">
  Regex.ao
</h1>

<p align="center">
  <strong>regex.ao</strong> é uma coleção de expressões regulares mais comuns e que podemos querer implementar durante o desenvolvimento das nossas aplicações. Agora com esse repositório é só procurar e colar no seu projeto.
</p>

### Índice:

- [Remover acentos em strings](#remover-acentos-em-strings)
- [Remover números em strings](#remover-numeros-em-strings)
- [Permitir somente números](#permitir-somente-numeros)
- [Verificar se é uma URL](#verificar-se-e-uma-url)

#### <a id="remover-acentos-em-strings"></a> Remover acentos em `Strings`

```js
function removeAccents(value) {
	return value.normalize("NFD").replace(/[\u0300-\u036f]/g, "");
}

//input: Maçãs
//output: Macas
```

#### <a id="remover-numeros-em-strings"></a> Remover números em `Strings`

```js
function removeNumber(s) {
	return s.replace(/[0-9]/g, "");
}

//input: george21
//output: george
```

#### <a id="permitir-somente-numeros"></a> Permitir somente `Números`

```js
function allowNumber(value) {
	return /^[0-9]*$/.test(value);
}

//input: george21   //input: 230
//output: false     //output: true
```

#### <div id="verificar-se-e-uma-url"></div> Verificar se é uma `URL`

```js
function isURL(value) {
	const regex =
		/^(?:https?):\/\/(?:(?!(?:10|127)(?:\.\d{1,3}){3})(?!(?:169\.254|192\.168)(?:\.\d{1,3}){2})(?!172\.(?:1[6-9]|2\d|3[0-1])(?:\.\d{1,3}){2})(?:[1-9]\d?|1\d\d|2[01]\d|22[0-3])(?:\.(?:1?\d{1,2}|2[0-4]\d|25[0-5])){2}(?:\.(?:[1-9]\d?|1\d\d|2[0-4]\d|25[0-4]))|(?:(?:[a-z\u00a1-\uffff0-9]-*)*[a-z\u00a1-\uffff0-9]+)(?:\.(?:[a-z\u00a1-\uffff0-9]-*)*[a-z\u00a1-\uffff0-9]+)*(?:\.(?:[a-z\u00a1-\uffff]{2,})))(?::\d{2,5})?(?:\/\S*)?$/;

	return regex.test(value);
}

//input: www.martins.com   //input: https:github.com/martygo
//output: false     //output: true
```

## Alguma sugestão?

_Abra uma issue_
