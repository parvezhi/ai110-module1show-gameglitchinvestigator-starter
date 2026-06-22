# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

- What did the game look like the first time you ran it?
- List at least two concrete bugs you noticed at the start  
  (for example: "the hints were backwards").

  When I first ran the game, the UI loaded but the behavior was clearly wrong. The hints did not match my guesses, the score dropped into negative numbers, and the attempts counter didn’t match the debug info. The game also accepted extremely large numbers like 440 without any validation.

**Bug Reproduction Log**

Document at least 3 bugs you found. Add rows as needed.

| Input | Expected Behavior | Actual Behavior | Console Output / Error |
|-------|-------------------|-----------------|------------------------|
| | | | |
| | | | |
| | | | |

| Input     | Expected Behavior                           | Actual Behavior                          | Console |
|-----------|---------------------------------------------|------------------------------------------|---------|
| 440       | Hint says "Too High" / "Go LOWER"           | Hint says "Go HIGHER!"                   | none    |
| 1         | Score stays positive on Easy                | Score becomes negative after few guesses | none    |
| 44        | Attempts left matches debug Attempts value  | Attempts left: 2, debug Attempts: 4      | none    |

---

## 2. How did you use AI as a teammate?

- Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)?
- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).
- Give one example of an AI suggestion that was incorrect or misleading (including what the AI suggested and how you verified the result).

---

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.
- Did AI help you design or understand any tests? How?

---

## 4. What did you learn about Streamlit and state?

- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?

---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
- What is one thing you would do differently next time you work with AI on a coding task?
- In one or two sentences, describe how this project changed the way you think about AI generated code.

One habit I want to reuse is writing simple tests to confirm my fixes. Even as a beginner, tests helped me feel confident that the logic was correct. I also liked using AI to explain confusing code step‑by‑step.

Next time, I would ask the AI more targeted questions instead of broad ones, because specific prompts gave me better results. This project showed me that AI-generated code can look correct but still contain serious logic bugs, so human judgment is always needed.
