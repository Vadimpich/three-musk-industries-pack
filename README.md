# Three Musk Industries — Craftoria

Ресурспак с русским справочником для нашего сервера Minecraft 1.21.1. Книга работает через уже установленный в Craftoria GuideME.

## Скачать

[ThreeMuskGuide.zip](resourcepacks/ThreeMuskGuide.zip) — готовый серверный ресурспак. Его прямая ссылка после публикации:

```text
https://raw.githubusercontent.com/Vadimpich/three-musk-industries-pack/main/resourcepacks/ThreeMuskGuide.zip
```

SHA-1 этой версии: `57a6fd80887feea2778ad1d4d1d4081f1702a8cc`.

В `server.properties` указывается прямая ссылка и SHA-1:

```properties
resource-pack=https://raw.githubusercontent.com/Vadimpich/three-musk-industries-pack/main/resourcepacks/ThreeMuskGuide.zip
resource-pack-sha1=57a6fd80887feea2778ad1d4d1d4081f1702a8cc
```

Серверный файл [рецепта](server/kubejs/server_scripts/Mods/ThreeMusk/guide.js) нужно разместить по тому же пути в `kubejs` сервера. Рецепт: обычная книга + палка.

Исходники книги находятся в [`guide-src`](guide-src). После правки страниц ZIP и его SHA-1 нужно обновить вместе, чтобы клиенты загрузили новую версию.
