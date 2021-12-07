# frontend-hiring

Creating Fake API's using JSONPlaceholder

### To run locally

```npm i```

```npm run json:server```
which runs the db.json file, to access individual json file (faq or events), change the file name in package.json(line 7)

### Localhost

http://localhost:3000/faq <br/>

http://localhost:3000/events <br />

combined: http://localhost:3000/db

### Remote Links: 

FAQs: https://karenpinto1602.github.io/frontend-hiring/faq.json <br />

Events: https://karenpinto1602.github.io/frontend-hiring/events.json <br />

### Example to access the data using react axios from faq.json

```
import React from 'react';
import Axios from 'axios';
import { useState } from 'react';

function Sample() {
    const url = 'https://karenpinto1602.github.io/frontend-hiring/faq.json';

    const [faqs, setFaqsData] = useState();

    //Get data
    function getFAQs() {
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
    function postFAQs() {
        Axios.post(url, {
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
