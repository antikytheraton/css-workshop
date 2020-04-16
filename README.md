# CSS Workshop

# Selectors

## Structure of CSS declaration

Demo: https://codepen.io/no-cheating/pen/NWqZEgP?editors=1100

- <selector> {
  <declarations>
  }
  - Declarations structure:
    <attribute1>: <value1>;
    <attribute2>: <value2>;
    (...)
    <attributeN>: <valueN>;
- Target (select) HTML elements
- HTML structure:
  - It is a tree
  - parent-child relationship
  - ancestor-descendant relationship
    Basic selector types

---

Demo: The same as previous one

- Element
- Class (multiple can be listed with no spaces)
- ID
- Attribute:
  - Simple attribute selector: [attribute]
  - Exact attribute value: [attribute=value]
  - Partial attribute value: [attribute~*^$|value]
- Universal (\*)
  Exercise: https://codepen.io/no-cheating/pen/JjYGjRx?editors=1100
  Combinators

---

Demo: https://codepen.io/no-cheating/pen/abOgQXK?editors=1100

- Combined selectors read from right to left and apply only to the last element
- And (no space)
- Descendant (space)
- Child (>)
- Adjacent sibling (+)
- General sibling (~)
  Exercise: https://codepen.io/no-cheating/pen/LYpGYWo?editors=1100
  Pseudo classes and elements

---

Demo: https://codepen.io/no-cheating/pen/oNXrQKV?editors=1100

- "phantom classes"
- Structural:
  - Apply to the elements itself (not children)
  - :root
  - :first-child, :last-child, :nth-child, :nth-last-child, :only-child
  - :first-of-type, :last-of-type, :nth-of-type, :nth-last-of-type, :only-of-type,
    - :nth-child(even), :nth-child(odd)
- Dynamic:
  - :link, :visited - unvisited and visited link
  - :focus
  - :hover
  - :active
- UI state:
  - :enabled, :disabled
  - :checked
  - :required, :optional
  - :valid, :invalid
  - :in-range, :out-of-range
  - :target
  - and more
- :not
- Pseudo elements:
  - ::before, ::after
  - ::first-letter, ::first-line
    Exercise: https://codepen.io/no-cheating/pen/QWjyWJQ?editors=1100
    Specificity

---

https://codepen.io/no-cheating/pen/vYOqvNB?editors=1100

- Four number list: (inline, id, class, element)
  - inline: inline styles
  - id: Only ID selector
  - class: Class, pseudo class and attribute selectors
  - element: Element and pseudo element selectors
  - Combinators and universal selector don't add specificity
- !important trumps any specificity
- Specifity is hard and leads a lot of problems, which sometimes end up in
  using !important. To prevent those problems one good approach is sticking to
  using class selectors of length 1 at all times.
  - They are precise and don't leak
  - They are easy to overwrite - you just need another class selector of
    length 1 declared later
    Exercise: https://codepen.io/no-cheating/pen/mdeVyem?editors=1100
    Inheritance

---

Demo: https://codepen.io/no-cheating/pen/eYNwbZr?editors=1100

- Only some attributes are inherited
- Inherited values have no specificity (every declaration overwrites them)
  Cascade

---

Demo: https://codepen.io/no-cheating/pen/eYNwbWj?editors=1100

1. Find all selectors matching current element
2. Sort declarations based on !impotrance: !important or not
3. Sort declarations based on origin (in order): author, reader, user agent

- Exception: !importance reader's declarations overwrite anything

4. Sort declarations based on specificity
5. Sort declaraitons based on order they appear

---

### References

[HTML Semantics article](http://nicolasgallagher.com/about-html-semantics-front-end-architecture/)
