Overview / How it works
-------------------
Cookiecutter is a command line utility that makes project templating easy. It works by taking variables from a JSON file full of variable and filling them into Jinja syntaxed variable names. The variables in the JSON can be for directory names, file names, and file contents. 

You can use Cookiecutter from a local cookiecutter project (CP) or remotely from a github repo. But keep in mind that cookiecutter will copy the remote CP into your ~/.cookiecutters directory, so once you run cookiecutter on a remote repo, you only have to invoke the local copy.

So instead of doing this:
`cookiecutter git@github.com:myuserid/my-cp.git`

You do this:
`cookiecutter ~/.cookiecutter/my-cp.git`


How To Run
---------

Step 1. Install cookiecutter::
   
   
    $ pip install cookiecutter      

Step 2. Run cookiecutter:: 


    $ cookiecutter https://github.com/pebreo/cookiecutter-hello-world.git

Gotchas
-------
1) When using cookiecutter from a git repo, your top directory (the same level as your cookiecutter.json) should be 
called `{{cookiecutter.repo_name}}`, otherwise you get an error.

```
UPDATE: This is not the case anymore with the newest cookiecutter. 
You can name your top directory whatever you want, not just repo_name.
```


2) In your `cookiecutter.json`, make sure your directory variables are defined first, then filenames, then file contents.

So given: `{{cookiecutter.repo_name}}/{{cookiecutter.filename}}/{{cookiecutter.content}}`

Your `cookiecutter.json` would look like:

``` json

{
    "repo_name": "myrepo",
    "filename": "myfile",
    "content": "mycontent"
}
```
