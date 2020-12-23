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
ms.openlocfilehash: 589bbfe75f0beea88066b5a6188b1d29c98ddd5f
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905651"
---
<a name="deploy-microsoft-teams-for-surface-hub"></a>Развертывание Microsoft Teams для Surface Hub
======================================

Перед установкой Teams для Surface Hub сделайте следующее:

 □ убедитесь, что оборудование, операционная система и другие требования выполнены. Дополнительные сведения см. в [руководстве администратора Microsoft Surface Hub.](https://docs.microsoft.com/surface-hub/)<br>
 □ убедитесь, что установлено минимальное обновление операционной системы, необходимое для Teams: [KB4343889.](https://support.microsoft.com/help/4343889)<br>
 □ назначить лицензию Teams учетной записи устройства Hub.<br>
 □ Если вы переходите со Skype для бизнеса Online, подтвердим, что пользователю назначена лицензия Teams.

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a>Установка Teams для Surface Hub из Microsoft Store 

Эти инструкции по установке Teams для Surface Hub из Microsoft Store. 
 
1. Запустите Microsoft Store:<br>
   а) Нажмите **кнопку**  >  **"Запустить все**  >  **приложения".**<br> б) **Коснитесь учетной записи устройства Surface Hub, управления.**<br>
   в. Слева коснитесь вкладки **"Приложения & возможности".**<br> г. Справа нажмите кнопку **"Открыть Магазин".** 
2. В Microsoft Store поищите *Microsoft Teams.* **Отобразит Microsoft Teams** для Surface Hub. Нажмите **кнопку " Получить приложение",** чтобы установить его.  
3. После завершения установки перезапустите Surface Hub. 

> [!NOTE]
> Не нажать **кнопку "Запустить"** на странице записи Магазина.

## <a name="make-teams-the-default-calling-and-meetings-application"></a>Сделать Teams приложением для звонков и собраний по умолчанию
 
Настроить политику приложения для звонков и собраний по умолчанию можно двумя вариантами: 

- **Вариант 1.** Настройка с помощью USB-ключа. 
- **Вариант 2.** Настройка с помощью MDM, например Intune.
 
### <a name="option-1-configure-via-usb-key"></a>Вариант 1. Настройка с помощью USB-ключа 
 
Пакеты можно найти на этой странице [скачивания.](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g) Выберите подходящий пакет для пакета, который вы планируете установить, и скопируйте его на USB-ключ. Правильный PPKG-файл зависит от политики приложения, используемой по умолчанию: 

|Число  |Описание  |
|---------|---------|
|0     | Предпочтительное приложение Skype на start-экране, доступно приложение "Собрания Teams"        |
|1     | Предпочтительное приложение Teams на экране "Начните", доступно приложение "Собрания Skype"        |
|2     | Монопольно для Teams на start-экране (приложение Skype не доступно)        |
 
1. Прикрепите USB-клавишу к устройству Surface Hub. 
2. Откройте приложение **"Параметры"** на устройстве Surface Hub. 
3. Откройте **"Управление учетной записью устройства Surface Hub".**
4. Откройте **"Управление устройствами".** 
5. Нажмите **кнопку "Добавить или удалить пакет подготовка".** 
6. Нажмите **кнопку "Добавить пакет".**
7. Выберите в **меню пункт** "Съемный носителю". 
8. Добавьте соответствующий <strong>пакет TeamsRTMMode*.ppkg,</strong> который ранее был скопирован на USB-ключ. 
9. Перезапустите устройство Surface Hub. 
10. После перезапуска устройства вы сможете запустить приложение Teams с начала и присоединиться к собранию из календаря. 

### <a name="option-2-configure-via-mdm-such-as-intune"></a>Вариант 2. Настройка с помощью MDM, например Intune 

Чтобы настроить политику приложения для звонков и собраний по умолчанию через Intune, воспользуйтесь следующими данными. См. также блог [о развертывании приложения Microsoft Teams для Surface Hub с помощью Intune.](https://y0av.me/2018/07/16/deploy-the-microsoft-teams-for-surface-hub-app-using-intune/)

|Параметр   |Значение    |Описание    |
|----------|---------|---------|
|Путь      | ./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode        |
|Тип данных | integer (0-2)   |0 — предпочтительное приложение Skype на экране "Начните", доступно приложение "Собрания Teams"<br>1. Предпочитаемая программа Teams на start-экране, доступные собрания Skype<br>2. Монопольное приложение Teams на start-экране (приложение Skype не доступно) |
|Операции| Получить, установить        |

|Параметр   |Значение    |
|----------|---------|
|Путь      | ./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId        |
|Тип данных | string - set string to Teams application package ID as **Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe! Teams** |
|Операции| Получить, установить        |

Перезапустите устройство Surface Hub. После перезапуска устройства вы сможете запустить приложение Teams с пуска и присоединиться к собранию из календаря.

