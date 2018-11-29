# docker-heroku
docker run -it -v $(pwd):/app ruby:2.3 sh
cd app
gem install travis --no-rdoc --no-ri
curl https://cli-assets.heroku.com/install-ubuntu.sh | sh
heroku login --interactive
travis login --pro
travis encrypt $(heroku auth:token) --add deploy.api_key --pro
