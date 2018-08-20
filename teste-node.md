Em nossos testes avaliamos conhecimento técnico, clareza, criatividade e organização de código. 

Procure resolver as questões da melhor maneira possivel.

1) Como se chama o conceito que permite que uma função acesse variáveis de sua função pai?

    1. Polimorfismo
    2. Closure
    3. Heranca
    4. Singleton
    5. Nenhum dos citados

2) Considerando o funcionamento de Async/Await, Qual dessas respostas não está correta:

    a) A expressão await pausa a execução da função assíncrona e espera pela resolução da Promise passada
    b) Simplificam o uso de Promises na forma sincrona
    c) A expressão async pausa a execução da função assíncrona e espera pela resolução da Promise passada

3) Descubra e corrija o erro código abaixo:

    ```javascript
    const fetch = require('node-fetch');

    class UsuarioService {
        constructor() {
            this.fetch = fetch;
        }

        ListarUsuarios() {
            return this.fetch('https://reqres.in/api/users')
                    .then(res => res.json())
        }

        async MostarUsuarios() {
            let usuarios = this.ListarUsuarios();
            console.log(usuarios);
        }
    }

    let usuarioService = new UsuarioService();
    usuarioService.MostarUsuarios();
    ```

4) Refatore o código abaixo para que todos os tipos de cliente tenham o método "nomeCompleto", utilizando o conceito de Herança.

    ```javascript
    class ClienteEmpresarial {
        constructor(cnpj, primeiroNome, ultimoNome) {
            this.cnpj = cnpj;
            this.primeiroNome = primeiroNome;
            this.ultimoNome = ultimoNome;
        }

        nomeCompleto() {
            console.log(`${this.primeiroNome} ${this.ultimoNome}`);
        }
    }

    class ClienteResidencial {
        constructor(cnpj, primeiroNome, ultimoNome) {
            this.cnpj = cnpj;
            this.primeiroNome = primeiroNome;
            this.ultimoNome = ultimoNome;
        }

        nomeCompleto() {
            console.log(`${this.primeiroNome} ${this.ultimoNome}`);
        }
    }

    let empresarial = new ClienteEmpresarial(11111111111, 'Joao', 'Silva');
    let residencial = new ClienteResidencial(22222222222, 'Manuel', 'Oliveira');

    empresarial.nomeCompleto();
    residencial.nomeCompleto();
    ```

5) Dada as funçoes ListarEstados e ListarCidades, ajuste o método ListarTodos para que mostre no console todas as cidades e estados.

    ```javascript
    function ListarEstados() {
        return Promise.resolve(['RJ', 'SP']);
    }

    function ListarCidades(uf) {
        let cidades = [{ uf: 'RJ', nome: 'Rio de Janeiro' }, { uf: 'RJ', nome: 'Petrópolis' },
                    { uf: 'SP', nome: 'Sao Paulo' }, { uf: 'SP', nome: 'Sorocaba' }];
        return Promise.resolve(cidades.filter(x=> x.uf == uf));
    }

    function ListarTodos() {
        // ?
    }
   
    ListarTodos();
    ```

6) Faça o código abaixo funcionar utilizando o conceito de Closure:

```javascript
function start() {

    function display() {
        console.log(message);
    }

    display();
}

start();
```

7) Considerando o funcionamento das arrow functions, marque as opções corretas:

    a) Possuem sintaxe mais curta
    b) São sempre anônimas
    c) Simplificam o uso de Promises na forma sincrona
    d) Servem apenas para realizar buscas
    e) Não repassam o this do pai no bind

8) Refatore a função "amigos" para que utilize arrow functions:

    ```javascript
    class Pessoa {
        constructor(nome) {
            this.nome = nome;
        }

        amigos(nomes) {
            let self = this;
            nomes.map(function(nomeAmigo) {
                console.log(`Eu sou o ${self.nome} e o ${nomeAmigo} é meu amigo`);
            });
        }
    }

    let pessoa = new Pessoa('Joao');

    pessoa.amigos(['Felipe', 'Pedro']);
    ```

9) Quais dos itens abaixo não são frameworks de teste:

    a) Jest
    b) Mocha
    c) Express
    d) Supertest
    e) Restify

10) Crie um script em nodeJs, utilizando tetes e as melhores práticas de desenvolvimento, para resolver o problema abaixo:

    Fizz Buzz - Neste problema, você deverá exibir uma lista de 1 a 100, um em cada linha, com as seguintes exceções:

        Números divisíveis por 3 deve aparecer como 'Fizz' ao invés do número;
        Números divisíveis por 5 devem aparecer como 'Buzz' ao invés do número;
        Números divisíveis por 3 e 5 devem aparecer como 'FizzBuzz' ao invés do número'.

    Exemplo de saida:

        1,
        2,
        Fizz,
        4,
        Buzz,
        Fizz,
        7,
        ... continua