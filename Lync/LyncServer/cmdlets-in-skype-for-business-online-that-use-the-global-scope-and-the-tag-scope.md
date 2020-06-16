---
title: Командлеты в Skype для бизнеса Online, использующие глобальную область и область тегов
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use the global scope and the tag scope
ms:assetid: 1e2bc055-8a72-425e-967b-e253add7018c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362774(v=OCS.15)
ms:contentKeyID: 56558824
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8063334f2cea6fcca768754197bacbd30869461
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755079"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope"></a>Командлеты в Skype для бизнеса Online, использующие глобальную область и область тегов

 


В Skype для бизнеса Online политики можно настроить на *глобальном* уровне или в *области тегов* (или *на уровне отдельных пользователей*). При использовании командлетов **Get – CS** нет необходимости указывать область или идентификатор. Если вы вызываете один из этих командлетов без параметров, будут возвращены все соответствующие элементы. Например, эта команда возвращает сведения обо всех политиках внешнего доступа:

    Get-CsExternalAccessPolicy

Если вы хотите ограничить возвращаемые данные, необходимо включить только параметр Identity или параметр Filter. Например, чтобы возвратить только глобальную политику, используйте следующую команду:

    Get-CsExternalAccessPolicy -Identity "global"

Чтобы вернуть политику на уровне пользователя с удостоверением "Редмондакцессполици", используйте следующую команду:

    Get-CsExternalAccessPolicy -Identity "RedmondAccessPolicy"


> [!NOTE]  
> При ссылке на политику на уровне пользователя <STRONG>префикс</STRONG> тега является необязательным. Этот синтаксис, который включает префикс, также является допустимым:<BR>Get-CsExternalAccessPolicy – Identity "Tag: Редмондакцессполици"



Чтобы получить все политики, кроме глобальных (то есть всех политик для отдельных пользователей), используйте следующую команду:

    Get-CsExternalAccessPolicy -Filter "tag:*"

Следующие командлеты работают как с глобальной областью, так и с областью "на пользователя" (тег):

  - [Get-CsClientPolicy](https://technet.microsoft.com/library/gg398830\(v=ocs.15\))

  - [Get-CsConferencingPolicy](https://technet.microsoft.com/library/gg398293\(v=ocs.15\))

  - [Get-CsDialPlan](https://technet.microsoft.com/library/gg413043\(v=ocs.15\))

  - [Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425805\(v=ocs.15\))

  - [Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg398348\(v=ocs.15\))

  - [Get-CsPresencePolicy](https://technet.microsoft.com/library/gg398463\(v=ocs.15\))

  - [Get-CsVoicePolicy](https://technet.microsoft.com/library/gg398101\(v=ocs.15\))


> [!NOTE]  
> Несмотря на имя, абонентские группы, функционально говоря, политики. Для сохранения терминологии, используемой с предыдущими версиями Lync Server, используется термин " <EM>абонентская абонентская</EM> политика", а не, например, политика набора номера.



## <a name="see-also"></a>См. также


[Удостоверения, области и клиенты в Skype для бизнеса Online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Командлеты Skype для бизнеса Online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

