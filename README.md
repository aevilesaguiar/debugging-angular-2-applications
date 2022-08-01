# Depurando aplicativos Angular 2

## Introdução

Embora o Angular 2 ainda seja jovem, existem muitas técnicas e métodos de depuração que você pode usar.

Este guia fornece uma visão geral abrangente das várias maneiras de depurar aplicativos Angular 2. Para tirar o máximo proveito da depuração do Angular 2, é recomendável que você use o Google Chrome , pois a maioria dos exemplos apresentados aqui dependem das Ferramentas do desenvolvedor do Chrome

## Habilitando e desabilitando a depuração

Os aplicativos Angular 2 têm o modo de desenvolvimento ativado por padrão. O modo de desenvolvimento permite que os erros sejam exibidos no console e o uso de pontos de interrupção. Quando você abre seu console no modo de depuração, normalmente vê esta mensagem aparecer:

Antes de implantar seu aplicativo e colocá-lo em um servidor ativo, certifique-se de desabilitar o modo de desenvolvimento. Para fazer isso, você precisa importar a função no arquivo em que está inicializando o aplicativo:

//main.ts

import { enableProdMode } from '@angular/core';

enableProdMode();
bootstrap(AppComponent, [
//providers, etc
]);

## Depurador

Ativar mapas de origem permitirá que você veja o código TypeScript de seu aplicativo em vez do código JavaScript transpilado, facilitando a depuração de seu código linha por linha.

Para ativar os mapas de origem, edite tsconfig.json

tscofig.json

{
  //...
  "compilerOptions": {
    "sourceMap": true
  }
  //...
}

Agora, em seu código-fonte, sempre que você colocar a instrução depurador, você poderá ver o código TypeScript em seu depurador, em vez de seu JavaScript transpilado:

search(term: string) {
    this.searchSubject.next(term);
    debugger; //debug here!
}

Quando você o usa, o depurador pausa o código em seu aplicativo e permite que você revise seu estado.


## Referencia:

- https://app.pluralsight.com/guides/debugging-angular-2-applications
