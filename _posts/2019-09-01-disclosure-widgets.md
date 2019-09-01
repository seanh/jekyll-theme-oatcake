Disclosure Widgets: `<details>` and `<summary>`
===============================================

You can create a disclosure widget, allowing some content to be hidden by
closing the widget, by using [the `<details>` tag](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/details):

<details>
  <summary>This is the summary</summary>
  <p>And here are the details:</p>
  <ol>
    <li>Cash on hand: $500.00</li>
    <li>Current invoice: $75.30</li>
    <li>Due date: 5/6/19</li>
  </ol>
</details>

Adding the `open` attribute to the `<details>` tag makes it be open by default:

<details open>
  <summary>This is the summary</summary>
  <p>And here are the details:</p>
  <ol>
    <li>Cash on hand: $500.00</li>
    <li>Current invoice: $75.30</li>
    <li>Due date: 5/6/19</li>
  </ol>
</details>

A `<details>` with no `<summary>` just gets the word "Details" as its summary:

<details>
  <p>And here are the details:</p>
  <ol>
    <li>Cash on hand: $500.00</li>
    <li>Current invoice: $75.30</li>
    <li>Due date: 5/6/19</li>
  </ol>
</details>
