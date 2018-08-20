# Git Filter Branch demo

Wanna see filter branch work?

- clone this repo
- run `git blame numbers.txt` and see that it is made of two commits
- run `git checkout -b filter-branch-demo`
- run
    ```
    git filter-branch --tree-filter "sed -i '' 's/    /  /' numbers.txt"
    ```

At this point you can run `git blame numbers.txt` and see that it is still made of two commits but their hashes have changed. And run `git diff master` and see that the file whitespace has been changed.

The filter-branch command steps through each commit, applies the filter (in this case the `sed` command), and stores the result as though that were the original commit.

# References

- https://manishearth.github.io/blog/2017/03/05/understanding-git-filter-branch/
- https://git-scm.com/docs/git-filter-branch

