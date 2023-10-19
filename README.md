# leetcode_sol

clean outputs in all jupyter notebooks:

```
jupyter nbconvert --ClearOutputPreprocessor.enabled=True --inplace ./*.ipynb`
```

# renormalization notebooks

Step 1. Add to `.git/config`


```
[filter "strip-notebook-output"]
clean = "jupyter nbconvert --ClearOutputPreprocessor.enabled=True --ClearMetadataPreprocessor.enabled=True --to=notebook --stdin --stdout --log-level=ERROR"
smudge = "cat"
required
```

Step 2. Create `.git/info/attributes` and add:

```
*.ipynb filter=strip-notebook-output
```

Step 3. Do renormalization:
```
git add --renormalize .
```