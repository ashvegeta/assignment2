# assignment2

configuration details of docker-compose yml file


networks:
  ashik_arun:
    driver: bridge
services:
  drupal:
    image: drupal:8-apache
    networks:
      ashik_arun: null
    ports:
    - published: 8080
      target: 80
    volumes:
    - var/www/html/modules
    - var/www/html/profiles
    - var/www/html/themes
    - var/www/hmml/sites
  postgrel:
    environment:
      POSTGRES_PASSWORD: example
    image: postgres:10
    networks:
      ashik_arun: null
    volumes:
    - /var/lib/postgresql/data
