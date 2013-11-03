How To Run
==========

Step 1. Install cookiecutter
   
    $ pip install cookiecutter      

Step 2. Run cookiecutter 

    $ cookiecutter https://github.com/pebreo/cookiecutter-hello-world.git

Gotchas
======
1) When using cookiecutter from a git repo, your top directory (the same level as your cookiecutter.json) should be 
called `{{cookiecutter.repo_name}}`, otherwise you get an error.

2) In your cookiecutter.json, make sure your directory variables are defined first, then filenames, then file contents.
So given: `{{cookiecutter.repo_name}}/{{cookiecutter.filename}}/{{cookiecutter.content}}`

Your cookiecutter.json would look like:



    {
        "repo_name": "myrepo",
        "filename": "myfile",
        "mycontent": "mycontent"
    }
