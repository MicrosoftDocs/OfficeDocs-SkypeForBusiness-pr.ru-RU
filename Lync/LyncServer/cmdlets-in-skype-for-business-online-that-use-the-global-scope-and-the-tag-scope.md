---
title: Командлеты в Skype для бизнеса Online, использующие глобальную область и область тегов
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Cmdlets that use the global scope and the tag scope
ms:assetid: 1e2bc055-8a72-425e-967b-e253add7018c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362774(v=OCS.15)
ms:contentKeyID: 56558824
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51327b98be69f92736c1c8523c97b4de6463273b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841094"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope"></a>Командлеты в Skype для бизнеса Online, использующие глобальную область и область тегов

 


В Skype для бизнеса Online политики можно настроить как в *глобальной области* , так и в *области тега* (или *отдельно для каждого пользователя*). При использовании командлетов **Get-CS** вам не нужно указывать область или удостоверение. Если вы вызываете один из этих командлетов без параметров, будут возвращены все соответствующие элементы. Например, эта команда возвращает сведения обо всех политиках внешнего доступа:

    Get-CsExternalAccessPolicy

Если вы хотите ограничить возвращаемые данные, необходимо включить параметр Identity или параметр фильтра. Например, чтобы возвратить только глобальную политику, используйте следующую команду:

    Get-CsExternalAccessPolicy -Identity "global"

Для возврата политики для пользователей с удостоверением "Редмондакцессполици" используйте следующую команду:

    Get-CsExternalAccessPolicy -Identity "RedmondAccessPolicy"


> [!NOTE]  
> При обращении к политике на уровне пользователя <STRONG>префикс</STRONG> тега является необязательным. Этот синтаксис, включающий префикс, также является допустимым:<BR>Get-Ксекстерналакцессполици-Identity "тег: Редмондакцессполици"



Чтобы получить все политики за исключением глобальных политик (то есть всех политик для пользователей), используйте следующую команду:

    Get-CsExternalAccessPolicy -Filter "tag:*"

Следующие командлеты работают как в глобальной области, так и в области "на пользователя" (тег).

  - [Get-CsClientPolicy](https://technet.microsoft.com/en-us/library/gg398830\(v=ocs.15\))

  - [Get-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg398293\(v=ocs.15\))

  - [Get-CsDialPlan](https://technet.microsoft.com/en-us/library/gg413043\(v=ocs.15\))

  - [Get-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/gg425805\(v=ocs.15\))

  - [Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/gg398348\(v=ocs.15\))

  - [Get-CsPresencePolicy](https://technet.microsoft.com/en-us/library/gg398463\(v=ocs.15\))

  - [Get-Ксвоицеполици](https://technet.microsoft.com/en-us/library/gg398101\(v=ocs.15\))


> [!NOTE]  
> Несмотря на имя, абонентские группы будут функционально говорить, что политики. Термин "абонентская <EM>Группа</EM> " используется вместо (например, с политикой набора номера) для сохранения терминологии, используемой в предыдущих версиях Lync Server.



## <a name="see-also"></a>См. также


[Удостоверения, области и клиенты в Skype для бизнеса Online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Командлеты Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))

