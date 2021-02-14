---
title: Политики управления AppLocker
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: rafarhi
search.appverid: MET150
f1.keywords:
- NOCSH
description: Узнайте, как включить клиентские приложения Teams для настольных пк с помощью политик управления приложениями AppLocker.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4e70fc4502851137494c316db9eff7faefc140d1
ms.sourcegitcommit: c573b0be535fcf927ae01d60a7eb8fbf1aec271d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2020
ms.locfileid: "46526695"
---
# <a name="applocker-application-control-policies-in-microsoft-teams"></a>Политики управления приложениями AppLocker в Microsoft Teams

В этой статье объясняется, как включить клиентские приложения Teams для настольных пк с помощью политик управления приложениями AppLocker. Использование AppLocker предназначено для ограничения выполнения программ и сценариев пользователями, которые не используют административные точки. Дополнительные сведения и инструкции по AppLocker см. в руководстве [по appLocker.](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)

Для включения Teams с помощью AppLocker необходимо создать политики включения в список на основе AppLocker. Политики создаются с помощью программного обеспечения для управления групповыми политиками и (или) использования Windows PowerShell для AppLocker (дополнительные сведения см. в технической справке [по AppLocker).](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) Политика AppLocker сохранена в формате XML и может быть изменена в любом текстовом или редакторе XML.

## <a name="teams-allow-list-with-applocker"></a>Список "Разрешить" в Teams с помощью AppLocker

Правила AppLocker организованы в коллекции правил. Правила AppLocker применяются к целевому приложению, и именно они являются компонентами, составляющими политику AppLocker.  

Чтобы разрешить Teams, рекомендуем использовать правила условий [publisher,](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) так как все файлы приложений Teams имеют цифровую подпись.
  
Использовать правила пути не рекомендуется, так как каталог установки Teams можно писать пользователям. Мы также не рекомендуем использовать hash rules, так как они должны обновляться при каждом обновлении клиентского приложения Teams.

Так как исполняемые файлы рабочего стола Teams имеют цифровую подпись, в условии publisher указывается файл приложения на основе цифровой подписи и атрибутов внедренной версии. Цифровая подпись содержит сведения о компании, создав файл приложения (издателе). Сведения о версии, полученные из двоичного ресурса, включают имя продукта, в состав которого входит файл, и номер версии файла приложения.

### <a name="example-of-publisher-condition-rules"></a>Пример правил условий publisher

Для клиентского приложения Teams (все файлы, все версии) добавьте в правила DLL для исполняемых & следующее:

```console
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
Product name: MICROSOFT TEAMS UPDATE
```

## <a name="related-topics"></a>Статьи по теме
[Что такое AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker) 
 [Справочник по приложению AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)
