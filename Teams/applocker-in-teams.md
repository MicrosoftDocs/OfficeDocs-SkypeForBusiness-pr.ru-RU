---
title: Политики управления приложениями AppLocker в группах Майкрософт
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: rafarhi
search.appverid: MET150
description: Процедура включения рабочего стола клиентское приложение группы с политиками управления AppLocker приложений.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 04379cad0ab224915a02475b010f908d486284cc
ms.sourcegitcommit: 85b135cf622c9e9eb1857ef953bc618dc2cdb51e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "34063214"
---
# <a name="applocker-application-control-policies-in-microsoft-teams"></a>Политики управления приложениями AppLocker в группах Майкрософт

В этой статье объясняется, как включить приложения для настольных компьютеров группы с политиками управления AppLocker приложений. Использование AppLocker предназначен для ограничения выполнение программы и скрипт пользователям без прав администратора. Дополнительные сведения и инструкции по AppLocker см [возможности AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).

Процесс для включения групп с помощью AppLocker требует создания политик на основе AppLocker создания списка разрешенных. Политики, созданные с помощью программного обеспечения управления групповой политики и/или использование командлетов Windows PowerShell для AppLocker ( [AppLocker Техническая справка](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) для получения дополнительных сведений см). Политика AppLocker сохраняется в формате XML и можно изменить с помощью любого текстового или XML-редактора.

## <a name="teams-whitelisting-with-applocker"></a>Разрабатывает групп с помощью AppLocker

Правила AppLocker сгруппированы в коллекции правил. Они являются компонентами, которые составляют политики AppLocker и правила AppLocker применяются целевого приложения.  

Группам белом рекомендуется использовать [publisher условие правила](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) , так как все файлы приложения группы используют цифровую подпись.
  
Не рекомендуется использовать путь правила, так как каталог установки групп для записи пользователя. Также не рекомендуется использовать правила хэш-функции из-за правил необходимо будет обновляться каждый раз, когда обновляется клиентского приложения группы.

Поскольку группам рабочего стола исполняемые файлы цифровую подпись, условие издателя указывает файл приложения на основе его цифровой подписи и атрибуты внедренных версии. Цифровая подпись содержит сведения о компании, создавшей файла приложения (издатель). Сведения о версии, получаемые из двоичного ресурса, включает в себя имя продукта, который является частью файла и номер версии файла приложения.

### <a name="example-of-publisher-condition-rules"></a>Пример publisher условие правила

Для клиентского приложения группы (все файлы, все версии):

```
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
```

## <a name="related-topics"></a>Статьи по теме
[Что такое AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker) 
 [AppLocker Технический справочник](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)