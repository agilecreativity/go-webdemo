### README.md

My first example of how to use Go with Heroku

Based on the following tutorial [getting started with Go][]

### Deploy and run locally

```
$git clone https://github.com/bchoomnuan/webdemo.git
$cd webdemo
$go build

## Then to run the code locally
$PORT=3000 ./webdemo
```

Open your browser to `http://localhost:300` should give you back 'hello world'

Test via `curl`

```
$curl -I http://localhost:3000

HTTP/1.1 200 OK
Date: Sun, 22 Feb 2015 06:23:47 GMT
Content-Length: 12
Content-Type: text/plain; charset=utf-8
```

### Deploy to Heroku

Now we know that the app is running locally, we are now ready to deploy this to Heroku

```sh
## Login to Heroku
$heroku login

## Create the new Heroku app using Go buildpack
$heroku create -b https://github.com/kr/heroku-buildpack-go.git

## Show the app name (take note for the next step)
$heroku apps --apps

## You are now ready to push deploy the code to Heroku
$git push heroku master
```

You should get the output similar to the following session:

```
# Note: I am using --force option with Git
$ git push heroku +master                                                                                                                 1 ↵
Counting objects: 3, done.
Delta compression using up to 8 threads.
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 624 bytes | 0 bytes/s, done.
Total 3 (delta 2), reused 0 (delta 0)
remote: Compressing source files... done.
remote: Building source:
remote:
remote: -----> Fetching custom git buildpack... done
remote: -----> Go app detected
remote: -----> Using go1.4.1
remote: -----> Running: go get -tags heroku ./...
remote: -----> Discovering process types
remote:        Procfile declares types -> web
remote:
remote: -----> Compressing... done, 3.3MB
remote: -----> Launching... done, v8
remote:        https://vast-sierra-8530.herokuapp.com/ deployed to Heroku
remote:
remote: Verifying deploy... done.
To https://git.heroku.com/vast-sierra-8530.git
 + ccf2fec...a01b6e9 master -> master (forced update)
```

If you do everything correctly, you should be able to access the result in your
browser like so

```
## Open the app in your browser
$heroku open --apps <YOUR-HEROKU-APP-NAME>

## e.g. In this example we need to use
$heroku open --apps vast-seirra-8530
```

### Links & Resources

- Use [heroku accounts][] to make it work with Heroku
- http://blog.wercker.com/2013/07/10/deploying-golang-to-heroku.html
- https://github.com/bgentry/heroku-go
- http://www.zhubert.com/blog/2014/02/11/setting-up-go/
- http://www.zhubert.com/blog/2014/03/08/deploying-golang-to-heroku/
- https://github.com/zhubert/speedy-bible
- https://github.com/zhubert/go-search

[getting started with Go]: https://mmcgrana.github.io/2012/09/getting-started-with-go-on-heroku.html
[heroku accounts]: https://github.com/ddollar/heroku-accounts
