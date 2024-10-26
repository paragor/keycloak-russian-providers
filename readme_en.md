# Disclaimer
Author of the original repository did not respond to the pull request, so a fork was created with fixes and additions.

# Установка
Compiled Jar file is available on the releases page:
https://github.com/paragor/keycloak-russian-providers/releases

# Russian social networks identity providers for Keycloak.

This is Russian social networks identity providers library for [Keycloak](https://www.keycloak.org/) server.
With this library you can log in into Keycloak via
+ Yandex [https://yandex.com](https://yandex.com)  
+ VKontakte - [vk.com](http://vk.com)
+ Mail.Ru - [Mail.Ru](https://mail.ru)
+ Odnoklassniki - [ok.ru](https://ok.ru) 

[Live demo](https://elements.playa.ru/) - it uses [docker from our Docker Hub directory](https://github.com/playa-ru/keycloak-russian).

## Keycloak versions

It was tested against Keycloak versions:
+ 26.0.0
+ 25.0.2
+ 24.0.1
+ 23.0.6
+ 22.0.3
+ 21.1.1
+ 21.0.1
+ 17.0.0
+ 16.1.1
+ 15.0.2
+ 13.0.0
+ 12.0.1
+ 11.0.3
+ 10.0.0
+ 8.0.1
+ 4.8.3.Final
+ 4.5.0.Final
+ 4.4.0.Final
+ 3.4.3.Final

**Table supported versions:**

| Version Library | Version Keycloak |                    Repository                    |
|:---------------:|:----------------:|:------------------------------------------------:|
|   26.0.0.rsp    |      26.0.0      |    [Maven Central](https://mvnrepository.com)    |
|  25.0.2.rsp-2   |      25.0.2      |    [Maven Central](https://mvnrepository.com)    |
|  24.0.1.rsp-2   |      24.0.1      |    [Maven Central](https://mvnrepository.com)    |
|  23.0.6.rsp-3   |      23.0.6      |    [Maven Central](https://mvnrepository.com)    |
|   22.0.3.rsp    |      22.0.3      |    [Maven Central](https://mvnrepository.com)    |
|   21.1.1.rsp    |      21.1.1      |    [Maven Central](https://mvnrepository.com)    |
|     1.0.46      |      21.0.1      |    [Maven Central](https://mvnrepository.com)    |
|     1.0.43      |      17.0.0      |    [Maven Central](https://mvnrepository.com)    |
|     1.0.42      |      16.1.1      |    [Maven Central](https://mvnrepository.com)    |
|     1.0.38      |      15.0.2      |    [Maven Central](https://mvnrepository.com)    |
|     1.0.37      |      13.0.0      |    [Maven Central](https://mvnrepository.com)    |
|     1.0.32      |      12.0.4      |    [Maven Central](https://mvnrepository.com)    |
|     1.0.28      |      12.0.0      | [Playa Repository](https://nexus.playa.ru/nexus) |
|     1.0.26      |      12.0.1      | [Playa Repository](https://nexus.playa.ru/nexus) |
|     1.0.25      |      11.0.3      | [Playa Repository](https://nexus.playa.ru/nexus) | 
|     1.0.21      |      10.0.0      | [Playa Repository](https://nexus.playa.ru/nexus) |
|     1.0.17      |      8.0.1       | [Playa Repository](https://nexus.playa.ru/nexus) |
|     1.0.16      |      6.0.1       | [Playa Repository](https://nexus.playa.ru/nexus) |
|     1.0.15      |   4.8.3.Final    | [Playa Repository](https://nexus.playa.ru/nexus) |
|      1.0.1      |   4.5.0.Final    | [Playa Repository](https://nexus.playa.ru/nexus) |

## How to use it

### With Docker

- grab Keycloak-4.5.0.Final with library installed, as well as two [additional themes](https://github.com/playa-ru/keycloak-playa-themes) from [Docker Hub](https://github.com/playa-ru/keycloak-russian).
```
docker pull playaru/keycloak-russian
```
 - or run Maven build with `docker` profile.
```
  mvn install -Pdocker
```
### Without Docker 

You can install this library manually, in this case you should follow [instruction](https://www.keycloak.org/docs/latest/server_development/index.html#registering-provider-implementations) with a few extra steps:

* Build project from source or [get keycloak-russian-providers.jar from our Nexus repo](https://nexus.playa.ru/nexus/content/repositories/releases/ru/playa/keycloak/keycloak-russian-providers/). 
* Copy `keycloak-russian-providers.jar` to `${keycloak.home.dir}/standalone/deployments`.
* Copy files from `/src/main/resources/themes/base/admin/resources/partials` to `${keycloak.home.dir}/themes/base/admin/resources/partials`
* Add to the file `${keycloak.home.dir}/themes/base/admin/messages/admin-messages_en.properties` the following:
```
ok-public-key=Application's public key
ok.publicKey.tooltip=Application's public key
vk-api-version=API Version
vk.version.tooltip=VK API version
vk-fetched-fields=Additional user's profile fields
vk.fetched-fields.tooltip=Provide additional fields which would be fetched using the profile request
```
* Add to the file `${keycloak.home.dir}/themes/base/admin/messages/admin-messages_ru.properties` the following:
```
ok-public-key=Публичный ключ приложения
ok.publicKey.tooltip=Публичный ключ приложения
vk-api-version=API Version
vk.version.tooltip=Версия API
vk-fetched-fields=Дополнительные поля из профиля пользователя
vk.fetched-fields.tooltip=Запрашивать дополнительные поля
```
