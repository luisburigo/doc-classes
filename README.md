# Doc-classes

## Class: CarregaDadosPeloInput
  Objetos e valores aceitos:
  ```js
  CarregaDadosPeloInput({
      input: Element | Object | Required,
      output: Element | Object | Required,
      urlConfig: {
        url: String | Required,
        callback: Function
      },
      tipo: String | Required
  })
  
  // Caso utilize callbacks no input ou ouput
  
   CarregaDadosPeloInput({
      input: {
        el: Element | Required,
        callback: Function,
        callbackEmptyValue: Function
      },
      output: {
        el: Element | Required,
        callback: Function,
      },
      urlConfig: {
        url: String | Required,
        callback: Function
      },
      tipo: String | Required
  })
  ```


  Exemplo de como utilizar a classe:
  ```js
  const options1 = {
      input: document.getElementById('entrada'),
      output: document.getElementById('saida'),
      urlConfig: {
          url: 'http://teste.com/api/',
          path: 'teste'
      },
      tipo: 'cidade'
  }
  const carregaDadosPeloInput1 = new CarregaDadosPeloInput(options1);
  ```
  
  Exemplo de como utilizar a classe com metodos de callback:
  ```js
   const options2 = {
      input: {
          el: document.getElementById('entrada'),
          callbackEmptyValue(){
              console.log('Campo vazio')
          },
          callback(){
              console.log('Callback input')
          }
      },
      output: {
          el: document.getElementById('saida'),
          callback(){
              console.log('Callback output')
          }
      },
      urlConfig: {
          url: 'http://teste.com/api/'
      },
      tipo: 'loja'
  }
  const carregaDadosPeloInput2 = new CarregaDadosPeloInput(options2);
  ```
