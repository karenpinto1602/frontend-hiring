# frontent-hiring

Creating Fake API's using JSONPlaceholder

### To run locally

```npm i```

```npm run json:server```

### Localhost

http://localhost:3000/faq <br/>

http://localhost:3000/events 


### Remote Links: 

FAQs: https://karenpinto1602.github.io/frontent-hiring/faq.json <br />

Events: https://karenpinto1602.github.io/frontent-hiring/events.json <br />

### Example to access the data using react axios from faq.json

```
import React from 'react';
import Axios from 'axios';
import { useState } from 'react';

function Sample() {
    const url = 'https://karenpinto1602.github.io/frontent-hiring/faq.json';

    const [faqs, setFaqsData] = useState();

    //Get data
    function getCards(e) {
        Axios.get(url)
            .then(response => {
                setFaqsData(response.data)
                // collective data
                console.log(faqs);

                // display only questions
                faqs.map(faq => {
                    return console.log(faq.question);
                })
            })
            .catch(error => {
                console.log(error)
            })
    }

    //Post data
    // Strictly informative, NOT TO BE TOUCHED BY THE INTERNS
    function submit(e) {
        Axios.post(jobs_url, {
            "question" : "What is you Name?",
            "answer" : "My Name is XZY"
        })
            .then(res => {
                console.log("SUCCESS POST")
            })
            .catch(error => {
                console.log("Error in POST: " + error)
            })
    }
    
}
export default Sample;

```