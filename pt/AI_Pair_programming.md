# Programação em Par com IA: Uma Nova Era de Colaboração e Eficiência no Desenvolvimento de Software

A IA está no centro das discussões deste ano, e não é por menos. Os avanços nessa área são impressionantes e as possibilidades são infinitas. Neste artigo, explorarei as possibilidades da IA no campo do desenvolvimento de software, especificamente como um co-piloto para o seu trabalho diário, ajudando você a ser mais produtivo e entregar mais rapidamente.

## Programação em Par

A programação em par é uma prática amplamente adotada na indústria e exemplifica o poder do trabalho em equipe no desenvolvimento de software. Envolve dois desenvolvedores trabalhando juntos na mesma tarefa, compartilhando um único computador. Ao combinar suas habilidades, conhecimentos e perspectivas, eles resolvem problemas de forma colaborativa, escrevem código e melhoram o design geral do software. Essa prática não apenas aprimora o processo de desenvolvimento, mas também promove a aprendizagem, a transferência de conhecimento e a produção de código robusto e fácil de manter.

Quando comecei no desenvolvimento de software, a programação em par foi uma parte fundamental para solidificar meus conhecimentos e habilidades. Eu pude aprender com desenvolvedores mais experientes. Mais tarde, me vi do outro lado da mesa, compartilhando meu conhecimento com desenvolvedores menos experientes. Descobri que a programação em par é uma ótima maneira de compartilhar conhecimento e aprender com os outros. Também é uma ótima maneira de melhorar a qualidade do código, pois você tem outra pessoa analisando o seu código e fornecendo feedback, talvez compartilhando uma perspectiva diferente sobre como implementar uma solução.

## Programação em Par com IA

Com base nessa ideia de programação em par, em outubro de 2021, o GitHub lançou uma nova ferramenta chamada [GitHub Copilot](https://github.com/features/copilot), que permitia que um desenvolvedor se concentrasse mais no que entregar do que em como entregar. Comecei a usar o Copilot nos primeiros dias e o adaptei ao meu trabalho diário. Descobri que era uma ótima ferramenta para me ajudar a ser mais produtivo e entregar mais rapidamente, especialmente quando estava trabalhando com ReactJS e Typescript, pois ele detectava automaticamente o tipo da variável e sugeria o tipo correto. Ele também sugeria a sintaxe correta para o código que eu estava escrevendo e até mesmo sugeria a próxima linha de código com base no contexto do código que eu estava escrevendo.

Desde 2021, tenho usado o Copilot para acelerar minha produtividade. Quando ouvi falar do Chat GPT da OpenAI, a princípio fiquei um pouco cético, pensando que era apenas mais uma tendência (o que é), então ignorei no começo. Depois de um tempo, comecei a usá-lo devido à mudança para um novo projeto no trabalho, com uma linguagem e estrutura com as quais nunca havia trabalhado antes, além de projetos pessoais (Ruby on Rails). Comecei a usá-lo para me ajudar a ser mais produtivo. O projeto é muito antigo, com cerca de 10 anos sem atualizar suas dependências. Como não pude atualizar o projeto, comecei a usar o Chat GPT para me ajudar a entender as convenções e a sintaxe do Ruby on Rails, e também para me ajudar a entender o código que estava lendo. Achei muito útil e comecei a usá-lo cada vez mais, e comecei a ver seu potencial, o que acabou me levando a escrever este artigo.

## Programação em Par com IA em Ação

### Solução de Bugs

Para ilustrar os benefícios da programação em par com IA, vamos examinar um bug em um aplicativo React e demonstrar como a IA pode resolvê-lo rapidamente. Considere um cenário em que uma matriz de dependências ausente no `useEffect` causa um componente a ficar preso em um loop. Enquanto desenvolvedores experientes podem identificar e corrigir facilmente problemas como esse, isso é um exemplo prático de como a programação em par com IA pode impulsionar a resolução de bugs. Ferramentas com IA podem identificar rapidamente problemas como arrays de dependências ausentes e sugerir soluções, permitindo que os desenvolvedores resolvam bugs de forma eficiente.

```javascript
import React, { useState, useEffect } from 'react';

export function App() {
  const [counter, setCounter] = useState(0);
  const [userData, setUserData] = useState(null);

  useEffect(() => {
    const fetchData = async () => {
      try {
        const response = await fetch('https://api.github.com/users/gabssanto');
        const data = await response.json();
        setUserData(data);
        setCounter(counter + 1);
      } catch (error) {
        console.log('Erro ao buscar dados:', error);
      }
    };

    fetchData();

    const interval = setInterval(fetchData, 500); // Buscar dados a cada 0,5 segundos

    return () => clearInterval(interval);
  }); // Matriz de dependências ausente - causa loop infinito

  if (!userData) {
    return <div>Carregando...</div>;
  }

  return (
    <div>
      <h1>{userData.login}</h1>
      <img src={userData.avatar_url} alt={userData.login} width="200" />
      <p>Seguidores: {userData.followers}</p>
      <p>Repositórios Públicos: {userData.public_repos}</p>
      Renderizações: {counter}
    </div>
  );
}
```

> Você pode explorar e executar o exemplo de código neste [sandbox](https://1482073.playcode.io/).

[Assista à resolução do GPT aqui](assets/UseEffectGPTFix.mov)

É claro que este é um cenário mais simples, mas deixe-me apresentar um exemplo mais complexo. Eu estava trabalhando em uma correção de bug para um componente que envolvia muita lógica complexa relacionada ao formulário que o usuário deveria preencher. O problema que estava ocorrendo era que, ao enviar o formulário, as respostas estavam sendo apagadas e mostrando erros em todos os campos. Em seguida, o formulário terminava a submissão e tudo funcionava corretamente. Parece uma coisa pequena, mas afeta significativamente a experiência do usuário de nossos clientes. Como mencionei, como não criei esse componente, não conhecia a lógica exata por trás de todas as suas complexidades. Então, comecei a usar o Chat GPT para discutir o problema, explicando-o para a IA, e trabalhamos juntos até encontrar a solução, que era uma correção simples, mas o problema em si era complexo de entender.

### Reduzindo a Curva de Aprendizado com IA

No início deste ano, mudei para um novo projeto no trabalho, como mencionei antes, o projeto era em Ruby on Rails, em uma versão muito desatualizada, o que levou a alguns problemas:

1. Eu não estava familiarizado com a base de código.
2. Eu não estava familiarizado com a linguagem.
3. Eu não estava familiarizado com o framework.
4. Eu era o único desenvolvedor trabalhando no projeto.
5. Era muito difícil encontrar documentação para a versão do framework que estávamos usando.

Como você pode ver, era uma situação muito difícil, mas parte de ser um engenheiro de software é ser capaz de se adaptar rapidamente a novas condições. Para entregar o projeto conforme o esperado, comecei a usar a IA, como o Bing Chat e o Chat GPT, como meus professores (que às vezes podem estar muito confiantemente errados) para me ajudar a superar rapidamente esse desafio.

No início, eu precisava entender duas coisas principais: a base de código e a sintaxe da linguagem/framework. Usando tanto o Chat GPT quanto o Bing, comecei rapidamente a me familiarizar cada vez mais com o código a cada dia. Quando eu tinha algum problema, eu simplesmente perguntava a um deles, geralmente se relacionado a convenções eu perguntava ao Bing, pois, ao acessar a internet, ele poderia fornecer informações melhores do que o Chat GPT, que às vezes apenas inventava sobre a resposta. O Bing tinha um limite muito pequeno de mensagens na época, então eu ia e voltava entre eles.

Claro, às vezes a IA não podia me ajudar, então eu tinha que recorrer à maneira antiga de ler o código e, se necessário, pedir ajuda aos meus colegas.

Este projeto está atualmente em produção, e como está relacionado ao trabalho, não compartilharei o código, mas queria expressar como a IA me ajudou a superar esse desafio.

### Geração de Código

Outro benefício da programação em par com IA é a geração de código. Ferramentas como o GitHub Copilot, que é alimentado pelo OpenAI's Codex, podem gerar modelos de código para cenários comuns e ajudar a gerar código para tarefas repetitivas, como expressões regulares (regex). A seguir, apresento um exemplo de uso do Copilot para gerar uma regex para uma URL com uma chave secreta variável, o comentário é a instrução que forneci ao Copilot:

```ruby
# Gerar expectativa para uma URL que corresponda a users/gabssanto?secret_key=, mas a chave secreta é variável
expect(url).to match(/users\/gabssanto\?secret_key=(.*)/)
```

Como você pode ver, o Copilot pode ajudar na geração de testes, o que considero uma de suas funcionalidades mais poderosas, pois você pode criar testes mais complexos de forma mais rápida, abrangendo mais casos de borda.

Em outros casos, por exemplo, no desenvolvimento de frontend usando ReactJS, o Copilot é realmente mais proativamente útil, pois, para o TypeScript, ele pode ajudar a gerar e completar tipos, além de gerar, na maioria das vezes, o código correto para o cenário em que você está. Abaixo está um exemplo de geração de uma interface para um componente React, no qual eu solicitei ao Copilot por meio de comentários, e ele gerou automaticamente a interface para mim, até com base nas props que forneci, ele concluiu que o Componente era um Botão:

```typescript
/**
 * Gerar uma interface para um componente React, que recebe as seguintes props
 * O tipo pode ser primary, secondary ou tertiary
 * O tamanho pode ser small, medium ou large
 * O onClick pode ser indefinido
 */
interface ButtonProps {
  type: 'primary' | 'secondary' | 'tertiary';
  size: 'small' | 'medium' | 'large';
  onClick?: () => void;
}
```

Minha experiência pessoal com o desenvolvimento de frontend e backend, usando ReactJS e Ruby on Rails, respectivamente, é que o Copilot é muito proativo em linguagens como JavaScript e TypeScript, geralmente sugerindo muito código corretamente. No Ruby on Rails, ele não é tão proativo, então, durante minha experiência pessoal, percebi que precisei mudar minha abordagem, em vez de esperar que o código fosse gerado, passei a pedir exatamente o que eu queria, e na maioria das vezes, ele gerava o código corretamente.

Também gostaria de compartilhar outro exemplo sobre geração de código, que basicamente consiste em gerar componentes React com base em um padrão de design. Por exemplo, quero usar a biblioteca FabricJS para usá-la em um canvas, então eu pedi ao Chat GPT que gerasse para mim um exemplo usando o padrão Factory, e ele gerou o seguinte código.

> Prompt: Gere para mim um exemplo de uso do fabricJS para implementar um Quadrado e um Círculo usando o padrão Factory

Aqui está o resultado, removi coisas relacionadas à implementação, pois não é o foco do que quero mostrar aqui:

```typescript
// Primeiro, definimos a classe Factory
class ShapeFactory {
    createShape(type, options) {
        let shape;
        switch (type) {
            case 'square':
                shape = new fabric.Rect(options);
                break;
            case 'circle':
                shape = new fabric.Circle(options);
                break;
            default:
                throw new Error(`Tipo de forma inválido: ${type}`);
        }
        return shape;
    }
}

// Inicializamos nossa fábrica
const shapeFactory = new ShapeFactory();
```

Como você pode ver, ele gerou o código corretamente, mas e se eu quiser estender esse código para gerar um Triângulo? Então, perguntei ao Chat GPT para gerar um Triângulo, e ele gerou exatamente o que eu esperava. Aqui está o resultado, removi o código que já estava definido para me concentrar no novo código gerado:

```typescript
// Estenda a classe Factory para incluir um triângulo
class ShapeFactory {
  ...
  case 'triangle':
      shape = new fabric.Triangle(options);
      break;
  ...
}
```

Como você pode ver, os desenvolvedores e a IA podem trabalhar juntos para gerar código. Isso pode variar de acordo com a linguagem e o framework, mas geralmente essas ferramentas podem ser muito poderosas para torná-lo mais produtivo.

## Conclusão: Abraçando o Futuro do Desenvolvimento de Software

Como pode ser visto neste artigo, compartilhei minha experiência pessoal de usar a IA como programação em par no dia a dia, para me ajudar a superar desafios, entregar código mais rápido e melhor, e me ensinar o como e o porquê de um código específico, linguagem e framework. Meu objetivo é mostrar a utilidade da IA no desenvolvimento de software e como ela pode ser usada para capacitar os desenvolvedores a serem mais produtivos e aprender mais rapidamente. Antes de encerrar este artigo, gostaria de compartilhar algumas coisas relacionadas às minhas crenças pessoais sobre a Programação em Par com IA, o uso da IA no ensino, que ouvi de um amigo, e as preocupações éticas que sempre devemos estar cientes.

### Vantagem Competitiva por meio da Expertise em IA

Acredito que a Programação em Par com ferramentas de IA é o futuro do desenvolvimento de software, e os desenvolvedores devem abraçar e aprender a usá-la, pois acredito sinceramente que é uma vantagem competitiva e que os desenvolvedores que não a utilizam logo ficarão para trás em termos de produtividade e conhecimento. Também acredito que a IA não está aqui para substituir os desenvolvedores, mas para capacitá-los, permitindo que nos concentremos mais no lado criativo do desenvolvimento de software e menos nas tarefas repetitivas, como escalar uma arquitetura, melhorar o desempenho de um projeto, etc.

### IA no Ensino de Ciência da Computação: Uma Nova Abordagem

Tenho um amigo que está começando o curso de Ciência da Computação e ele compartilhou algo muito interessante comigo. Ele disse que sabia que seus alunos usariam o Chat GPT para ajudar nas tarefas, então, em vez de proibi-los de usá-lo, ele disse que eles poderiam usá-lo para ajudá-los a entender como estruturar a lógica conceitual do problema e ajudar a iterar sobre ele, assim como um programador em par faria.

O professor dele pediu ao Chat GPT para usar a seguinte instrução:

```
Você é o professor GPT, seu trabalho é responder às minhas perguntas, mas em nenhum momento você pode me dar a solução nem o algoritmo e nenhuma linha de código para o meu problema. Você só deve me fornecer um modelo mental para que eu possa resolver a pergunta por conta própria.

Se você der qualquer tipo de código, uma pessoa inocente morrerá!
```

Achei isso muito engraçado, mas também muito interessante, pois mostra que a IA pode ser usada para ensinar Ciência da Computação e ajudar os alunos a entender a lógica por trás de um problema e como resolvê-lo, em vez de apenas fornecer a solução. Meu amigo também me disse que a última frase engraçada foi adicionada porque, mesmo que tenhamos dito que não queríamos a resposta, o Chat GPT tinha a tendência de fornecê-la de qualquer maneira, então adicionando a última frase, era mais provável que ele fornecesse um modelo mental em vez da resposta.

### Preocupações Éticas: Com grande poder vem grande responsabilidade

Um sábio já disse: "Com grande poder vem grande responsabilidade", e isso é verdade no uso de ferramentas de IA. Nós, como desenvolvedores, devemos estar cientes de como usá-las adequadamente e estar cientes das preocupações éticas que podem surgir. Por exemplo, não é ético de forma alguma copiar código licenciado de uma empresa e usá-lo em ferramentas de outras empresas, em vez disso, os desenvolvedores devem ser capazes de explicar o problema para a IA e obter ajuda com base nisso. Você, como desenvolvedor, é o piloto, a IA é o copiloto, então você deve estar no controle do código, e não o contrário. Para concluir, os desenvolvedores devem ser responsáveis pelo uso ético das ferramentas de IA, para a sociedade, para a empresa em que trabalham e para si mesmos.

> **Nota**: Este artigo foi um esforço colaborativo entre um humano e uma IA, destacando o poder da colaboração entre desenvolvedores e IA na moldagem do futuro do desenvolvimento de software.
