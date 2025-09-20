PD 1083 API

This repository hosts the Code of Muslim Personal Laws of the Philippines (Presidential Decree No. 1083) in JSON format. It provides an article-by-article structure for study, research, and integration into applications, bots, or GPTs.

📂 Files

pd1083_hierarchical.json → Nested structure (Book → Title → Chapter → Section → Articles)

pd1083_index.json → Table of contents with article ranges

pd1083_flat_complete.json → Flat structure (easy to query by article number)

🌐 API Access

Once GitHub Pages is enabled for this repository, your JSON files will be accessible at:

https://<username>.github.io/pd1083-api/pd1083_flat_complete.json


Example request using curl:

curl https://<username>.github.io/pd1083-api/pd1083_flat_complete.json

🔍 Example Usage

Fetch Article 34 from the flat JSON file in JavaScript:

fetch("https://<username>.github.io/pd1083-api/pd1083_flat_complete.json")
  .then(res => res.json())
  .then(data => {
    const article = data.articles.find(a => a.article_number === 34);
    console.log(article.text);
  });

⚡ Helper Function

You can use this function to easily fetch any article by number:

async function getArticle(articleNumber) {
  const res = await fetch("https://<username>.github.io/pd1083-api/pd1083_flat_complete.json");
  const data = await res.json();
  return data.articles.find(a => a.article_number === articleNumber);
}

// Example:
getArticle(10).then(article => console.log(article.text));

🤖 Using with GPT Actions

You can connect this API to a custom GPT in ChatGPT Builder.
Define an Action schema like this:

{
  "name": "get_pd1083_article",
  "description": "Retrieve text of a specific Article from PD 1083",
  "parameters": {
    "type": "object",
    "properties": {
      "article_number": {
        "type": "integer",
        "description": "The Article number from PD 1083 to retrieve"
      }
    },
    "required": ["article_number"]
  }
}


Your GPT can then fetch pd1083_flat_complete.json, search for the requested article_number, and return the text with explanations, reviewers, or case notes.

⚖️ Disclaimer

This project is for educational and research purposes only.
It is not a substitute for legal advice from accredited Shariah lawyers or judges.
