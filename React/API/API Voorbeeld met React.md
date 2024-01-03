Bronnen:
https://www.geeksforgeeks.org/reactjs-ajax-and-api/
https://www.freecodecamp.org/news/how-to-consume-rest-apis-in-react/

Om gegevens van een **API** op te halen in een **ReactJS**-applicatie, kun je gebruik maken van **AJAX** of **Fetch API** [1](https://www.freecodecamp.org/news/how-to-consume-rest-apis-in-react/)[2](https://www.geeksforgeeks.org/reactjs-ajax-and-api/).

Met behulp van AJAX kun je asynchroon gegevens ophalen van een server en deze gebruiken om de inhoud van een webpagina dynamisch bij te werken zonder de hele pagina te hoeven vernieuwen [1](https://www.freecodecamp.org/news/how-to-consume-rest-apis-in-react/). Fetch API is een browser-API die het mogelijk maakt om HTTP-verzoeken te doen vanuit JavaScript [1](https://www.freecodecamp.org/news/how-to-consume-rest-apis-in-react/).

Om **RESTful API’s** te consumeren in React, kun je gebruik maken van **Axios** of **Fetch API** [1](https://www.freecodecamp.org/news/how-to-consume-rest-apis-in-react/). Axios is een promise-based HTTP-client voor het maken van HTTP-verzoeken vanuit JavaScript [1](https://www.freecodecamp.org/news/how-to-consume-rest-apis-in-react/). Fetch API is een browser-API die het mogelijk maakt om HTTP-verzoeken te doen vanuit JavaScript [1](https://www.freecodecamp.org/news/how-to-consume-rest-apis-in-react/).

Hier is een voorbeeld van hoe je een **RESTful API** kunt consumeren in React met behulp van **Axios**:

```javascript
import React, { useState, useEffect } from 'react';
import axios from 'axios';

function App() {
  const [data, setData] = useState([]);

  useEffect(() => {
    const fetchData = async () => {
      const result = await axios(
        'https://jsonplaceholder.typicode.com/posts',
      );

      setData(result.data);
    };

    fetchData();
  }, []);

  return (
    <div>
      <ul>
        {data.map(item => (
          <li key={item.id}>
            <h3>{item.title}</h3>
            <p>{item.body}</p>
          </li>
        ))}
      </ul>
    </div>
  );
}

export default App;
```

Dit voorbeeld haalt gegevens op van de **JSONPlaceholder API** en toont deze op de pagina [1](https://www.freecodecamp.org/news/how-to-consume-rest-apis-in-react/).

Als je meer wilt weten over het integreren van API’s met ReactJS, dan raad ik je aan om de volgende links te bekijken [1](https://www.freecodecamp.org/news/how-to-consume-rest-apis-in-react/)[3](https://clouddevs.com/react/guide-to-integrating-apis-with-reactjs/)[2](https://www.geeksforgeeks.org/reactjs-ajax-and-api/). Ze bevatten stapsgewijze handleidingen over hoe je API’s kunt integreren in ReactJS.