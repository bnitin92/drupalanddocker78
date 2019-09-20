# Comments

#always specify exact available image rather than latest

# Import drupal8 base image
FROM drupal:8.7.5-apache

#include extra capabilities
RUN apt-get update && apt-get -f install -y \
  curl \
  git \
#  mysql-client \
  vim \
  wget \
#  postgresql-client \
  traceroute \
  nano

# Installing postgres client
RUN apt-get update \
    && mkdir -p /usr/share/man/man1 \
    && mkdir -p /usr/share/man/man7 \
    && apt-get install -y --no-install-recommends postgresql-client \
    && rm -rf /var/lib/apt/lists/* \
    && apt-get clean 

# Installing Composer (PHP dependency manager)
RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" && \
  php composer-setup.php && \
  mv composer.phar /usr/local/bin/composer && \
  php -r "unlink('composer-setup.php');"

# Installing Drush
RUN wget -O drush.phar https://github.com/drush-ops/drush-launcher/releases/download/0.4.2/drush.phar && \
  chmod +x drush.phar && \
  mv drush.phar /usr/local/bin/drush



#Installing sublime 

# RUN apt update && apt install apt-transport-https ca-certificates curl software-properties-common \
#   curl -fsSL https://download.sublimetext.com/sublimehq-pub.gpg | sudo apt-key add - \
#   sudo add-apt-repository "deb https://download.sublimetext.com/ apt/stable/" \
#   apt update \
#   apt install sublime-text

# RUN wget -qO - https://download.sublimetext.com/sublimehq-pub.gpg | sudo apt-key add - \
#   echo "deb https://download.sublimetext.com/ apt/stable/" | sudo tee /etc/apt/sources.list.d/sublime-text.list \
#   apt-get update \
#   apt-get install sublime-text