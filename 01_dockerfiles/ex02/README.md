1. `git clone https://bitbucket.org/railstutorial/sample_app_4th_ed.git app`
2. `docker build -t ft-rails -f Dockerfile_builder .`
3. `docker build -t rails -f Dockerfile_runner .`
4. `docker run -it --rm -p 3000:3000 rails`
