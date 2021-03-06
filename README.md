# This project using REACT.JS

## Links
- https://www.youtube.com/watch?v=DiLVAXlVYR0
- https://www.youtube.com/channel/UCVTlvUkGslCV_h-nSAId8Sw
- https://blog.coderockr.com/gerenciando-rotas-com-react-router-ed44ce1e8753#.no8infsvj


## RUN the **learncodeacademy** code
```
```

## Imports
- **React** || Pega tudo no PACOTE _REACT_
- **ReactDOM** || Usado para criar o VIRTUAL DOM
- **ReactRouter** || Usado para _ROTAS_ top para _SPA_
  - **History** || Usado para _HISTORICO_ de navegação

## Functions

- ReactDOM.render(component, parentReceive) || _Renderiza_ os componentes do REACT
- **this.setState({obj})** || SÓ PODE MUDAR ESTADO COM ESSA FUNÇÃO
- **.bind()** || Passa um contexto de execução


## Components
- **Criar** um componente
  - Metodos
    - **render()** || _Renderiza_ o componente ao chama-lo
  - Atributos
    - **state** || Define o comportamento _ATUAL_ do componente
```javascript
  export default class MyComponent extends React.Component{
    constructor(){
      this.state = {obj}
    }
    render(){return element;}
  }
```
- **Usar** um componente || Deve ser chamado da seguinte forma.
```javascript
  import MyComponent from 'path/MyComponent';
```
- **PROPRIEDADES** || Funciona como atributos html
  - <Component attr={val} />
  - Para _ACESSAR_ usa-se o **this.props**
- **propTypes** || Usar _depois_ da declaração da classe
  - Define que é _obrigatório_
```javascript
  Component.propTypes = { obj: React.PropTypes.type.isRequired};
```  

- **VALORES PADROES** || Define os _valores_ padroes para _propriedades_ não informadas
```javascript
  Component.defaultProps = {obj};
```
### STATELESS FUNCTIONAL COMPONENTS
- Se um componente estiver usando **apenas** o método **render** para exibir conteúdo, então ele pode ser convertido em um **componente funcional sem estado**.
- Links
  - https://www.reactenlightenment.com/react-state/8.4.html
  - https://tylermcginnis.com/functional-components-vs-stateless-functional-components-vs-stateless-components/


# (OLD)CONTEXT 
- Set **context** | Not best pratice
```javascript
this.context.name;
```
- Define the expected context
```javascript
class App{}
App.contextTypes = {
  store: React.PropTypes.object.isRequired
}
```
# (NEW)CONTEXT 
- API de **contexto**. usado para definir **propriedades GLOBAIS**
  - Possui **duas funções**
   - **Provider** da um valor para um váriavel de contexto
   - **Consumer** utiliza valor para um váriavel de contexto
    
    
- **Criando** o contexto
```js
import React from 'react';
export default React.createContext({
  theme: 'teste'
});
```
- **Utilizando** contexto
```js
import ThemeContext from './components/context';
import * as themes from './styles/themes';

class App extends Component{
  state = {
    theme: themes.dark
  }
  
  toogleTheme = () => {
  }
  
  render(){
    return(
      <div>
      <ThemeContext.Provider value={this.state}>
        <ThemeSwitcher toggleTheme={this.toggleTheme} />
        <ThemeContext.Consumer>
        {theme => (
          <TodoList theme />
        )}

        </ThemeContext.Consumer>
      </ThemeContext.Provider>
      </div>
    )
  }
```

# REACT IN SERVER

## ELECTRODE
> **Render** react in **server** side Create by walmart

- Install
```shell
npm install yo gulp generator-electrode -g
```
- Init
```shell
yo electrode
```


## NEXT JS


## Observations
- Use _transpile babel_
- Use _webpack_
- Use JFX
- Nome do _componente_ deve ter inicio do nome _maiusculo_
- Ao criar um component deve _EXPORTAR_ com **export default**
- BOA PRATICA
  - Ter um _unico_ arquivo app.js(bootstrap) que contém o _COMPONENTE_ PRINCIPAL da app _ROOT COMPONENT_
- _JSX_ PRECISA de uma TAG que ENVOLVA TODO O HTML
- **constructor** sobreescreve constructor padrao, chamar **super()**
- Para _usar variaveis_ no JSX tem que ter o **{}**
- Para _componentes_ com _MAIS DE UM ELEMENTO_ no return devem estar entre algum _ELEMENTO PAI_
- Separar o CSS INLINE COM virgula **,**
- CSS INLINE nome das propriedades **não** devem receber **-**, _marginRight_
- **Proptype** || Serve para saber como usar o componente, define do que ele precisa para funcionar
  - Não gera erros para o usuário
  - Não para a aplicação/componente
  - Mostra erro no console
