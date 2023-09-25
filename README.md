# Desafio Técnico LinkApi - Júnior
## Instruções
- Leia atentamente as instruções abaixo para realização do teste proposto.
- Desenvolva e versione os projetos usando git.
- Utilize o GitHub para hospedar o código em um repositório privado.
- Crie a documentação de como executar e consumir seu projeto.
- Compartilhe este repositório privado com o e-mail people@linkapi.com.br.
- Enviar o link do repositório para people@linkapi.com.br.

## ⚠ IMPORTANTE - CRITÉRIOS DE DESCLASSIFICAÇÃO ⚠

- O teste em questão deve ser feito utilizando a engine NodeJS (Vanilla JavaScript ou
TypeScript), caso contrário, o candidato será desclassificado automaticamente.
- O repositório deve estar com o compartilhamento privado, caso contrário, o candidato será
desclassificado automaticamente.

# O que será avaliado?
- Requisitos realizados.
- Desacoplamento de código.
- Legibilidade de código.
- Boas práticas de desenvolvimento de API RESTful, utilize os links enviados como referência para aplicá-las em seu projeto.
- Mapeamento dos campos.
- Modelagem dos dados.
- Performance das aplicações.
- Documentação das aplicações.
- Exposição de dados sensíveis no código.

# Projeto 1 - API GATEWAY 

### Objetivo
Construção de uma API RESTful usando a tecnologia NodeJS.
### Fluxograma

![image](./apigateway.png)

## Endpoints
Endpoint - Listagem de usuários
1. Construir uma API RESTful que receba uma chamada simples e realizar a listagem de usuários do
serviço MockApi conforme os passos posteriores.
2. Deverá ser feita uma requisição para o serviço MockApi realizando a listagem de usuários, através da rota GET /users
3. Com a resposta da requisição anterior, deverá ser criado um subprocesso para cada usuário
retornado.
4. Para cada usuário retornado, deverá ser feita uma chamada na seguinte rota para resgatar o
endereço: "/users/{userId}/address".
5. Para cada usuário retornado, deverá ser feita uma chamada na seguinte rota para resgatar os
contatos: "/users/{userId}/contact".
6. As informações de contato e endereço deverão ser agrupadas junto ao seu respectivo usuário.
7. Sua API por fim deverá retornar ao requisitante os usuários com as respectivas informações
(informações base do usuário retornadas na listagem de usuários + lista de endereços + lista de
contatos).
8. O endpoint deverá retornar uma lista com o seguinte payload para cada usuário:
```json
{
	"id": "1",
	"createdAt": "2022-02-09T20:58:14.264Z",
	"fullName": "",
	"email": "",
	"addresses": [
		{
			"addressId": "1",
			"address": "Bahringer Field",
			"country": "Malaysia",
			"countryCode": "NF",
			"city": "Aliceshire",
			"state": "Utah",
			"zipcode": "68580"
		}
	],
	"contacts": [
		{
			"contactId": "1",
			"name": "Nina Jacobs I",
			"phoneNumber": "976-271-2917",
			"email": "Desiree_Schmidt@gmail.com"
		}
	]
}
```
## Pontos de atenção
### Serviço MockApi
#### Parâmetros de acesso da API
- URL base da API: https://{{host}}.mockapi.io/api/v1
- Parâmetro Host: Enviado por e-mail
#### Parâmetros de paginação
Esta api suporta parâmetros de paginação que podem ser utilizados, através da queryString para realizar a listagem completa de dados:
- page: Número da pagina a ser buscada
- limit: Quantidade de elementos a serem retornados por página
 #### Exemplo de utilização:
- GET /users?page=1&limit=10
#### Parâmetros de ordenação
Esta api suporta parâmetros de ordenação que podem ser utilizados através da queryString:
- sortBy: Campo que será considerado na ordenação de dados
- order:Ordem de classificação (asc ou desc)
#### Exemplo de utilização:
- GET /users?sortBy=createdAt&order=desc



# Projeto 2 - Automação de Conversão
### Objetivo
Desenvolvimento de uma automação em NodeJs.
### Fluxograma

![image](./atm.png)

### Requisitos
1. Criar um Script de automação em NodeJs, com as regras de negócio e funcionalidade dos steps
posteriores.
2. Seu script deverá inicialmente realizar a busca de todos os usuários na API que foi desenvolvida
anteriormente.
3. Com a resposta da requisição anterior, deverá ser criado um subprocesso para cada usuário
retornado.
4. Converter a estrutura de cada usuário para a estrutura abaixo:

```json
{
	"fullName": "Kapi Kaperson",
	"email": "kapi.kapeira@gmail.com",
	"address": "Rua das Kapivaras",
	"addressNumber": 123,
	"phoneNumber": "941-123-555"
}
```
5. Criar banco de dados Mongo, feito isso deverá ser criada uma collection chamada "users" para
inclusão dos usuários. Portanto para cada conversão realizar a inserção dos dados do usuário na
collection “users”.
## Pontos de atenção
Para a criação do banco de dados MongoDB é preferível a entrega com Docker, mas existem serviços
como MongoDB Atlas para criação de uma instancia gratuitamente que atende este requisito.

### Links que podem ser úteis no desenvolvimento:

- https://semantix.ai/primeiros-passos-em-api-gateway/
- https://semantix.ai/como-chegar-ao-nivel-supremo-de-apis-restful/
- https://semantix.ai/politicas-em-apis-restful/
- https://semantix.ai/seguranca-em-apis-restful/
- https://semantix.ai/performance-em-apis-restful-cache-compressao-e-mais/
- https://semantix.ai/api-restful-o-que-voce-precisa-saber-sobre-metodos-e-codigos-de-status-do-protocolo-http/
- https://semantix.ai/a-anatomia-de-uma-api-restful/
- https://semantix.ai/paginacao-ordenacao-e-filtros-em-apis-restful/
- https://semantix.ai/o-que-sao-funcoes-de-ordem-superior-em-javascript/
