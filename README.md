# affirmations-api

I developed this fetchable API with the intention of making it accessible to anyone in need of positive affirmations. My goal is to offer a tool that can serve as a gentle reminder of one's inherent worth. In a world where we can all benefit from more positivity, I sincerely hope that this API can play a part in reminding others of just that.
### Endpoint: [https://raw.githubusercontent.com/mehmetserdar/affirmations-api/main/affir.json]

## Fetch Random Affirmation
Below is the JavaScript code that can be used to fetch a random affirmation from an API using the fetch function:

```javascript
function getRandomAffirmation() {
  fetch("https://raw.githubusercontent.com/mehmetserdar/affirmations-api/main/affir.json")
    .then(function (response) {
      return response.json();
    })
    .then(function (data) {
      var categories = data.categories;
      var randomCategoryIndex = Math.floor(Math.random() * categories.length);
      var category = categories[randomCategoryIndex];
      var affirmations = category.affirmations;
      var randomAffirmationIndex = Math.floor(Math.random() * affirmations.length);
      var affirmation = affirmations[randomAffirmationIndex];

      var noteContentTextArea = document.getElementById("note-content");
      noteContentTextArea.value = affirmation;
    })
    .catch(function (error) {
      console.log("An error occurred while fetching the random affirmation:", error);
    });
}

document
  .getElementById("random-affirmation-button")
  .addEventListener("click", function () {
    getRandomAffirmation();
  });


```




## Contributing
Additional contributions are welcome. If you know of a positive affirmation that would be useful to add, please contribute to this open-source project.

