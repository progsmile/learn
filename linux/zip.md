Create zip ignoring directories
```bash
zip -r project.zip project/ -x "project/.git/*" -x "project/.idea/*" -x "project/node_modules/*" -x "project/vendor/*"
```

