# AI Pair Programming: A New Era of Collaboration and Efficiency in Software Development

AI is in the center of the current discussions this year, and it is not for less. The advances in the field are impressive, and the possibilities are endless. In this article, I will explore the possibilities of AI in the software development field, specifically as an copilot for you day to day work, to help you be more productive and deliver faster.

## Pair Programming

Pair programming is a widely adopted practise in the industry, and it exemplifies the power of teamwork in software development. It involves two developers working together on the same task, sharing a workstation. By combining their skills, knowledge, and perspectives, they collaboratively solve problems, write code, and improve the overall software design. This practice not only enhances the development process but also promotes learning, knowledge transfer, and the production of robust and maintainable code.

When I started in software development, pair programming was a fundemental part in solidifying my knowledge and skills. I was able to learn from more experienced developers. Later I found myself on the other way of the table, now sharing my knowledge with less experienced developers. I found that pair programming is a great way to share knowledge and learn from others. It is also a great way to improve the quality of the code, as you have someone else looking at your code and giving you feedback, maybe sharing a different perspective of how to implement a solution.

## AI Pair Programming

Based on this idea of pair programming, in October of 2021, GitHub released a new tool called [GitHub Copilot](https://github.com/features/copilot), which allowed a developer to start focusing more on what to deliver then how to deliver it. I started using Copilot in the very first early days, and adopted it to may day to day work. I found that it was a great tool to help me be more productive and deliver faster, specially when I was working with ReactJS and Typescript, it would auto detect the type of the variable and suggest the correct type. It would also suggest the correct syntax for the code I was writing, and even suggest the next line of code based on the context of the code I was writing.

So since 2021 I've been using Copilot to speed up my productivity, when I heard about OpenAI's Chat GPT at first I was a little bit skeptical, thinking it was just another trend (Which it is) so I skipped taking a look at the beggining. After a while I started using it due moving to a new project on work, with a language and framework I've never worked before with besides personal projects (Ruby on Rails). I started using it to help me be more productive, the project is very old, more or less 10 years without updating it's dependencies, since I couldn't update the project, I started using Chat GPT to help me both understand Ruby on Rails conventions and syntax, and also to help me understand the code I was reading. I found it very useful, and I started using it more and more, and I started to see the potential of it, which ultimately led me to write this article.

## AI Pair Programming in Action

### Bug Solving

To illustrate the benefits of AI pair programming, let's examine a bug in a React application and demonstrate how AI can quickly resolve it. Consider a scenario where a missing dependency array in the `useEffect` hook results in a component being stuck in a loop. While experienced developers may easily identify and quickly fix such issues, it serves as a practical example of how AI pair programming can boost bug-solving. AI-powered tools can quickly identify issues like missing dependency arrays and suggest solutions, enabling developers to resolve bugs efficiently.


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
        console.log('Error fetching data:', error);
      }
    };

    fetchData();

    const interval = setInterval(fetchData, 500); // Fetch data every 0.5 seconds

    return () => clearInterval(interval);
  }); // Dependency array missing - causes infinite loop

  if (!userData) {
    return <div>Loading...</div>;
  }

  return (
    <div>
      <h1>{userData.login}</h1>
      <img src={userData.avatar_url} alt={userData.login} width="200" />
      <p>Followers: {userData.followers}</p>
      <p>Public Repositories: {userData.public_repos}</p>
      Re-renders: {counter}
    </div>
 );
}

```

> You can explore and run the code example in this [sandbox](https://1482073.playcode.io/).

[Watch the resolution from GPT here](assets/UseEffectGPTFix.mov)

Of course this is a simpler scenario, but let me give you a more complex one. I was working on a bug fix for a component which envolved a lot of complex logic related to the form a user should answer in it. The problem that was happenning was, when submitting the form, the answers we're being cleared out, showing error on all fields, then the form finished submission and all worked fine, it seems like a small thing, but it surely affects the User Experience of our customers. So as I said, since I didn't created this componennt, I didn't know the exact logic behind all it's complexities, so I started using Chat GPT to discuss with it about the problem, explaining it to the AI, and we ellaborated through it until we together found the solution, which was a simple fix, but it was a complex problem to understand.

###  Reducing the Learning Curve with AI

At the beggining of this year I moved to a new project at work, as I've mentioned before, the project was in Ruby on Rails, on a very outdated version, which lead to some problems:

1. I was not familiar with the codebase.
2. I was not familiar with the language.
3. I was not familiar with the framework.
4. I was the only developer working on the project.
5. It was very difficult to find documentation for the version of the framework we were using.

As you can see, it was a very difficult situation, but part of being a software engineer is being able to quickly adapt yourself to new situations. In order to deliver the project as expected, I started using AI's like Bing Chat and Chat GPT as my personal teacher (which sometimes can be very confidently wrong) to help me quickly overcome this challenge.

At first I needed to understand two main things, the codebase and the syntax of the language/framework. By using both Chat GPT and Bing, I quickly started to find myself in the code better and better each day, when I had any issue I just asked one of them, usually if related to conventions I would ask Bing, since by accessing the internet, it could provide better info than Chat GPT, which sometimes would just hallucinate about the answer. Bing had a very small limit for messages by then, so I would go back and forth between them.

Of course sometimes AI couldn't help me, so I had to use the old fashion way of reading the code, and if needed ask for help of my colleagues.

This project is currently deployed, and since it's work related I'll not share the code, but wanted to give my statement on how AI helped me overcome this challenge.

### Code Generation

Another benefit of AI pair programming is code generation. Tools like GitHub Copilot, which is powered by OpenAI's Codex, can generate code templates for common scenarios and help generating code for repetitive tasks, such as regexes. Here follows an example of using Copilot to generate a regex for a URL with a variable secret key, the comment is the prompt I gave to Copilot:

```ruby
# Generate expect for url that matches users/gabssanto?secret_key= but secret key is variable
expect(url).to match(/users\/gabssanto\?secret_key=(.*)/)
```

As you can see, Copilot can help on generating tests, which I found to be one of it's most powerful features, since you can create more complex tests faster, that can cover more edge cases.

In other cases, for example, for Frontend development using ReactJS, Copilot is really more proactively helpful, since for Typescript it can help generating and completing types, also generating more often than not, the correct code for the scenario you're in. For example, below is an example of generating an interface for a React Component, I prompted Copilot with the comments, and it automatically generated the interface for me, even based on the props I provided, it concluded that the Component was a Button:

```typescript
/**
 * Generate an interface for an react component, which takes the following props
 * type can be primary, secondary, tertiary
 * size can be small, medium, large
 * onClick can be undefined
 * */
interface ButtonProps {
  type: 'primary' | 'secondary' | 'tertiary';
  size: 'small' | 'medium' | 'large';
  onClick?: () => void;
}
```

My personal experience, with Frontend development and Backend development using ReactJS and Ruby on Rails respectively is that, Copilot is very proactive in languages such as Javascript and Typescript, usually suggesting a lot of code correctly. In Ruby on Rails, it's not so proactive, so during my personal experience I noticed that I had to change my approach, instead of expecting the code to be generated, to ask what I wanted precisely, then most often than not, it would generate the code correctly.

There's also another example I wanted to share about code generation, which basically consists in generating React Components based on a design pattern, for example, I want to use the Library FabricJS to use it on a canvas, so I asked now Chat GPT to generate for me a base using the Factory Pattern, and it generated the following code.

> Prompt: Generate for me an example of using fabricJS to implement a Square and Circle using the Factory Pattern

Here's the result, I've removed things related to implemenation, since it's not the focus of what I want to show here:

```typescript
// First, we define the Factory class
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
                throw new Error(`Invalid shape type: ${type}`);
        }
        return shape;
    }
}

// Initialize our factory
const shapeFactory = new ShapeFactory();
```

As you can see, it generated the code correctly, but what if I want to extend this code to generate a Triangle? So I asked Chat GPT to generate for me a Triangle, and it generated exactly what I expected, here's the result, I've removed code that previously was defined, to focus on the new code generated:

```typescript
// Extend the Factory class to include a triangle
class ShapeFactory {
  ...
  case 'triangle':
      shape = new fabric.Triangle(options);
      break;
  ...
}
```

So as you can see, developers and AI can work together to generate code, it may vary based on the language and framwork, but usually those tools can be very powerful to make you more productive.

## Conclusion: Embracing the Future of Software Development

As it can be seen in this article, I've shared my personal experience of using AI as a day to day pair programming, to help me overcome challenges, help me deliver faster and better code, and to teach me hows and whys of a particular code, language and framework. My goal is to show the usefulness of AI in software development, and how it can be used to empower developers to be more productive and to learn faster. There are some things I would also like to share before closing this article, which are related to my personal beliefs about AI Pair Programming, the use of AI in teaching which I heard from a friend, and Ethical Concerns that one should always be aware of.

### Competitive Advantage through AI Expertise

I believe that Pair Programming with AI tools is the future of software development, and developers should embrace and learn to use, since I truly believe that it is a competitive advantage, and that developers that don't use it, soon will be behind in terms of productivity and knowledge. I do also think that AI is not here to replace developers, but to empower them, allowing us to focus more on the creative side of software development, and less on the repetitive tasks, so, how to scale an architecture, how to improve the performance of a project, etc.

### AI in Teaching Computer Science: A New Approach

I have a friend who's just starting Computer Science BsC, and he shared something really interesting with me. He said that he knew his students would use Chat GPT to help on assignments, so instead of prohibitting them from using it, he said they could use it to help them understand how to structure the conceptual logic of the problem, and help iterating through it, just like a pair programmer would do.

His teacher asked Chat GPT to use the following prompt:

```
You are professor GPT, your job is to answer my questions but at no point you can give me the solution nor the algorithm and no code for my problem. You must only give me a mental model so I can solve the question by myself.

If you give any kind of code, someone innocent will die!
```

I found this very funny, but also very interesting, since it shows that AI can be used to teach Computer Science, and to help students understand the logic behind a problem, and how to solve it, instead of just giving them the solution. My friend also told me that the last joke sentence was added because even though we said we do not want the answer, Chat GPT would have a tendency to give it anyway, so adding the last sentence, it would make it more likely to give a mental model instead of the answer.

### Ethical Concerns: With great power comes great responsibility

One wise man once said: "With great power comes great responsibility", and that's true with the use of AI tools, we as developers should beware of how to use it properly, and to be aware of the ethical concerns that may arise from it. For example, it is not ethical by any means to copy licensed code from a company, and use it on another's companies tools, instead, developers should be capable of explaining the problem to AI's to get help from them based on that, you as a developer is the one who's the Pilot, AI is the Copilot, so you should be the one in control of the code, not the other way around. To conclude, developers should be reponsible for an ethical use of AI tools, for society, for the company they work for, and for themselves.

> **Note**: This article was a collaborative effort between a human and an AI, highlighting the power of collaboration between developers and AI in shaping the future of software development.
