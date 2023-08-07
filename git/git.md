## Clone 1 branch with latest depth level

`git clone git@github.com:some/some.git some_v2 --branch=2.0.1 --depth=1`


## Exclude ignored files 

```bash
git rm --cached `git ls-files -ic --exclude-from=.gitignore`
```
