---
title: Политики управления приложениями AppLocker в Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: rafarhi
search.appverid: MET150
f1.keywords:
- NOCSH
description: Сведения о том, как включить клиентские приложения Teams для настольных систем с политиками управления приложениями AppLocker.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2d3e9df38164c5253aab3a331b47b26892a910b7
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41826387"
---
# <a name="applocker-application-control-policies-in-microsoft-teams"></a>Политики управления приложениями AppLocker в Microsoft Teams

В этой статье объясняется, как включить клиентское приложение Teams для настольных систем с политиками управления приложениями AppLocker. Функция AppLocker разработана для ограничения выполнения программы и сценария пользователями, не являющимися администраторами. Дополнительные сведения и рекомендации по AppLocker можно найти в статье [что такое AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).

Процесс включения команд с помощью AppLocker требует создания политик брандмауэров на основе AppLocker. Политики создаются с помощью программного обеспечения управления групповыми политиками и/или с помощью командлетов Windows PowerShell для AppLocker (Дополнительные сведения можно найти в [техническом справочнике по AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) ). Политика AppLocker сохраняется в формате XML и может быть изменена любым текстовым или XML-редактором.

## <a name="teams-whitelisting-with-applocker"></a>Teams брандмауэров с AppLocker

Правила AppLocker организованы в коллекции правил. Правила AppLocker применяются к целевому приложению и представляют собой компоненты, составляющие политику AppLocker.  

Для Добавление Teams рекомендуется использовать [правила условия издателя](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) , так как все файлы приложения Teams снабжены цифровой подписью.
  
Мы не рекомендуем использовать правила путей, так как каталог установки Teams является доступным для записи пользователем. Кроме того, мы не рекомендуем использовать правила для хеша, поскольку правила должны обновляться каждый раз при обновлении клиентского приложения Teams.

Так как на настольных компьютерах Teams с цифровой подписью, условие издателя определяет файл приложения на основе его цифровой подписи и атрибутов внедренной версии. Цифровая подпись включает сведения о компании, которая создала файл приложения (издатель). Сведения о версии, получаемые из двоичного ресурса, включают имя продукта, частью которого является файл, и номер версии файла приложения.

### <a name="example-of-publisher-condition-rules"></a>Пример правил условий в Publisher

В клиентском приложении Teams (все файлы, все версии) добавьте следующие правила для исполняемых правил & правила DLL:

```
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
Product name: MICROSOFT TEAMS UPDATE
```

## <a name="related-topics"></a>См. также
[Что такое AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker) 
 [Технический справочник по AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)
