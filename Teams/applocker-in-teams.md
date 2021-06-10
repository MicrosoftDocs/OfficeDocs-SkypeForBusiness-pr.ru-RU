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
description: Узнайте, как включить Teams с помощью политик управления приложенияМи AppLocker.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d6e6040956ba5e5469076b4fbbab337f58268c68
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120851"
---
# <a name="applocker-application-control-policies-in-microsoft-teams"></a>Политики управления приложениями AppLocker в Microsoft Teams

В этой статье объясняется, как включить Teams с помощью политик управления приложениями AppLocker. Приложение AppLocker предназначено для ограничения выполнения программ и сценариев пользователями, не относясь к администрированию. Дополнительные сведения и инструкции по AppLocker см. в приложении [AppLocker.](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)

Для включения Teams с помощью AppLocker необходимо создать политики списка на основе AppLocker. Политики создаются с помощью программного обеспечения для управления групповыми политиками и /или использования Windows PowerShell для AppLocker (дополнительные сведения см. в технической справке [AppLocker).](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) Политика AppLocker сохранена в формате XML и может быть изменена с помощью любого текста или редактора XML.

## <a name="teams-allow-list-with-applocker"></a>Teams списка разрешить с помощью AppLocker

Правила AppLocker организованы в наборы правил. Правила AppLocker применяются к целевому приложению, и они являются компонентами, которые составляют политику AppLocker.  

Чтобы разрешить Teams, рекомендуется использовать правила [](/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) условий publisher, так как Teams все файлы приложений подписаны цифровой подписью.
  
Использовать правила пути не рекомендуется, так как Teams каталог установки является удобным для пользователей. Мы также не рекомендуем использовать правила с hash, так как они должны обновляться при каждом обновлении Teams клиентского приложения.

Поскольку Teams файлам на компьютере назначена цифровая подпись, в условии publisher указывается файл приложения на основе его цифровой подписи и внедренных атрибутов версии. Цифровая подпись содержит сведения о компании, создав файл приложения (издателя). Сведения о версии, полученные из двоичного ресурса, включают имя продукта, в состав которого входит файл, и номер версии файла приложения.

### <a name="example-of-publisher-condition-rules"></a>Пример правил условий publisher

Для клиента Teams (все файлы, все версии) добавьте в правила DLL исполняемые правила &:

```console
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
Product name: MICROSOFT TEAMS UPDATE
```

## <a name="related-topics"></a>Статьи по теме
[Что такое AppLocker?](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker) 
 [Техническая справка по AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)