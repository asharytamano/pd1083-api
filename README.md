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

⚖️ Disclaimer

This project is for educational and research purposes only.
It is not a substitute for legal advice from accredited Shariah lawyers or judges.
