# composer

## Требования

- PHP 8.4 или выше.

## Установка

Компонент может быть установлен через [Composer](https://getcomposer.org):

```shell
composer require teapodlibs/composer
```

# Использование

В разделе composer.json файла вам потребуется добавить scripts, как это сделано в примере

```json
"scripts": {
    "post-install-cmd": [
      "Teapodsoft\\Composer\\Installer::postInstall"
    ],
}
```

В разделе composer.json файла можете использовать следующие настройки для автоматического копирования файла из
директории в директорию и создании директории с определенными правами доступа. Для этого в composer.json укажите
следующую конструкцию:
```json
"extra": {
    "Teapodsoft\\Composer\\Installer::postInstall": {
        "copyFiles": [
            {"secrets/secrets.example.json": "secrets/secrets.json"}
        ],
        "createPaths": [
          {"runtime": "0777"}
        ]
    }
},
```

# Документация

- [Internals](docs/internals.md)

# Лицензия

Пакет composer используется в публичном пространстве и может быть модифицирован или использован в комерческих целях по
лицензии от BSD Licence.

Поддерживается командой [TeapodSoft](https://github.com/teapodsoft)
