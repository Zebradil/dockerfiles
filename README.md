Taskwarrior-web in Docker container
===================================

It runs taswarrior-web and executes `task sync` command every five minutes,

Run
---
```
docker run -d \
    -v `pwd`/.taskrc:/root/.taskrc \
    -v `pwd`/.task:/root/.task \
    -p 5678:5678 \
    zebradil/taskwarrior-web
```

`.taskrc` is required. `.task` is optional, it depends on what is specified in `.taskrc`.

So, run the command above and open http://localhost:5678 in browser.
