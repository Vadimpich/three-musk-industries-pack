# Three Musk Industries — клиентская Craftoria и игровой справочник

Файлы для нашего приватного Minecraft-сервера: [packwiz-манифест](packwiz/pack.toml) синхронизирует моды в Prism Launcher, а [русский справочник](resourcepacks/ThreeMuskGuide.zip) доступен прямо в игре через GuideME.

Основа: **Craftoria 1.37.0 · Minecraft 1.21.1 · NeoForge 21.1.249 · Java 21**. Этот репозиторий не обновляет Craftoria или NeoForge до новых версий.

## Подключить автообновление в Prism Launcher

Каждому игроку достаточно настроить это один раз:

1. Сделайте копию инстанса **Craftoria 1.37.0** в Prism Launcher. Сохранения и настройки лучше дополнительно скопировать перед первым запуском.
2. Скачайте [официальный `packwiz-installer-bootstrap.jar`](https://github.com/packwiz/packwiz-installer-bootstrap/releases/download/v0.0.3/packwiz-installer-bootstrap.jar) и положите его в папку `minecraft` этого инстанса — рядом с `options.txt`.
3. Откройте **Редактировать инстанс → Настройки → Пользовательские команды**, включите их и вставьте в поле **Команда перед запуском** одну строку:

   ```text
   "$INST_JAVA" -jar "$INST_MC_DIR/packwiz-installer-bootstrap.jar" -s client https://raw.githubusercontent.com/Vadimpich/three-musk-industries-pack/main/packwiz/pack.toml
   ```

4. Запустите игру с доступом в интернет. При первом запуске установщик сверит файлы и скачает недостающие; затем будет проверять обновления перед каждым запуском. Если CurseForge попросит скачать какой-то файл вручную, следуйте ссылке в окне установщика.

Манифест фиксирует **533 JAR-мода, 35 штатных ресурспаков и 3 шейдерпака** текущего клиента, включая наши дополнения вроде CompassHUD. Он не синхронизирует `config/`, `options.txt`, хоткеи, карты и сохранения. Посторонние JAR в папке `mods` он тоже не обязан удалять: не ставьте вручную другую версию уже включённого мода.

Полная инструкция и рекомендации по обслуживанию — в [PACKWIZ.md](PACKWIZ.md). Манифест рассчитан **на клиентов**; моды, нужные серверу, добавляются на сервер отдельно.

## Русский справочник в игре

[ThreeMuskGuide.zip](resourcepacks/ThreeMuskGuide.zip) содержит страницы о командах, FTB Teams и чанках, приключенческих и технических модах, зачарованиях и полезных механиках Craftoria. На сервере ресурспак предлагается при входе, поэтому клиентам отдельно ставить его не нужно. Книга создаётся из **обычной книги и палки**.

Исходные страницы лежат в [`guide-src/`](guide-src/), серверный рецепт — в [`server/kubejs/server_scripts/Mods/ThreeMusk/guide.js`](server/kubejs/server_scripts/Mods/ThreeMusk/guide.js). Текущий SHA-1 ZIP: `57a6fd80887feea2778ad1d4d1d4081f1702a8cc`.

После изменения справочника нужно пересобрать ZIP, обновить его SHA-1 в `server.properties` и перезапустить сервер. Прямая ссылка на ресурспак:

```text
https://raw.githubusercontent.com/Vadimpich/three-musk-industries-pack/main/resourcepacks/ThreeMuskGuide.zip
```

## Что лежит в репозитории

- [`packwiz/`](packwiz/) — манифест и метаданные версий; обычные моды скачиваются с CurseForge или официальных релизов, а не хранятся здесь.
- [`downloads/`](downloads/) — собственный клиентский мод CompassHUD, для которого нужен прямой URL.
- [`guide-src/`](guide-src/) и [`resourcepacks/`](resourcepacks/) — исходники и готовый ZIP справочника.
- [`server/`](server/) — серверный KubeJS-рецепт справочника.

Перед добавлением нового мода проверяйте совместимость с нашей версией Minecraft/NeoForge и с сервером. Версии в packwiz закреплены: **не запускайте `packwiz update --all`** без отдельной проверки сборки.
