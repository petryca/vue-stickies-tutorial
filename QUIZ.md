# Vue.js Sticky Notes Tutorial - Quiz Worksheet

## Instructions
Create a new file called `answers.md` and answer the following questions based on your understanding from the tutorial. Write clear, concise answers in your own words. Include code examples where appropriate.

---

## HTML & Meta Tags (Questions 1-5)

1. **Explain what `<meta name="viewport" content="width=device-width, initial-scale=1">` does and why it's important for modern web development.**

2. **What is the purpose of the `lang="en"` attribute in the `<html>` tag?**

3. **In the tutorial, we use `<main id="app">` as our container. What is the semantic meaning of the `<main>` element, and why is it better than using a `<div>`?**

4. **Explain what the `draggable="true"` attribute does on an HTML element.**

5. **Why do we include Vue.js using a `<script>` tag at the bottom of the body, rather than in the `<head>`?**

---

## CSS Fundamentals (Questions 6-15)

6. **Explain what `box-sizing: border-box;` does and why it's applied to the `*` selector.**

7. **What is the difference between `rem` and `px` units? Why does the tutorial use `rem` for most measurements?**

8. **Explain how the CSS Grid properties work in this code:**
   ```css
   display: grid;
   grid-template-columns: repeat(4, 1fr);
   grid-auto-rows: 1fr;
   gap: 1rem;
   ```

9. **What does the `1fr` unit mean in CSS Grid?**

10. **Explain how these media queries create a responsive design:**
    ```css
    @media (max-width: 1120px) {
      main {
        grid-template-columns: repeat(3, 1fr);
      }
    }
    ```

11. **What does `transition: all 0.3s;` do? Give an example of when this transition would be visible in the app.**

12. **Explain what `transform: scale(1.4)` does and when it's applied in our sticky notes app.**

13. **Why does the tutorial use `resize: none;` on the textarea elements?**

14. **What is the purpose of `outline: none;` and what accessibility concerns might this raise?**

15. **Explain the visual effect created by these two classes working together:**
    ```css
    .dragging { opacity: 0.5; transform: rotate(2deg); }
    .drag-over { transform: scale(1.05); }
    ```

---

## Vue.js Directives (Questions 16-25)

16. **Why do some Vue directives start with `@` and some with `:` ? What is the difference between them?**

17. **Explain what `v-for="(stickie, index) in stickies"` does and why we need the `index`.**

18. **What is the purpose of `:key="index"` when using `v-for`?**

19. **Explain how `v-model="stickies[index].text"` creates two-way data binding.**

20. **What does the `.delete` modifier do in `@keyup.delete="deleteStickie(index)"`?**

21. **How does `.alt` work in `@click.alt="changeColor(index)"`, and what key combination does this require?**

22. **Explain the difference between `:style` and `:class` bindings. Give an example of when you'd use each.**

23. **What does this conditional class binding do: `:class="{ 'dragging': draggedIndex === index }"`?**

24. **If you wanted to listen for the Enter key being pressed, what directive would you use?**

25. **What's the difference between `@click` and `@click.prevent`?**

---

## JavaScript & Array Methods (Questions 26-35)

26. **What does the `push()` method do? How is it used in the `addStickie()` function?**

27. **Explain how `splice()` is used differently in these two scenarios:**
    - `this.stickies.splice(index, 1)`
    - `this.stickies.splice(targetIndex, 0, draggedItem)`

28. **What does `Date.now()` return and why is it useful for creating unique IDs?**

29. **Explain what the `trim()` method does in this code: `this.stickies[index].text.trim() === ''`**

30. **What does the modulo operator (`%`) do in this code:**
    ```javascript
    const newColorIndex = (currentIndex + 1) % colors.length;
    ```

31. **Explain the difference between `JSON.stringify()` and `JSON.parse()`. When do we use each in this app?**

32. **What is the purpose of the `try...catch` block in the storage methods?**

33. **In the drag and drop code, why do we use `[0]` here:**
    ```javascript
    const draggedItem = this.stickies.splice(this.draggedIndex, 1)[0];
    ```

34. **What does `indexOf()` return if the item is not found in the array?**

35. **Why is `event.preventDefault()` necessary in the drag and drop methods?**

---

## Vue.js Application Structure (Questions 36-45)

36. **Why must `data()` be a function that returns an object, rather than just an object?**

37. **What is the difference between the `mounted()` lifecycle hook and the `created()` hook? (You may need to research this)**

38. **Explain when code should go in `methods:` versus when it should go in `watch:`.**

39. **What does `deep: true` do in a watcher, and why is it necessary for watching the `stickies` array?**

40. **How do you access data properties from within a method? Give an example.**

41. **What does `.mount('#app')` do at the end of the Vue application?**

42. **If you wanted to compute the total number of notes dynamically, would this go in `data()`, `methods:`, or `computed:`? Explain why.**

43. **What happens if you forget to return an object from the `data()` function?**

44. **How would you call one method from inside another method in Vue?**

45. **What is the purpose of using `this.` before properties and methods in Vue?**

---

## Browser APIs & Events (Questions 46-50)

46. **What is `localStorage` and what are its limitations?**

47. **Explain what these DataTransfer properties do:**
    - `event.dataTransfer.effectAllowed`
    - `event.dataTransfer.dropEffect`

48. **What is the difference between `dragenter` and `dragover` events?**

49. **Why do we need to handle both `@dragover` and `@drop` events for drag and drop to work?**

50. **What would happen if we didn't remove the 'dragging' class in the `onDragEnd` method?**

---

## Problem Solving & Code Analysis (Questions 51-60)

51. **The delete functionality only works when the note is empty. How would you modify the code to delete a note when pressing Delete regardless of content?**

52. **Currently, the color change cycles through colors in order. How would you modify `changeColor()` to pick a random color instead?**

53. **What would happen if two notes were created at the exact same millisecond? How could you ensure truly unique IDs?**

54. **The current auto-save triggers on every keystroke. How could you implement a "debounced" save that only saves after the user stops typing for 1 second?**

55. **How would you add a feature to display the character count for each note?**

56. **What changes would be needed to limit users to a maximum of 20 sticky notes?**

57. **How would you implement an "undo" feature for the last deleted note?**

58. **What's a potential security concern with using `v-html` instead of `v-model` for the notes? (Research if needed)**

59. **How would you modify the code to always show the "Add" button in the last position?**

60. **Design a data structure for adding tags to each note. What would the modified `stickies` array look like?**

---

## Bonus Challenge

61. **Explain how you would add a dark mode toggle to this application.**

---

## Submission Guidelines

- Save your answers in a file called `answers.md`
- Use proper Markdown formatting: 
    - [Markdown Cheat Sheet](https://www.markdownguide.org/cheat-sheet/) 
    - [GitHub Markdown Guide](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
- Include code blocks
- For coding questions, provide working examples
- Explain your reasoning, don't just give one-word answers

Good luck! Remember, the goal is to demonstrate your understanding of the concepts, not just to get the "right" answer.