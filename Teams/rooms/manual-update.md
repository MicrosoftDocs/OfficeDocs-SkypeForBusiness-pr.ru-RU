---
title: Обновление устройства комнат Microsoft Teams вручную
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
appliesto:
- Microsoft Teams
ms.reviewer: sohailta
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Узнайте, как вручную обновить устройство комнат Microsoft Teams до определенной версии.
ms.openlocfilehash: fc5602aad6ffdb52ddd9f58c458b0fd6d2a625fd
ms.sourcegitcommit: 67782296062528bbeade5cb9074143fee0536646
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/24/2020
ms.locfileid: "49731401"
---
# <a name="manually-update-a-microsoft-teams-rooms-device"></a>Обновление устройства комнат Microsoft Teams вручную

Приложение "Комнаты Microsoft Teams" распространяется по Microsoft Store. Обновления для приложения устанавливаются из Microsoft Store автоматически во время ночного обслуживания; это рекомендуемый способ получения обновлений. Однако в некоторых случаях устройство с комнатами Teams не может получать обновления из Microsoft Store. Например, политики безопасности могут не позволять устройствам подключаться к Интернету или разрешая скачивание приложений из Microsoft Store. Кроме того, перед выполнением настройки может потребоваться обновить устройство, во время которого магазин Microsoft Store не доступен.

Если вы не можете получить обновления из Microsoft Store, вы можете использовать сценарий автономного обновления приложения PowerShell, чтобы вручную обновить устройства комнат Teams до более новой версии приложения "Комнаты Teams". Выполните действия, инструкции из этой статьи, чтобы вручную обновить устройства комнат Teams.

> [!NOTE]
> Этот процесс позволяет обновить только устройство комнат Teams с уже установленным приложением "Комнаты Teams". Его нельзя использовать для выполнения новой установки. Его также нельзя использовать для перенаградить приложение на более старую версию. Чтобы выполнить новую установку приложения "Комнаты Teams", обратитесь к производителю устройства, чтобы получить только его мультимедиа, или см. в этой ссылке: "Подготовка [установимого носитителя".](console.md#prepare-the-installation-media)

## <a name="step-1-download-the-offline-app-update-script"></a>Шаг 1. Скачивание сценария обновления автономного приложения

Сначала скачайте последнюю версию сценария обновления автономного приложения. Чтобы скачать сценарий, нажмите <https://go.microsoft.com/fwlink/?linkid=2151817> кнопку . Сценарий будет загружен в папку загрузок по умолчанию на вашем устройстве.

Загруженные файлы могут быть помечены Windows как заблокированные. Если вам нужно запустить сценарий, не влияя на него, потребуется разблокировать его. Чтобы разблокировать сценарий, сделайте следующее:

1. Щелкните файл правой кнопкой мыши в проводнике
2. Нажмите **кнопку "Свойства"**
3. Выберите **"Разблокировать"**
4. Нажмите **кнопку "ОК"**

Чтобы разблокировать сценарий с помощью PowerShell, [см. пункт "Разблокировать файл".](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1)

После скачивания сценария автономного обновления приложения передайте файл на устройство комнат Teams. Вы можете передать файл на устройство с помощью USB-накопителя или доступа к файлу из сетевой папки в режиме администрирования на устройстве. Не забудьте учтите, где вы сохраняете файл на устройстве.

## <a name="step-2-run-the-script-to-update-the-teams-rooms-app"></a>Шаг 2. Запуск сценария для обновления приложения "Комнаты Teams"

Сценарий обновления автономного приложения необходимо запускать из командной команды с повышенными уровнями, пока пользователь Skype (пользователь, на котором работает приложение) еще выполняется. Дополнительные сведения о том, как войти в учетную запись администратора для использования командной подсказки с повышенными уровнями во время входа пользователя Skype, см. в переключении в режим администрирования и обратно при запуске приложения ["Комнаты Microsoft Teams".](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)

Чтобы запустить сценарий из командной подсказки с повышенными уровнями, сделайте следующее:

1. Переключение в режим администрирования
2. Щелкните значок "Начните", введите **"Командная подсказка"** и выберите команду **"Запуск от администратора"**
3. Чтобы получить полный путь к сценарию и имя файла сценария, запустите следующую `<path to script>` команду:

    ```console
    PowerShell -ExecutionPolicy Unrestricted "<path to script>"
    ```

Например, если файл сценария находится в папке и его имя `C:\Users\Admin\Downloads` `MTR-Update-4.5.6.7.ps1` имеет имя, запустите следующую команду:

```console
PowerShell -ExecutionPolicy Unrestricted "C:\Users\Admin\Downloads\MTR-Update-4.5.6.7.ps1"
```

Разрешить запуск сценария. Когда все будет готово, сценарий перезагружает устройство комнат Teams.

Сценарий также можно запустить с помощью удаленной powerShell. Дополнительные сведения об использовании удаленного powerShell с устройствами комнат Teams см. в руководстве по удаленному управлению [с помощью PowerShell.](rooms-operations.md#remote-management-using-powershell)

## <a name="step-3-verify-the-app-has-been-updated-successfully"></a>Шаг 3. Проверка успешного обновления приложения

Если сценарий выполняется успешно, устройство перезагружается в приложение "Комнаты Teams".

Если сценарий столкнется с проблемой, он указывает, в чем заключается проблема в командной строке, и записыв его выходные данные в файл. Следуйте инструкциям сценария. Если вам нужно обратиться в службу поддержки Майкрософт, не забудьте включить файл журнала вместе с запросом на поддержку. Сценарий предоставит путь к файлу журнала.