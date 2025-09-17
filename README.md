# Merge Conflicts Demo

1. **Set the Scene**

   - Repo setup: Start with a small, simple repo.
   - Branches: Ask Anne to create a new feature branch.
   - File choice: Pick one line of text you both will edit.

2. **Trigger the Conflict**

   - Anne (on feature branch):
     1. Edit the paragraph on line 14 to read, "This project is super cool — Anne’s edit.”
     2. Commit and push to her branch.
   - You (on main):
     1. Edit the same line to say “This project is awesome — Ciso’s edit.”
     2. Commit and push to main.

   Now you have divergent changes on the same line.

3. **Attempt the Merge**
   - Anne’s turn again:
     1. From her feature branch, she runs:
     ```bash
     git merge main
     ```
     2. Git detects the conflict and stops.
   - Show the conflict markers inside the file:
     ```txt
     <<<<<<< HEAD
     This project is super cool — Anne’s edit.
     =======
     This project is awesome — Instructor’s edit.
     >>>>>>> main
     ```
4. Resolve Together

   - Open the conflicted file in VS Code (or whatever editor you use).
   - Show the options:
     - Keep Anne’s version,
     - Keep your version, or
     - Combine into a third line.
   - Demonstrate the “combine” option (e.g., “This project is awesome AND super cool — collaborative edit.”).

   Save the file, then:

   ```bash
   git add README.md
   git commit
   git push
   ```

5. Debrief
   - Explain: Conflicts aren’t errors; they’re Git asking you to make a decision.
   - Highlight: The markers, the three options, and the cleanup step.
   - Best practice tips:
     - Pull main often to reduce conflicts.
     - Communicate when editing the same files.
     - Keep PRs small.
