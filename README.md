### README.md

Use Go with Heroku

- [getting started with Go](https://mmcgrana.github.io/2012/09/getting-started-with-go-on-heroku.html)

### Steps

```
heroku create -b https://github.com/kr/heroku-buildpack-go.git
```

Then what you will get will be something like

```
$heroku create -b https://github.com/kr/heroku-buildpack-go.git
Creating ancient-wave-7514... done, stack is cedar-14
Buildpack set. Next release on ancient-wave-7514 will use https://github.com/kr/heroku-buildpack-go.git.
https://ancient-wave-7514.herokuapp.com/ | https://git.heroku.com/ancient-wave-7514.git

$heroku apps
=== My Apps
ancient-wave-7514
```

### Tips

- Use [heroku accounts](#) to make it work with Heroku
- http://blog.wercker.com/2013/07/10/deploying-golang-to-heroku.html
- https://github.com/bgentry/heroku-go
- http://www.zhubert.com/blog/2014/02/11/setting-up-go/
- http://www.zhubert.com/blog/2014/03/08/deploying-golang-to-heroku/
- https://github.com/zhubert/speedy-bible
- https://github.com/zhubert/go-search
