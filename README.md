Slydo API Docs
========

[Slydo is a new kind of payment solution](https://slydo.co).

This is the public repo for the [Slydo API documentation](https://docs.slydo.co). 
It was generated using [Slate](https://github.com/lord/slate).

Testing Locally
-----------------------
You'll need Docker.

From the root of the repo:
```
> docker build -t slydo-api-doc:v1 .
```

And run it, forwarding the port, including the image name and version:
```
> docker run -p 4567:4567 slydo-api-doc:v1
```

Then just visit http://localhost:4567 in your browser!


Need help? Found a bug?
-----------------------

Just [submit an issue](https://github.com/slydo/docs/issues) to this GitHub repo if you need any help. And, of course, 
feel free to submit pull requests with bug fixes or changes.
