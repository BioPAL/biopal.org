# Biopal website

This repository contains the material that will be published on biopal.org
Static web pages are produced by Hugo, using [Docsy](https://github.com/google/docsy) theme.

Docsy is a Hugo theme for technical documentation sites, providing easy site navigation, structure, and more.
The theme is included in this project as a Git submodule:

```bash
▶ git submodule
 a053131a4ebf6a59e4e8834a42368e248d98c01d themes/docsy (heads/master)
```

You can find detailed theme instructions in the Docsy user guide: https://docsy.dev/docs/

## Contributing

1. Make your own local working copy of this repo using git clone:

```bash
git clone --recurse-submodules --depth 1 https://github.com/BioPAL/biopal.org.git
```

You can now edit your own versions of the site’s source files.

If you want to do SCSS edits and want to publish these, you need to install `PostCSS`

```bash
npm install
```

## Running the website locally

Building and running the site locally requires a recent `extended` version of [Hugo](https://gohugo.io).
You can find out more about how to install Hugo for your environment on
[Hugo](https://gohugo.io/getting-started/installing) web pages.

Once you've made your working copy of the site repo, from the repo root folder, run:

```
hugo server
```

## Running a container locally

You can run biopal.org inside a [Docker](https://docs.docker.com/)
container, the container runs with a volume bound to the `docsy-example`
folder. This approach doesn't require you to install any dependencies other
than [Docker Desktop](https://www.docker.com/products/docker-desktop) on
Windows and Mac, and [Docker Compose](https://docs.docker.com/compose/install/)
on Linux.

1. Build the docker image 

   ```bash
   docker-compose build
   ```

1. Run the built image

   ```bash
   docker-compose up
   ```

   > NOTE: You can run both commands at once with `docker-compose up --build`.

1. Verify that the service is working. 

   Open your web browser and type `http://localhost:1313` in your navigation bar,
   This opens a local instance of the docsy-example homepage. You can now make
   changes to the docsy example and those changes will immediately show up in your
   browser after you save.

### Cleanup

To stop Docker Compose, on your terminal window, press **Ctrl + C**. 

To remove the produced images run:

```console
docker-compose rm
```
For more information see the [Docker Compose
documentation](https://docs.docker.com/compose/gettingstarted/).

## Troubleshooting

As you run the website locally, you may run into the following error:

```
➜ hugo server

INFO 2021/01/21 21:07:55 Using config file: 
Building sites … INFO 2021/01/21 21:07:55 syncing static files to /
Built in 288 ms
Error: Error building site: TOCSS: failed to transform "scss/main.scss" (text/x-scss): resource "scss/scss/main.scss_9fadf33d895a46083cdd64396b57ef68" not found in file cache
```

This error occurs if you have not installed the extended version of Hugo.
See our [user guide](https://www.docsy.dev/docs/getting-started/) for instructions on how to install Hugo.


## Build the html site to be uploaded 

To generate the html static website to be uploaded on the server, simply digit following command:
   ```bash
   hugo
   ```
The html static website will be produced in *public/* folder.

The current configuration present in *config.toml* is set to produce a website with correct paths working when uploaded.

To reproduce instead the static website browsable from a local file system, use folowing flags in *config.toml*:
   ```bash
      baseURL = "/"
      relativeURLs = true
      uglyURLs = true
      canonifyURLs = false
   ```