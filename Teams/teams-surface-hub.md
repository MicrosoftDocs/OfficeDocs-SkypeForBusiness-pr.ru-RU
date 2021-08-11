---
title: Развертывание Microsoft Teams для Surface Hub
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 12/04/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: jatpatel
description: Узнайте, как установить и настроить приложение Teams для Surface Hub, чтобы Teams по умолчанию приложение для звонков и собраний.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Devices
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3a4e1786064f0f87d153d3167c9d2eceed3126f9df97e5e6deb77e55c6b1691e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54292926"
---
# <a name="deploy-microsoft-teams-for-surface-hub"></a>Развертывание Microsoft Teams для Surface Hub

Прежде чем Teams для Surface Hub, сделайте следующее:

 □ убедитесь, что оборудование, операционная система и другие требования выполнены. Дополнительные сведения см. в [Microsoft Surface Hub администрирования](/surface-hub/).<br>
 □ убедитесь, что установлено минимальное обновление операционной системы для Teams — [KB4343889.](https://support.microsoft.com/help/4343889)<br>
 □ назначение лицензии Teams учетной записи устройства Hub.<br>
 □ Если вы переходите с Skype для бизнеса Online, подтвердим, Teams лицензия назначена пользователю.

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a>Установите Teams для Surface Hub из Microsoft Store 

Эти инструкции по установке Teams для Surface Hub из Microsoft Store. 
 
1. Запустите Microsoft Store.<br>
   а) Нажмите **Запустить**  >  **все приложения**  >  **Параметры**.<br> б) **Коснитесь Surface Hub учетной записи устройства, управления**.<br>
   в. Слева коснитесь вкладки **Приложения & Функции.**<br> г. Справа нажмите кнопку **Открыть Магазин.** 
2. В Microsoft Store наймем Microsoft Teams . Отобраз **Microsoft Teams для Surface Hub.** Нажмите **кнопку Получить приложение** для установки.  
3. После завершения установки перезапустите Surface Hub. 

> [!NOTE]
> Не **нажмем кнопку Запустить** на странице со списком Магазин.

## <a name="make-teams-the-default-calling-and-meetings-application"></a>Сделать Teams приложением для звонков и собраний по умолчанию
 
Настроить политику приложений для звонков и собраний по умолчанию можно двумя вариантами: 

- **Вариант 1.** Настройка с помощью USB-клавиши. 
- **Вариант 2.** Настройка с помощью MDM, например Intune.
 
### <a name="option-1-configure-via-usb-key"></a>Вариант 1. Настройка с помощью USB-клавиши 
 
Пакеты можно найти на этой странице [скачивания](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g). Выберите подходящий пакет, который вы планируете установить, и скопируйте его на USB-накопитель. Правильный PPKG-файл зависит от политики приложений, используемой по умолчанию: 

|Число  |Описание  |
|---------|---------|
|0     | Skype на экране "Начните", Teams доступные собрания        |
|1     | Teams на экране "Начните", Skype доступные собрания        |
|2     | Teams монопольно на экране "Начните" (Skype приложение не доступно)        |
 
1. Прикрепить USB-клавишу к Surface Hub устройству. 
2. Откройте приложение **Параметры** на устройстве Surface Hub. 
3. Откройте **Surface Hub управление учетной записью устройства**.
4. Откройте **управление устройствами**. 
5. Нажмите **кнопку Добавить или удалить пакет.** 
6. Нажмите **кнопку Добавить пакет**.
7. Выберите в **меню параметр Съемный** носителю. 
8. Добавьте соответствующий <strong>пакет TeamsRTMMode*.ppkg,</strong> который ранее был скопирован на USB-ключ. 
9. Перезапустите Surface Hub устройстве. 
10. После перезапуска устройства вы сможете запустить приложение Teams с экрана "Пуск" и присоединиться к собранию из календаря. 

### <a name="option-2-configure-via-mdm-such-as-intune"></a>Вариант 2. Настройка с помощью MDM, например Intune 

Чтобы настроить политику приложения для звонков и собраний по умолчанию через Intune, используйте следующие следующую политику: Также см. блог [Развертывание Microsoft Teams для Surface Hub с помощью Intune.](https://y0av.me/2018/07/16/deploy-the-microsoft-teams-for-surface-hub-app-using-intune/)

|Параметр   |Значение    |Описание    |
|----------|---------|---------|
|Путь      | ./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode        |
|Тип данных | integer (0-2)   |0 — Skype на экране "Начните" и Teams доступные собрания<br>1. Teams на экране "Начните" и Skype доступные собрания<br>2. Teams монопольное приложение на экране "Начните" (Skype приложение не доступно) |
|Операции| Получить, Установить        |

|Параметр   |Значение    |
|----------|---------|
|Путь      | ./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId        |
|Тип данных | строка— задате для Teams как **Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams** |
|Операции| Получить, Установить        |

Перезапустите Surface Hub устройстве. После перезапуска устройства вы сможете запустить приложение Teams с экрана "Пуск" и присоединиться к собранию из календаря.