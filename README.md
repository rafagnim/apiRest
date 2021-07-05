<h2>Sistema de gerenciamento de pessoas em API REST com Spring Boot</h2>

Este pequeno API foi desenvolvido em aula proporcionada pela Digital Innovation One, através do desenvolvedor Rodrigo Peleais.

Em relação ao projeto desenvolvido em aula, fiz os seguintes acréscimos:

- ---

Acrescentei a API a opção de endereço, o que, dada a forma como efetuada resultou em alteração em vários pontos do projeto. Como a Entidade Pessoa pode ter vários tipos de endereço, foi necessária a criação de uma nova Enum AddressType com a enumeração dos tipos possíveis (optei pelos termos em português: RESIDENCIAL, COMERCIAL e OUTRO).

Foi necessário alterar a entidade Pessoa para inclusão desse atributo, na forma de FK (foreign key) e criar nova entidade DTO, para os endereços.

Fiz o teste da API alterada com uso da ferramenta Postman.

Abaixo segue a documentação, com a alteração efetuada.

JSON - Documentação:

http://localhost:8080/api/v1/people/ (POST)

http://localhost:8080/api/v1/people/"id" (PUT, etc.)

GET:

{"Id":Long}

POST:

{"firstName":"stringObrigatoria",

"lastName":"stringObrigatoria",

"cpf":"stringObrigatoria",

"address":[{"type":"COMERCIAL",

"address":"stringObrigatoria"}],

"birthDate":"dd-MM-aaa",

"phones":[{

"type":"MOBILE",

"number":"(011)67890123"}]}

```
Telefones Type (Enum):
HOME("Home"),
MOBILE("Mobile"),
COMMERCIAL("Commercial");
```

```
Endereços Type (Enum):
RESIDENCIAL("Residencial"),
COMERCIAL("Comercial"),
OUTRO("Outro");
```

Pré-requisitos para a execução do projeto:

* Java 11 (Para executar, alterar para SDK 11 (jbr-11 JetBrains Runtime version 11.1.10). Não utilizar versões superiores ou inferiores.
* Maven 3.6.3 ou versões superiores.
* Intellj IDEA Community Edition ou outra IDE.
