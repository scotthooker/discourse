web: unicorn -l $SOCKET -E production config.ru
worker: RAILS_ENV=production bundle exec sidekiq  -c 4 -e production -L ~/log/sidekiq.log -q critical -q low -q default&