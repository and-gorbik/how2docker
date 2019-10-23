FROM ruby

RUN apt-get update && \
    apt-get install -y nodejs build-essential libpq-dev sqlite3 && \
    gem install rails


ONBUILD WORKDIR /opt/app
ONBUILD COPY app/. .
ONBUILD RUN bundle install && \
            bundle exec rake db:migrate && \
            bundle exec rake db:seed

# git clone https://bitbucket.org/railstutorial/sample_app_4th_ed.git app
# docker build -t ft-rails .
# docker build -t rails -f Dockerfile_runner .
# docker run -it --rm -p 3000:3000 rails
