# my-test-build-with-token

```
"package-name": "git+https://<github_token>:x-oauth-basic@github.com/<user>/<repo>.git"
```

####generate token wit repository rights

####Install dependency
```
  npm install --loglevel verbose --save git+https://x-oauth-basic@github.com/oliverreese/my-private-dependency.git
```

####package.json
```
  "dependencies": {
    "express": "^4.17.1",
    "@oliverreese/my-private-dependency": "git+https://x-oauth-basic@github.com/oliverreese/my-private-dependency.git"
  }
```



####Dockerfile
```
ARG GITHUB_TOKEN

RUN git config --global url."https://${GITHUB_TOKEN}:x-oauth-basic@github.com/".insteadOf https://x-oauth-basic@github.com/

```


####Docker build/run
```
docker build --build-arg GITHUB_TOKEN=yourprivategithubtoken -t oliverreese/my-test-build-with-token .

docker run -p 8000:8080 -d oliverreese/my-test-build-with-token

```

####docker-compose
```
docker-compose up --build
```

  
