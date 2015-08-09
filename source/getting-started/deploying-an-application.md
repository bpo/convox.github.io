---
title: "Deploying an Application"
---
Applications can be deployed to Convox via the `convox deploy` [CLI](https://github.com/convox/cli) command.

## Deploying an example app

To quickly see Convox deployment in action, you can clone one of our [example apps](https://github.com/convox-examples).

```shell
$ git clone git@github.com:convox-examples/sinatra.git
```

Change into the sinatra directory and deploy the application.

```shell
$ cd sinatra
$ convox apps create
$ convox deploy
```

## Deploying your own app

Deploying your app on Convox is easy. To deploy, simply run:

```shell
$ cd ~/myapp
$ convox apps create myapp
$ convox deploy --app myapp
```


<div class="block-callout block-show-callout type-info">
### App Names
Passing an app name with `--app` is optional. If you do not provide one, the name of your current directory will be used as the app name.

App names can be made up of alphanumeric characters and dashes.
</div>

When you create a new app, Convox provisions all of the AWS infrastructure required to support your app. This will take a few minutes.

The first deployment can also be a little slow as all of the Docker images are built. Subsequent deploys of the same app will be significantly faster since they will take advantage of Docker layer caching.

The Convox CLI will print live updates as the deployment proceeds:

```shell
$ convox deploy --app myapp
Uploading... OK
RUNNING: docker build -t xmjsczmcug /tmp/repo044075326/clone
Sending build context to Docker daemon 92.16 kB
Sending build context to Docker daemon
Step 0 : FROM ruby:2.2.2
2.2.2: Pulling from ruby
...
```

when the build finishes the release ID will be shown.

```shell
Releasing... OK, RANLOWQFMRF
```

If necessary, the CLI will also wait for the app's load balancer to become available.

```shell
Waiting for app...
```

When the load balancer becomes available the deploy is finished. Any processes with open ports will be listed.

```shell
main: http://myapp-62376059.us-east-1.elb.amazonaws.com:5000
```