# AI Pair Programming: A New Era of Collaboration and Efficiency in Software Development

AI is in the center of the current discussions this year, and it is not for less. The advances in the field are impressive, and the possibilities are endless. In this article, I will explore the possibilities of AI in the software development field, specifically as an copilot for you day to day work, to help you be more productive and deliver faster.

<!-- ## Table of Contents -->
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

<!-- ### Code Generation and Snippet Suggestions: AI at Work

### Competitive Advantage through AI Expertise

### AI in Teaching Computer Science: A New Approach

## Conclusion: Embracing the Future of Software Development -->

<!-- ### Ethical Concerns  -->

<!-- Talk about not to use entire files, to use mainly for getting help on snippets if needed, but try to explain the problem instead, to get the answer -->

> **Note**: This article was a collaborative effort between a human and an AI, highlighting the power of collaboration between developers and AI in shaping the future of software development.




<!-- This tool is an AI-powered pair programmer that helps you write code faster and with less effort. It is powered by OpenAI's GPT-3, a powerful language prediction model. This tool is integrated with Visual Studio Code and GitHub Codespaces, and it can be used with other editors through the GitHub Copilot extension. -->

<!-- In the ever-evolving world of technology, have you ever wondered how Artificial Intelligence (AI) could revolutionize the way we approach software development? AI has emerged as a powerful tool that empowers developers to enhance their skills and capabilities. With its wide range of possibilities and applications, AI is transforming the way we approach development tasks, unlocking new opportunities for innovation. Although the fast pace of AI progress may render this article outdated soon, it serves as an excellent starting point for understanding the current state of AI and its potential to enhance the developer experience.

## Unleashing the Power of Teamwork: An Introduction to Pair Programming

Pair programming, a widely adopted practice in the industry, exemplifies the power of teamwork in creating high-quality code. It involves two developers working together on the same task, sharing a single workstation. By combining their skills, knowledge, and perspectives, they collaboratively solve problems, write code, and improve the overall software design. This practice not only enhances the development process but also promotes learning, knowledge transfer, and the production of robust and maintainable code.

## Unleashing the Power of AI in Pair Programming

AI pair programming combines the expertise of human developers with the capabilities of AI models like OpenAI's GPT-3, a powerful language prediction model. This collaboration enables a synergistic coding experience. By working together, human developers and AI can tackle complex programming challenges more efficiently, improving code quality, productivity, and learning opportunities. However, it's important to note that AI should be seen as a **Copilot** rather than the main driver. AI is not here to replace human developers, but rather to assist them in becoming more productive and efficient.

### Code Analysis and Bug Resolution: An Illustration

To illustrate the benefits of AI pair programming, let's examine a bug in a React application and demonstrate how AI can quickly resolve it. Consider a scenario where a missing dependency array in the `useEffect` hook results in a component being stuck in a loop. While experienced developers may easily identify and rectify such issues, it serves as a practical example of how AI pair programming can expedite bug-solving. AI-powered tools can quickly identify issues like missing dependency arrays and suggest solutions, enabling developers to resolve bugs efficiently.

In the given React code snippet, the `useEffect` hook lacks a dependency array, causing the effect to be invoked on every render, resulting in an infinite loop. An AI-powered pair programming tool can quickly identify this issue and suggest adding the missing dependency array, allowing the developer to resolve the bug efficiently.

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

By utilizing AI in pair programming, developers can benefit from code analysis and bug resolution capabilities that aid in delivering more efficient and bug-free code.

### Reducing the Learning Curve with AI

AI can significantly reduce the learning curve associated with new technologies. When learning a new framework or language, AI can assist with syntax and code structure, allowing developers to focus on concepts and logic rather than intricate details. For example, in my personal experience, while learning an older version of Ruby on Rails (RoR), I utilized AI to understand the syntax and code structure quickly. This approach expedited my learning process as I could concentrate on grasping the concepts and logic behind the code.

Similarly, tools like GitHub Copilot integrated with code editors can assist developers in understanding language syntax and framework conventions. By leveraging AI, developers can expedite their ability to learn syntax and conventions, ultimately improving the quality of the code they deliver.

### Code Generation and Snippet Suggestions: AI at Work

Another valuable application of AI in pair programming is code generation. Tools like GitHub Copilot can generate code snippets based on the context and requirements, accelerating the development process. For instance, in Ruby, using a comment to ask for the desired output or functionality can prompt Copilot to generate the corresponding code snippet. Here's an example:

```ruby
# Returns the name of the user
def name
  @name
end

# Generate expect for url that matches users/gabssanto?secret_key= but secret key is variable
expect(url).to match(/users\/gabssanto\?secret_key=(.*)/)
```

In React development, Copilot excels at generating code templates for common scenarios, such as a `useEffect` hook with a dependency array. Here's an example:

```javascript
useEffect(() => {
  // Code here
}, []); // Dependency array
```

By using AI-generated code snippets as a starting point, developers can save time and effort, allowing them to focus on refining and specifying the code for their specific needs.

### Competitive Advantage through AI Expertise

As AI continues to advance, leveraging its power to enhance developers' productivity will become a competitive advantage. The ability to effectively utilize AI tools will differentiate developers in the future, enabling them to deliver more value to their organizations. Similar to the significance of proficiently searching on Google today, AI expertise will be a skill that significantly impacts day-to-day work. Mastering AI applications will empower developers to excel and stand out in their roles.

## AI in Teaching Computer Science: A New Approach

AI can also play a role in teaching computer science. For example, students can use AI models like OpenAI's GPT-3 to ask questions and gain a deeper understanding of concepts and problem-solving techniques. However, in teaching scenarios, it's important to establish boundaries and guidelines to ensure that students actively engage in problem-solving rather than relying solely on AI-generated code. One approach is to present the AI as a "Professor" who can provide mental models and explanations without directly giving solutions or code. This encourages students to develop their problem-solving skills and fosters a deeper understanding of the subject matter.

## Conclusion: Embracing the Future of Software Development

In conclusion, AI pair programming is a collaborative approach that combines the expertise of human developers with the analytical power of AI models. By working in tandem, developers and AI can enhance problem-solving abilities, accelerate learning curves, and deliver high-quality code more efficiently. The fusion of human ingenuity and AI's capabilities paves the way for groundbreaking advancements in software development. Embracing AI pair programming will be essential for developers who strive to stay ahead in an increasingly competitive industry.
 -->
