

## Preparation - Creating a Merge Conflict

### Making Fixes in a New Branch

1. **Start from the `add-quotes` branch:**
   ```sh
   git checkout add-quotes
   ```

2. **Create a new branch `fix-quotes` and switch to it:**
   ```sh
   git checkout -b fix-quotes
   ```

3. **Make changes in your files:**
   - Fix the typo in the quote about a good programmer (change "crosing" to "crossing").
   - Remove the empty `test.txt` file.
   - Add a new `simplicity.txt` file with the following sentence:
     ```
     "Simplicity is the soul of efficiency." - Austin Freeman
     ```

4. **Commit your changes:**
   ```sh
   git add programmer.txt simplicity.txt
   git rm test.txt
   git commit -m "Fix typo, remove test.txt, add simplicity.txt"
   ```

5. **Push `fix-quotes` to GitHub:**
   ```sh
   git push --set-upstream origin fix-quotes
   ```

6. **Open a new pull request (from `fix-quotes` to `dev` branch):**
   - Title: `Pull request from fix-quotes to dev branch`

   **Keep this pull request open.**

### Introducing Changes in the First Branch

1. **Make sure that you are in the `add-quotes` branch:**
   ```sh
   git checkout add-quotes
   ```

2. **Make a change in the quote about a good programmer:**
   - Add its author: Doug Linder

3. **Add a `simplicity.txt` file with the following sentence:**
   ```
   "Nature is pleased with simplicity. And nature is no dummy." - Isaac Newton
   ```

4. **Commit your changes:**
   ```sh
   git add programmer.txt simplicity.txt
   git commit -m "Add author to quote, add new simplicity.txt with Isaac Newton quote"
   ```

5. **Push `add-quotes` to GitHub:**
   ```sh
   git push --set-upstream origin add-quotes
   ```

## Merging Pull Requests

1. **First, merge your pull request from the `fix-quotes` branch (it should be pull request #2).**

2. **Then, go to your pull request from the `add-quotes` branch (it should be pull request #1).**
   - Merge option should be disabled, and you should see the list of conflicts.
   - Merge button disabled due to conflicts.

### Instructions

Now it is time to solve the conflict. Do it by using the command line.

1. **Make sure that your `dev` branch is up-to-date:**
   ```sh
   git checkout dev
   git pull
   ```

2. **Switch to the `add-quotes` branch:**
   ```sh
   git checkout add-quotes
   ```

3. **Try to merge the `dev` branch:**
   ```sh
   git merge dev
   ```
   - You should see this message about a merge conflict:
     ```
     "Automatic merge failed; fix conflicts and then commit the result."
     ```

4. **Check the status of your files to have clear information:**
   ```sh
   git status
   ```
   - You should see the following message indicating a conflict.

5. **Open the conflicting files and decide which changes should stay.**

6. **Commit your changes:**
   ```sh
   git add <FILE NAMES>
   git commit
   ```
   - Git is smart enough to create a merge commit message for you in this case.

7. **Push your changes to GitHub:**
   ```sh
   git push
   ```

8. **Check your pull request. Now you should be able to merge your pull request from the `add-quotes` branch.**
