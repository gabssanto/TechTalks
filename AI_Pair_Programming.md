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
  
    const interval = setInterval(fetchData, 500); // Fetch data every 5 seconds

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
