# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

- What did the game look like the first time you ran it?
- List at least two concrete bugs you noticed at the start  
  (for example: "the hints were backwards").

When I first ran the game, the UI loaded but the behavior was clearly wrong. The hints did not match my guesses, the score dropped into negative numbers, and the attempts counter didn’t match the debug info. The game also accepted extremely large numbers like 440 without any validation. It was obvious the logic and state handling were broken.

**Bug Reproduction Log**

Document at least 3 bugs you found. Add rows as needed.



| Input | Expected Behavior | Actual Behavior | Console | Suspected Location |
|-------|-------------------|-----------------|---------|--------------------|
| 440 | Hint says “Too High” / “Go LOWER” | Hint says “Go HIGHER!” | none | logic_utils.py / check_guess |
| 1 | Score stays positive on Easy | Score becomes negative | none | app.py scoring block |
| 44 | Attempts left matches debug Attempts | UI shows 2, debug shows 4 | none | app.py session_state handling |

---

## 2. How did you use AI as a teammate?

- Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)?
- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).
- Give one example of an AI suggestion that was incorrect or misleading (including what the AI suggested and how you verified the result).

I used Copilot inside VS Code to understand the logic and help fix the bugs. One correct suggestion was when the AI told me to move the guess‑checking logic into logic_utils.py and fix the comparison so high guesses return “Too High.” I verified this by running pytest and playing the game again.

One incorrect suggestion was when the AI recommended removing the score update line completely. When I tested the game, the score stopped changing, so I knew the suggestion was wrong and I undid it. This helped me learn that AI suggestions must always be tested, not blindly accepted.
---

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.
- Did AI help you design or understand any tests? How?

I decided a bug was fixed only when both pytest passed and the game behaved correctly in Streamlit. One test I ran was checking that a guess higher than the secret returns a “Too High” message. The test passed, and the game also showed the correct hint when I tried it manually.

AI helped me design the pytest test by generating a simple test function that compared the guess and secret. This made it easier to confirm the logic was working.

## 4. What did you learn about Streamlit and state?

- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?

Streamlit reruns the entire script every time the user interacts with the page. Without session state, all variables would reset on every button click. Session state lets the game remember things like score, attempts, and the secret number across reruns.

I would explain it to a friend like this: “Streamlit refreshes the whole page every time you click something, so session state is like a little backpack that saves your variables so they don’t disappear.”

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
- What is one thing you would do differently next time you work with AI on a coding task?
- In one or two sentences, describe how this project changed the way you think about AI generated code.

One habit I want to reuse is writing simple tests to confirm my fixes. Even as a beginner, tests helped me feel confident that the logic was correct. I also liked using AI to explain confusing code step‑by‑step.

Next time, I would ask the AI more targeted questions instead of broad ones, because specific prompts gave me better results. This project showed me that AI-generated code can look correct but still contain serious logic bugs, so human judgment is always needed.
