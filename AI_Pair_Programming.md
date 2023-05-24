# Introduction
> This article is something that will quickly be outdaded due to |the fast pacing progress of AI, but it is a good starting point to understand the current state of AI and how it can be used to enhance the developer experience.

In today's rapidly evolving technological landscape, Artificial Intelligence (AI) has become a powerful tool that empowers developers to enhance their skills and capabilities. AI brings a wide range of possibilities and applications, revolutionizing the way we approach development tasks and unlocking new opportunities for innovation.


# AI Pair Programming
## React Bug Hunt

Here I show how to use pair programming to solve a bug in a React application. The bug is that the component is in a loop due to the missing dependency array in the `useEffect` hook. The solution is to add the dependency array. This is an easy case scenario for an experienced developer, but it is a good example to show how AI pair programming can be used to quickly solve bugs, note that for even experienced developers, smalls mistakes like that are pretty common.

[Running Example](https://1482073.playcode.io/)

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
