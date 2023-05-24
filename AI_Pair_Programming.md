# Introduction
> This article is something that will quickly be outdaded due to |the fast pacing progress of AI, but it is a good starting point to understand the current state of AI and how it can be used to enhance the developer experience.

In today's rapidly evolving technological landscape, Artificial Intelligence (AI) has become a powerful tool that empowers developers to enhance their skills and capabilities. AI brings a wide range of possibilities and applications, revolutionizing the way we approach development tasks and unlocking new opportunities for innovation.


# AI Pair Programming

## Code analysis

### React Bug Hunt Example

Here I show how to use pair programming to solve a bug in a React application. The bug is that the component is in a loop due to the missing dependency array in the `useEffect` hook. The solution is to add the dependency array. This is an easy case scenario for an experienced developer, but it is a good example to show how AI pair programming can be used to quickly solve bugs, note that for even experienced developers, smalls mistakes like that are pretty common.

[Running Example](https://1482073.playcode.io/)
<details>
  <summary>Code</summary>

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
        setCounter(counter + 1)
      } catch (error) {
        console.log('Error fetching data:', error);
      }
    };

    fetchData();

    const interval = setInterval(fetchData, 500); // Fetch data every 0.5 seconds

    return () => clearInterval(interval);
  }); // No dependency array (infinite loop)

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

export default App;
```
</details>

## Learning curve reduction

It is possible to use AI to reduce the learning curve of new technologies. For example, if you are learning a new framework, you can use AI to help you with the syntax and the structure of the code. This is a great way to learn new technologies, as you can focus on the concepts and the logic behind the code, instead of worrying about the syntax and the structure of the code.



To bring a personal example, on work, I had to work on a project which uses Ruby On Rails (RoR), which on the specific version (4.x.x) that the project was using, it was very different from the current version. I had to learn RoR 4.x.x, and I used AI to help me with the syntax and the structure of the code. This was a great way to learn RoR 4.x.x, as I could focus on the concepts and the logic behind the code, instead of worrying about the syntax and the structure of the code.

Another example that I can bring quickly is using Github Copilot, which is integrated with my current Editor (Visual Studio Code), to help me find regex as needed. This is a great use for AI, as I can focus on the logic behind the regex, instead of worrying about the syntax and the structure of the regex.

By AI here I mean Chat GPT and Bing Chat to understand the syntax and conventions of the language and the framework. This helped me to quickly learn the syntax and conventions, and improve the code that I could deliver to the project.

## Code generation

It is possible to use also new elements like Github's Copilot X to generate code. Let's imagine a controller in Ruby on Rails, we can use it to create a RSpec test for that controller. This is a great way to speed up the development process, as it can generate a lot of code for you, and you can work on specifying each scenarios better later coding by yourself, but it's a great bootstrap to start with.

## Competitive advantage

As AI's get more and more powerful, it will become a competitive advantage to use it's powers to enable developers to be more productive. I believe that this will be a key factor for developers to differentiate themselves in the future, as one that can properly use AI to enhance their skills and capabilities will be able to deliver more value to the company. I believe that this will be more or like the same as knowing how to properly search on google is today, it is a skill that is not directly related to the job, but it is a skill that makes a huge difference in day to day work.
