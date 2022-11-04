Nesta semana vamos abordar a estruturação e a criação de um projeto de front-end com Angular. 

## Ambiente Windows (Versão 64 Bits)

Toda a configuração do ambiente deve ser feita utilizando o framework Angular cuja instalação e configuração de pacotes e dependências foi discutido na segunda semana do curso. Como estamos tratando do ambiente Windows, vamos fazer tudo dentro do Laragon. Vamos então colocar a mão na massa! 

### Executando o Laragon

Considero que você já tenha o Laragon instalado, conforme discutimos no guia prático da Semana 2. Execute o Laragon conforme a tela a seguir:

<p align="center">
  <img target="_blank" src="../imagens/laragon1.png" alt="Inicializar o Laragon."/>
</p>

Na sequência será apresentada uma tela com o painel completo do Laragon, como mostra a figura a seguir:

<p align="center">
  <img target="_blank" src="../imagens/laragon2.png" alt="Painel do Laragon."/>
</p>

Clique no botão iniciar tudo para que o MySQL e o PHP entrem em operação, como podemos verificar na figura abaixo

<p align="center">
  <img target="_blank" src="../imagens/laragon3.png" alt="Inicialização de serviços no Laragon."/>
</p>

Temos que lembrar que estamos em ambiente Windows e podemos fazer os ajustes no Laragon tanto no temrminal de comando do Windows (CMD) quanto no terminal que é proporcionado pelo Laragon. Por questão de facilidade, eu utilizarei o terminal do Laragon. Para isso clique no botão terminal no painel do Laragon e terá um terminal aberto para que possamos interagir com o framework, instalar o Laravel e também condificar a aplicação do back-end.

<p align="center">
  <img target="_blank" src="../imagens/laragon4.png" alt="Terminal do Laragon."/>
</p>

Vocês podem verificar também via Windows Explorer os arquivos para o funcionamento do Apache e onde colocaremos nossa aplicação, como pode ser observado na figura a seguir

<p align="center">
  <img target="_blank" src="../imagens/laragon5.png" alt="Diretório do Apache."/>
</p>

Uma vez tendo acesso ao terminal do Laragon, o próximo passo é instalar o composer.

### Instalação do Angular no Laragon

Para que possamos criar um projeto com Angular, é preciso ter o angular cli instalado no Laragon. Acesse o terminal do Laragon e entre na pasta C:\laragon\bin

```
cd ..

cd bin

```

A seguir execute o comando para instalar o angular:

```
npm install -g @angular/cli
```

e terá como saída a tela mostrada a seguir:

<p align="center">
  <img target="_blank" src="../imagens/angular-windows-laragon.png" alt="Diretório do Apache."/>
</p>

### Criação do Projeto Angular

Para criar um projeto angular precisamos antesde mais nada resolver algumas dependências. Segue a lista de de dependências:

- Node JS
- NPM
- Ferramenta de linha de comando.
- Angular CLI

Supondo que você já tenha todas essas dependências resolvidas, como mostramos no Guia da Semana 2, você poderá iniciar o projeto com Angular.

Com o Angular CLI instalado basta executar o comando `ng new nome-projeto` no terminal para criar um novo projeto angular, como mostra a tela a seguir. Vamos considerar que este projeto ficará na pasta 'C:\laragon\www' que é o diretório padrão do servidor Web Apache. O nosso projeto vai se chamar **angular-crud-app**.

<p align="center">
  <img target="_blank" src="../imagens/angular-windows6.png" alt="Criacao do projeto Angular."/>
</p>

Responda às perguntas no prompt de acordo com a imagem abaixo:

<p align="center">
  <img target="_blank" src="../imagens/angular-windows7.png" alt="Respostas às perguntas."/>
</p>

Após a geração do projeto, você terá uma mensagem com a descrita na tela a seguir e poderá prosseguir.

<p align="center">
  <img target="_blank" src="../imagens/angular-windows8.png" alt="Resultado da criacao do projeto Angular."/>
</p>

Caso apareça alguma mensagem como `fatal` pode ignorá-la e prosseguir.

A estrutura desse projeto é dividida da seguinte forma:

- **node_modules**: pasta na qual estão todas as dependências JS (Java Script) necessárias para a execução e desenvolvimento da aplicação Web. Essa pasta é criada com a execução do comando `npm install`.
- **src**: pasta que contém todos os arquivos `typescript`, `scss` e `html` que serão editados para a construção efetiva da aplicação.
- **angular.json**: padrões de configuração para todo o espaço de trabalho e específicos do projeto para ferramentas de construção e desenvolvimento fornecidas pelo Angular CLI.
- **package.json**: arquivo que contém as definições do projeto bem como as bibliotecas que estão sendo utilizadas.

Praticamente, quase que todas as mudanças que serão realizadas no sistema serão feitas em arquivos dentro desta pasta (**src**).

O pŕoximo passo após a criação do projeto é criar os arquivos que serão necessários para o projeto. No nosso caso vamos acessar `C:\laragon\www\angular-crud-app`

```
cd \laragon\www\angular-crud-app
```
Veja a figura a seguir:

<p align="center">
  <img target="_blank" src="../imagens/angular-windows9.png" alt="Resultado da criacao do projeto Angular."/>
</p>

### Criação dos Arquivos

Os arquivos serão criados utilizando o angular CLI. O Angular CLI com seu comando `generate` nos permite criar os mais diversos tipos de arquivos já semi configurados para um projeto angular. Abaixo são listados os tipos de arquivo que podem ser gerados com o `ng generate (ng g)`:

- application:
- class:
- component:
- directive:
- enum:
- guard:
- interceptor:
- interface:
- module:

O primeiro passo é acessar o arquivo `\laragon\www\angular-crud-app\src\app\app.componen.html` e apagar todo o seu conteúdo. Para acessar este arquivo entre na pasta e digite o comando

```
nano \laragon\www\angular-crud-app\src\app\app.componen.html
```
apague todo o conteúdo e salve o arquivo com **CTRL+X**, depois **w** e em seguida tecle **ENTER**.

A seguir, rode os comandos abaixo no terminal. Lembre-se de estar na pasta `angular-crud-app`. Execute os comandos abaixo um a um.

```
ng g m components/painel
ng g c components/painel

ng g m components/pais
ng g c components/pais

ng g m components/universidades
ng g c components/universidades
```

O resultado da execução dos comandos anteriores pode ser visto na tela abaixo:

<p align="center">
  <img target="_blank" src="../imagens/angular-windows10.png" alt="Resultado da excução dos comandos dos componentes."/>
</p>

A seguir você deve criar os módulos de rotas para País e Universidade

Criar module de rotas para país
Importar module de rotas de país no modulo de país.

Criar module de rotas para universidade
Importar module de rotas de universidade no modulo de universidade.

Criar as rotas no arquivo de app routing

importar HttpClientModule no app.module.ts

# Definindo as Rotas

Para oferecer maior desacoplamento para os modulos angular vamos criar arquivos de rotas específicos para o módulo. Isso facilita a mudança de rotas caso seja necessária e faz com que os arquivos sejam mais autônomos. Dentro da pasta do módulo e do componente vamos criar um arquivo seguindo a nomeclatura `nome-modulo-routing.module.ts`, como exemplo, se tivermos um módulo de país vamos criar uma arquivo `pais-routing.module.ts`. 

Dentro desse arquivo vamos ter um código semelhante a esse:

```
import { NgModule } from '@angular/core';
import { RouterModule, Routes } from '@angular/router';
import { PaisComponent } from './pais.component';

const routes: Routes = [
  {
    path: '',
    component: PaisComponent
  }
];

@NgModule({
  imports: [RouterModule.forChild(routes)],
  exports: [RouterModule]
})
export class PaisRoutingModule { }
```

Os `imports` são as unidades básicas de importação de código externo do typescript. A constante `routes` do tipo `Routes` define as rotas desse módulo. O objeto dentro do array em routes pode receber diversos parêmetros, os mais comuns são:

- **path**: determina o caminho para acessar essa rota. Note que deixamos o caminho vazio para que a definição do nome da rota possa ser feita em um arquivo de rotas mais geral.
- **component**: determina o componente que será renderizado nessa rota.
- **loadChildren**: utilizado para rendizar uma página de maneira lerda. Ou seja, separar a aplicação em módulos menores e só carregar um módulo quando ele precisar ser carregado. Isso ajuda na velocidade de carregamento das páginas.
- **pathMatch**: define a estratégia que será utilizada no roteamento.
- **redirectTo**: quando a rota que estiver com um redirectTo for acessada redireciona para outra rota especificada.

Dentro do `@NgModules` é importante destacar que dentro do imports deve ter o texto de **imports: [RouterModule.forChild(routes)]** a diferença dessa rota para a rota geral do sistema está que a outra rota possui um RouterModule para o root (raiz), enquanto que esses mantém a rota para os filhos.

Agora que já foi apresentado um panorama geral sobre as rotas vamos criar os componentes de rotas para país e universidades, painel não vai conter uma rota por que ele está na rota raiz "/" assim vamos importar o componente direto no `app-routing.module.ts`.

Para páis devemos criar um arquivo com o nome `pais-routing.module.ts` dentro da pasta `src/app/components/pais`. O código desse arquivo como foi apresentado a cima deve ser igual a este:

```
import { NgModule } from '@angular/core';
import { RouterModule, Routes } from '@angular/router';
import { PaisComponent } from './pais.component';

const routes: Routes = [
  {
    path: '',
    component: PaisComponent
  }
];

@NgModule({
  imports: [RouterModule.forChild(routes)],
  exports: [RouterModule]
})
export class PaisRoutingModule { }
```

Após o arquivo de routing de país ter sido criado e o código escrito deve ser realizada a importação desse módulo no módulo geral do componente. No caso o módulo geral do componente é `PaisModule`. Assim, dentro de `imports` de `PaisModule` devemos colocar `PaisRoutingModule`.

Agora devemos fazer o mesmo processo para universidades. Criando um arquivo `universidades-routing.module.ts` dentro da pasta `src/app/components/universidades`. O código será semelhante ao código de país como pode ser visto a seguir:

```
import { NgModule } from '@angular/core';
import { RouterModule, Routes } from '@angular/router';
import { UniversidadesComponent } from './universidades.component';

const routes: Routes = [
  {
    path: '',
    component: UniversidadesComponent
  }
];

@NgModule({
  imports: [RouterModule.forChild(routes)],
  exports: [RouterModule]
})
export class UniversidadesRoutingModule { }
```

Igual a país, o módulo de rotas de universidades deve ser importado dentro do `UniversidadeModule`.

Para finalizar a configuração das rotas devemos ajustar o arquivo de `app-routing.module.ts` para tal vamos criar os `paths` para as rotas e importar os módulos de cada componente de maneira *lazy*. Ao final vamos ter um  `app-routing.module.ts` igual a este:
```
import { NgModule } from '@angular/core';
import { RouterModule, Routes } from '@angular/router';
import { PainelComponent } from './components/painel/painel.component';

const routes: Routes = [
  {
    path: '',
    component: PainelComponent,
    pathMatch: 'full'
  },
  {
    path: 'pais',
    loadChildren: () => import('src/app/components/pais/pais.module').then(m => m.PaisModule)
  },
  {
    path: 'universidade',
    loadChildren: () => import('src/app/components/universidades/universidades.module').then(m => m.UniversidadesModule)
  }
];

@NgModule({
  imports: [RouterModule.forRoot(routes)],
  exports: [RouterModule]
})
export class AppRoutingModule { }
```

A rota "/" é primeiro carregada na aplicação angular. Aqui definimos que o componente `PainelComponent` é carregado quando a aplicação angular for carregada. 

A definição da rotas `pais` foi utiliza o loadChildren. Nesse ambiente criamos uma função anônima com `() => ` e importamos o módulo de país e então mapeamos o módulo de país para a rota usando o `then(m => m.NomeModulo)`. 

A mesma definição foi realizada para a rota de `universidades`. De forma que, quando passarmos a rota `localhost:4200/pais` carregamos o componente de país. E quando passamos `localhost:4200/universidades` carregamos o componente de universidade.

# Definindo os Serviços

Para realizar requisições a uma API externa utilizaremos a classe `HttpClient` do `'@angular/common/http'`. Para isso é necessário importar o `HttpClientModule` no `app.module.ts`. O resultado após a edição deve ficar como mostra a imagem a seguir:

<p align="center">
  <img target="_blank" src="../imagens/angular-windows14.png" alt="Resultado da excução dos comandos dos componentes."/>
</p>

Após realizar a importação do `HttpClientModule` no `app.module.ts` devemos criar os serviços de `pais` e `universidade`. Para criar esses serviços devemos executar os códigos também na raíz do projeto `angular-crud-app`:

```
ng g s services/pais ou
ng generate service services/pais
```

Ao executar o comando para criação de serviços serão criados dois arquivos um `.spec.ts` e um arquivo `.ts`. O arquivo `.spec.ts` é um arquivo para teste de aplicação, nesse caso, não faremos nenhuma edição nele, por que, não está no escopo da aplicaçao. O arquivo de serviço `.ts` será editado. O arquivo `.ts` é semelhante a esse:

```
import { Injectable } from '@angular/core';

@Injectable({
  providedIn: 'root'
})
export class PaisService {

  constructor() { }
}
```

Após isso devemos criar as funções que acessam o back-end e realize as iterações com o mesmo. Devemos realizar a injeção de dependência no `HttpClient` no construtor que fica igual a seguir:

```
constructor(private http: HttpClient) { }
```

Além disso, será importado as variáveis de ambiente definidas em environment. Aqui é importante definir a rota geral do back-end que será acessada. Por exemplo, o environment.ts padrão do angular fica na pasta `src/environments` e após edição fica da seguinte forma:

```
export const environment = {
  production: false,
  url_api: 'http://localhost/api/'
};
```

Após realizar a importação de `PaisService` e `environments.ts` devemos criar as funções `listar()`, `criar()`, `listarPorId()`, `atualizar()` e `excluir()`. A classe de PaisService depois de escrever essas funções fica da seguinte forma:

```
import { HttpClient } from '@angular/common/http';
import { Injectable } from '@angular/core';
import { environment } from 'src/environments/environment';

@Injectable({
  providedIn: 'root'
})
export class PaisService {

  constructor(private http: HttpClient) { }

  public listar() {
    return this.http.get(environment.url_api + 'paises');
  }

  public criar(pais: any) {
    return this.http.post(environment.url_api + 'paises', pais);
  }

  public listarPorId(id: number) {
    return this.http.get(environment.url_api + 'paises/' + id);
  }

  public atualizar(pais: any, id: number) {
    return this.http.put(environment.url_api + 'paises/' + id, pais);
  }

  public excluir(id: number) {
    return this.http.delete(environment.url_api + 'paises/' + id);
  }
}
```

E com a execução de:

```
ng g s services/universidades ou 
ng generate service services/universidade
```

criamos o serviço de universidade. E realizando as mesmas operações de país temos uma classe de serviço da seguinte forma:

```
import { HttpClient } from '@angular/common/http';
import { Injectable } from '@angular/core';
import { environment } from 'src/environments/environment';

@Injectable({
  providedIn: 'root'
})
export class UniversidadeService {

  constructor(private http: HttpClient) { }

  public listar() {
    return this.http.get(environment.url_api + 'universidades');
  }

  public criar(pais: any) {
    return this.http.post(environment.url_api + 'universidades', pais);
  }

  public listarPorId(id: number) {
    return this.http.get(environment.url_api + 'universidades/' + id);
  }

  public atualizar(pais: any, id: number) {
    return this.http.put(environment.url_api + 'universidades/' + id, pais);
  }

  public excluir(id: number) {
    return this.http.delete(environment.url_api + 'universidades/' + id);
  }
}
```

Os serviços devem ser importados dentro dos módulos que usarão o serviço. Para isso vamos começar detalhando a importação de painel. Painel necessita dos dois serviços, por que, a contagem total é realizada consultando os dois serviços. O arquivo de module de painel pode ser encontrado em `src/app/components/painel/painel.module.ts`. A importação dos serviços devem ser realizados dentro da variável `providers` do NgModule. O código com as importações vai ficar da seguinte forma:

```
import { NgModule } from '@angular/core';
import { CommonModule } from '@angular/common';
import { PainelComponent } from './painel.component';
import { PaisService } from 'src/app/services/pais.service';
import { UniversidadeService } from 'src/app/services/universidades.service';

@NgModule({
  declarations: [
    PainelComponent
  ],
  imports: [
    CommonModule
  ],
  providers: [
    PaisService,
    UniversidadeService
  ]
})
export class PainelModule { }
```

O módulo de país usa apenas o serviço de país, de forma que, basta importarmos esse serviço. Deve-se então editar o arquivo `src/app/components/pais/pais.module.ts` de forma que ele fique igual ao seguinte código:

```
import { NgModule } from '@angular/core';
import { CommonModule } from '@angular/common';
import { PaisComponent } from './pais.component';
import { PaisRoutingModule } from './pais-routing.module';
import { PaisService } from 'src/app/services/pais.service';

@NgModule({
  declarations: [
    PaisComponent
  ],
  imports: [
    CommonModule,
    PaisRoutingModule,
  ],
  providers: [
    PaisService
  ]
})
export class PaisModule { }

```

E por fim, universidades necessitam dos dois serviços. O serviço de país é necessário por causa do formulário de cadastro e de que toda aplicação universidade está relacionada a um país conforme definido no banco de dados. O arquivo que deve ser editado está localizado em: `src/app/components/universidades/universidades.module.ts`. Ao final da adição do serviço ele ficara igual ao arquivo a seguir.

```
import { NgModule } from '@angular/core';
import { CommonModule } from '@angular/common';
import { UniversidadesComponent } from './universidades.component';
import { UniversidadesRoutingModule } from './universidades-routing.module';
import { UniversidadeService } from 'src/app/services/pais.service';
import { UniversidadeService } from 'src/app/services/universidades.service';

@NgModule({
  declarations: [
    UniversidadesComponent
  ],
  imports: [
    CommonModule,
    UniversidadesRoutingModule,
  ],
  providers: [
    PaisService,
    UniversidadeService
  ]
})
export class UniversidadesModule { }
```

Os serviços devem ser importados dentros dos modules específicos dos quais serão utilizados. Essa importação é realizada dentro do array de `providers`.

# Criando a lógica no Typescript

O arquivo .ts criado junto com o componente que fica nas pastas de `src/app/components` são responsáveis por gerenciar as lógicas do componente. No construtor fazemos injeção de dependencia dos serviços e outras classes necessárias para a aplicação.

## Painel

A lógica do painel é recuperar a quantidade de países e universidades. O caminho para acessar o componente lógico do painel é `src/app/components/painel/painel.component.ts`. Edite o arquivo, de modo que ele da seguinte forma:

```
import { Component, OnInit } from '@angular/core';
import { PaisService } from 'src/app/services/pais.service';
import { UniversidadeService } from 'src/app/services/universidades.service';

@Component({
  selector: 'app-painel',
  templateUrl: './painel.component.html',
  styleUrls: ['./painel.component.scss']
})
export class PainelComponent implements OnInit {

  public nuPaises: number = 0;
  public nuUniversidades: number = 0;

  constructor(
    private _paisService: PaisService,
    private _universidadeService: UniversidadeService
  ) { }

  ngOnInit(): void {
    this._paisService.listar().subscribe(resp => {
      this.nuPaises = Object.values(resp).length;
    }, err => {
      console.error('Ocurreu um erro');
    });

    this._universidadeService.listar().subscribe(resp => {
      this.nuUniversidades = Object.values(resp).length;
    }, err => {
      console.error('Ocurreu um erro');
    });
  }
}
```

Aqui no construtor temos a injeção de dependência para `PaisService` e `UniversidadeService`. E no método `ngOnInit()` que é um dos métodos do ciclo de vida de um componente angular chama as funções de listar dos serviços que escutar a resposta com o `subscribe` e conforme a resposta `sucesso` ou `erro` executa ações diferentes. A ação realizada em caso de sucesso é contar a quantidade de valores e atribuir as variáveis `nuPais` e `nuUniversidades`. Já a função de erro nesse caso apenas apresenta uma mensagem `'Acorreu um erro'` no console do navegador.

Nessa parte do código são definidas as variáveis na classe.

```
public nuPaises: number = 0;
public nuUniversidades: number = 0;
```

A primeira definição é referente a visibilidade da variável. A sugunda se refere ao nome da variável. A terceira está relacionada ao tipo da variável. Por fim, depois do igual está a atribuição de valores.

## País

A lógica para país foca na criação de função que executam os códigos desenvolvidos no serviço e na lógica de interação com os elementos HTML relacionados. O caminho para acessar o componente lógico do painel é `src/app/components/pais/pais.component.ts`. A função de PaisComponent é apresentada a seguir:

```
import { Component, OnInit } from '@angular/core';
import { PaisService } from 'src/app/services/pais.service';

@Component({
  selector: 'app-pais',
  templateUrl: './pais.component.html',
  styleUrls: ['./pais.component.scss']
})
export class PaisComponent implements OnInit {

  public paises: any = [];
  public pais: any = this._iniciarPais();

  constructor(
    private _paisService: PaisService
  ) { }

  ngOnInit(): void {
    this.listar();
  }

  public listar(): void {
    this._paisService.listar().subscribe(resp => {
      this.paises = resp;
    });
  }

  public salvar(): void {
    if (this.pais.nome !== "") {
      this._paisService.criar(this.pais).subscribe(resp => {
        alert('Cadastrado!');
        this.listar();
        this.pais = this._iniciarPais();
      });
    }
  }

  public editar(pais: any): void {
    this.pais = Object.assign({}, pais);
  }

  public atualizar() {
    if (this.pais.nome !== "") {
      this._paisService.atualizar(this.pais, this.pais.id).subscribe(resp => {
        alert('Ataulizado!');
        this.listar();
        this.pais = this._iniciarPais();
      });
    }
  }

  public cancelar(): void {
    this.pais = this._iniciarPais();
  }

  public excluir(id: number): void {
    this._paisService.excluir(id).subscribe(resp => {
      alert('Excluído!');
      this.listar();
    });
  }

  private _iniciarPais() {
    return {
      id: null,
      nome: ''
    };
  }
}
```

Aqui temos duas variáveis `pais` e `paises`. A variável `pais` recebe as informações do formulário de cadastro. A variável `paises` recebe o array com a lista de países. Essas variáveis podem ser vistas na linhas 10-11 da classe.

O construtor instancia a classe de PaisService, para fazer as requisições para o back-end. Abaixo do construtor temos as funções da classe:

- **listar()**: faz uma consulta ao serviço de paises e recupera a lista de países.
- **salvar()**: verifica se os dados estão preenchidos se sim envia uma requisição ao serviço de país para salvar um novo país. Se for bem sucedido apresenta um alerta, lista os registros e limpa a variável de país.
- **editar()**: faz uma cópia do país passado por parâmentro que pela propriedade de two-way-databinding renderiza o dado no formulário.
- **atualizar()**: verifica se os dados estão preenchidos se sim envia uma requisição ao serviço de país para atualizar o país. Se for bem sucedido apresenta um alerta, lista os registros e limpa a variável de país.
- **cancelar()**: limpa a variável pais.
- **excluir()**: chama a função de excluir do serviço de país e passa o 'id' do pais que deve ser excluído. Se der certo apresenta o alerta e em seguida lista novamente os paises.
- **_iniciarPais()**: returna uma instância de país vazia.

## Universidade

Universidade segue a mesma lógica de país. O caminho para acessar o componente lógico do painel é `src/app/components/universidades/universidades.component.ts`. O código de universidade pode ser visto abaixo:

```
import { Component, OnInit } from '@angular/core';
import { PaisService } from 'src/app/services/pais.service';
import { UniversidadeService } from 'src/app/services/universidades.service';

@Component({
  selector: 'app-universidades',
  templateUrl: './universidades.component.html',
  styleUrls: ['./universidades.component.scss']
})
export class UniversidadesComponent implements OnInit {

  public paises: any = [];
  public universidades: any = [];
  public universidadeForm: any = this._iniciarUniversidade();

  constructor(
    private _paisService: PaisService,
    private _universidadeService: UniversidadeService
  ) { }

  ngOnInit(): void {
    this.buscarPaises();
    this.listar();
  }

  public buscarPaises(): void {
    this._paisService.listar().subscribe(resp => {
      this.paises = resp;
    });
  }

  public listar(): void {
    this._universidadeService.listar().subscribe(resp => {
      this.universidades = resp;
    })
  }

  public criar(): void {
    if (
      this.universidadeForm.nome !== "" &&
      this.universidadeForm.descricao !== "" &&
      this.universidadeForm.pais_id !== "" &&
      this.universidadeForm.dt_fundacao !== ""
    ) {
      this._universidadeService.criar(this.universidadeForm).subscribe(resp => {
        this.listar();
        this.universidades = this._iniciarUniversidade();
        alert('Cadastrado!');
      });
    }
  }

  public editar(universidade: any): void {
    this.universidadeForm = Object.assign({}, universidade);
  }

  public atualizar() {
    if (
      this.universidadeForm.nome !== "" &&
      this.universidadeForm.descricao !== "" &&
      this.universidadeForm.pais_id !== "" &&
      this.universidadeForm.dt_fundacao !== ""
    ) {
      this._universidadeService.atualizar(this.universidadeForm, this.universidadeForm.id).subscribe(resp => {
        alert('Ataulizado!');
        this.universidades = this._iniciarUniversidade();
        this.listar();
      });
    }
  }

  public cancelar(): void {
    this.universidadeForm = this._iniciarUniversidade();
  }

  public excluir(id: number): void {
    this._universidadeService.excluir(id).subscribe(resp => {
      alert('Excluído!');
      this.listar();
    });
  }

  private _iniciarUniversidade() {
    return {
      id: null,
      nome: '',
      descricao: '',
      dt_fundacao: '',
      pais_id: ''
    }
  }
}
```

# Criando o código HTML

Nos atentaremos nessa sessão em apresentar as particularidades do angular e não necessariamente no html ou css empregado na aplicação.

Para criar os formulários as classes `FormsModule` e `ReactiveFormsModule` devem ser importadas no `src/app/app.module.ts` e no modulo específico que fará uso do formulário. Isto é, `src/app/components/pais/pais.module.ts` e `src/app/components/universidades/universidades.module.ts`.

O app.module.ts fica da seguinte forma após essa adição:

```
import { NgModule } from '@angular/core';
import { BrowserModule } from '@angular/platform-browser';
import { HttpClientModule } from '@angular/common/http';
import { AppRoutingModule } from './app-routing.module';
import { AppComponent } from './app.component';
import { FormsModule, ReactiveFormsModule } from '@angular/forms';

@NgModule({
  declarations: [
    AppComponent
  ],
  imports: [
    BrowserModule,
    AppRoutingModule,
    HttpClientModule,
    FormsModule,
    ReactiveFormsModule
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }
```

O módulo pais-module.ts fica da seguinte forma ao adicionar os forms:

```
import { NgModule } from '@angular/core';
import { CommonModule } from '@angular/common';
import { PaisComponent } from './pais.component';
import { PaisRoutingModule } from './pais-routing.module';
import { PaisService } from 'src/app/services/pais.service';
import { FormsModule, ReactiveFormsModule } from '@angular/forms';

@NgModule({
  declarations: [
    PaisComponent
  ],
  imports: [
    CommonModule,
    PaisRoutingModule,
    FormsModule,
    ReactiveFormsModule
  ],
  providers: [
    PaisService
  ]
})
export class PaisModule { }
```

E o módulo de universidades.module.ts fica da seguinte forma:

```
import { NgModule } from '@angular/core';
import { CommonModule } from '@angular/common';
import { FormsModule, ReactiveFormsModule } from '@angular/forms';
import { UniversidadesComponent } from './universidades.component';
import { UniversidadesRoutingModule } from './universidades-routing.module';
import { PaisService } from 'src/app/services/pais.service';
import { UniversidadeService } from 'src/app/services/universidades.service';

@NgModule({
  declarations: [
    UniversidadesComponent
  ],
  imports: [
    CommonModule,
    FormsModule,
    ReactiveFormsModule,
    UniversidadesRoutingModule,
  ],
  providers: [
    PaisService,
    UniversidadeService
  ]
})
export class UniversidadesModule { }
```

Para completar as configurações básicas para a criação do front-end. Basta copiar o seguinte css para o arquivo `src/styles.scss`:

```
/* You can add global styles to this file, and also import other style files */
body {
  font-family: "Roboto", sans-serif !important;
}

.titulo {
  width: 100%;
  text-align: center;
  font-style: normal;
}

.text-center {
  text-align: center;
}

.btn {
  background-color: cadetblue;
  border: 1px solid #c9c9c9;
  min-height: 20px;
  padding: 10px 15px;
  color: white;
  border-radius: 2px;
  cursor: pointer;
}

.txt-vermelho {
  color: red;
}

.m-lados {
  margin: 0px 5px;
}

.m-topo {
  margin-top: 20px;
}

.m-bottom {
  margin-bottom: 20px;
}

.table {
  width: 100%;
  border-collapse: collapse;
  margin-bottom: 1rem;
}

.table td, .table th {
  border: 1px solid #ddd;
  padding: 8px;
}

.table th {
  padding-top: 12px;
  padding-bottom: 12px;
  text-align: left;
  background-color: #04AA6D;
  color: white;
}
```

## Painel

No painel serão exibidos a quantidade de países e universidades cadastradas. A rota para esse arquivo é `src/app/components/painel/painel.component.html`. O html ficou da seguinte forma:

```
<div class="flex" style="margin-top: 60px;">
  <div class="box box-azul">
    <p>Total Países</p><br>
    <span>{{nuPaises}}</span>
  </div>

  <div class="box box-verde">
    <p>Total Universidades</p><br>
    <span>{{nuUniversidades}}</span>
  </div>
</div>
```

Aqui é importante observar a expressão ``{{  }}`` essa expressão é utilizada para imprimir um valor que foi mapeado no arquivo typescript que mapeia esse componente HTML. Dessa forma, o código HTML apresentado vai exibir o valor que existe nas variáveis `nuPaises` e `nuUniversidades`.

Para painel é necessário adicionar os estilos da página. O estilo da página pode ser visto abaixo:

```
.flex {
  display: flex;
  justify-content: center;
}

.box {
  display: block;
  width: 280px;
  height: 160px;
  border-radius: 5px;
  text-align: center;
  margin: 0px 10px;

  &.box-azul {
    background-color: #00008b;
    color: white;
  }

  &.box-verde {
    background-color: #008000;
    color: white;
  }

  p {
    font-size: 1.5rem;
    margin-bottom: 2px;
  }

  span {
    font-size: 2rem;
  }
}
```

Copie e cole esse estilo e o adicione no arquivo `src/app/components/painel/painel.component.scss`.

## País

Na tela de país serão exibidos o formulário de cadatro e edição de país, a listagem de países e os botões de alterar e excluir um país. A rota para esse arquivo é `src/app/components/pais/pais.component.html`. O código HTML referente a essa página é igual ao apresentado abaixo:

```
<h4>Cadastrar País</h4>
<form action="" class="m-bottom">
  <div>
    <label for="nome">Nome <span class="txt-vermelho">*</span>:</label> <br>
    <input type="text" name="nome" [(ngModel)]="pais.nome">
  </div>

  <button *ngIf="!pais.id" type="submit" class="btn m-topo" (click)="salvar()">
    Salvar
  </button>

  <button *ngIf="pais.id" type="submit" class="btn m-topo" (click)="atualizar()">
    Salvar
  </button>
  <button *ngIf="pais.id" type="submit" class="btn m-topo" (click)="cancelar()">
    Cancelar
  </button>
</form>

<hr>

<h4>Lista de Países</h4>
<table class="table m-topo m-bottom">
  <thead>
    <tr>
      <th>#</th>
      <th>Nome</th>
      <th>Ações</th>
    </tr>
  </thead>
  <tbody *ngIf="paises.length > 0">
    <tr *ngFor="let pais of paises;">
      <td>{{ pais.id }}</td>
      <td>{{ pais.nome }}</td>
      <td>
        <button (click)="editar(pais)">Editar</button>
        <button (click)="excluir(pais.id)">Excluir</button>
      </td>
    </tr>
  </tbody>
  <tbody *ngIf="paises.length == 0">
    <tr>
      <td class="text-center" colspan="3">
        Nenhum resultado encontrado.
      </td>
    </tr>
  </tbody>
</table>
```

Nessa tela existem diversas diretivas angular importantes: `[(ngModel)]`, `ngIf`, `ngFor` e `(click)`.

- **[(ngModel)]**: realiza o mapeamento em duas vias com uma variavel que é passada para ele. O mapeamento em dois caminhos significa que o ngModel vai escutar qualquer alteração no valor da variável e atualizar o campo e vice-versa. 
- **ngIf**: o ngIf é a forma de realizar operações condicionais no angular, normalmente você precisa passar uma expressão lógica que, caso seja verdadeira vai exibir o html, caso falsa vai ocultar o html. 
- **ngFor**: o ngFor é uma das formas de realizar iterações em angular. Normalmente o for deve receber a variavel que vai receber o valor e a variável que contém um array de valores. No exemplo acima isso pode ser visto em `*ngFor="let pais of paises;"`, que siginifica: itere a variável paises e atribua os valores um a um na váriavel país que foi criada para essa circunstância.
- **(click)**: cria um evento de click para o componente html que estiver com essa função. Um exemplo aqui é `(click)="editar(pais)"` que significa: quando clicar eu vou chamar a função editar e passar a variável país. Essa função editar fica no componente ts com o mesmo nome do componente html.

## Universidade

Universidade segue a mesma lógica que páis. A rota para esse arquivo é `src/app/components/universidade/universidade.component.html`. O componente html de universidade ficou dessa forma:

```
<h4>Cadastrar Universidade</h4>
<form action="" class="m-bottom">
  <div class="m-topo m-bottom">
    <label for="nome">Nome <span class="txt-vermelho">*</span>:</label> <br>
    <input type="text" name="nome" [(ngModel)]="universidadeForm.nome">
  </div>

  <div class="m-topo m-bottom">
    <label for="dtFundacao">Data da Fundação <span class="txt-vermelho">*</span>:</label> <br>
    <input type="date" name="dtFundacao" [(ngModel)]="universidadeForm.dt_fundacao">
  </div>

  <div class="m-topo m-bottom">
    <label for="pais">País <span class="txt-vermelho">*</span>:</label> <br>
    <select name="pais" [(ngModel)]="universidadeForm.pais_id" [disabled]="universidadeForm.id">
      <option value="">Selecione...</option>
      <option *ngFor="let pais of paises" value="{{ pais.id }}">{{ pais.nome }}</option>
    </select>
  </div>

  <div class="m-topo m-bottom">
    <label for="descricao">Descrição <span class="txt-vermelho">*</span>:</label> <br>
    <textarea name="descricao" cols="30" rows="10" [(ngModel)]="universidadeForm.descricao"></textarea>
  </div>

  <button *ngIf="!universidadeForm.id" type="submit" class="btn" (click)="criar()">
    Salvar
  </button>

  <button *ngIf="universidadeForm.id" type="submit" class="btn" (click)="atualizar()">
    Salvar
  </button>
  <button *ngIf="universidadeForm.id" type="submit" class="btn" (click)="cancelar()">
    Cancelar
  </button>
</form>

<hr>

<h4>Lista de Universidades</h4>
<table class="table m-topo  m-bottom">
  <thead>
    <tr>
      <th>#</th>
      <th>Nome</th>
      <th>Data Fundação</th>
      <th>Descrição</th>
      <th>Ações</th>
    </tr>
  </thead>
  <tbody *ngIf="universidades.length > 0">
    <tr *ngFor="let universidade of universidades;">
      <td>{{ universidade.id }}</td>
      <td>{{ universidade.nome }}</td>
      <td>{{ universidade.dt_fundacao }}</td>
      <td>{{ universidade.descricao }}</td>
      <td class="text-center">
        <button (click)="editar(universidade)">Editar</button>
        <button (click)="excluir(universidade.id)">Excluir</button>
      </td>
    </tr>
  </tbody>
  <tbody *ngIf="universidades.length == 0">
    <tr>
      <td class="text-center" colspan="5">
        Nenhum resultado encontrado.
      </td>
    </tr>
  </tbody>
</table>
```

## App Component

O html de app componente é diferente dos componentes acima. Por que, devido ao sistema de rotas que nós criamos toda vez que for renderizada a página de país a página de app também será renderizada. Pense nisso como uma organização de rotas igual a uma árvore. Eu tenho um componente pai e existirão componentes filhos. A rota para o app component é `src/app/app.components.html`.

O html de App Component é apresentado a seguir:

```
<h3 class="titulo">CRUD Básico em Angular/Laravel</h3>

<div class="text-center">
  <button routerLink="" class="btn m-lados" type="button">
    Painel
  </button>

  <button routerLink="pais" class="btn m-lados" type="button">
    Países
  </button>

  <button routerLink="universidade" class="btn m-lados" type="button">
    Universidades
  </button>
</div>

<router-outlet></router-outlet>
```

Nele definimos alguns botões que nos redirecionará para as diferentes rotas por causa da diretiva `routerLink` e temos também um componente `<router-outlet></router-outlet>`. O `</router-outlet>` é usado como um marcador para a renderização das telas filhas. Ou seja, quando eu redireciono minha aplicação para `localhost:4200/pais` o html de pais será renderizado em 
`</router-outlet>` e os html de app component será mantido estaticamente.

# Rodando a aplicação

Para executar a aplicação basta rodar o comando `npm start` no diretório raiz da aplicação. A aplicação pode ser acessada na URL `localhost:4200/`. O resultado pode ser visto a seguir

<p align="center">
  <img target="_blank" src="../imagens/angular-windows-browser.png" alt="Resultado da excução dos comandos dos componentes."/>
</p>
