---
title: Командлеты в Skype для бизнеса Online, использующие удостоверение пользователя и область тегов
description: Командлеты в Skype для бизнеса Online, использующие удостоверение пользователя и область тегов.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use a user identity and the tag scope
ms:assetid: 344a21b0-5301-4e77-853a-970bb1c11e1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362781(v=OCS.15)
ms:contentKeyID: 56558838
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e2ddbcc9c90096cea5fad4cb680f4ea1797ce48
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545615"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope"></a>Командлеты в Skype для бизнеса Online, использующие удостоверение пользователя и область тегов

 


Командлетам **Grant-CS** (которые используются для назначения политик пользователям) требуются два идентификатора: удостоверение пользователя (параметр Identity) и идентификатор политики на уровне пользователя (параметр PolicyName). Например, чтобы назначить политику голосовой связи RedmondVoicePolicy пользователю Ken Myer, используйте следующую команду:

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

При назначении политик пользователям следует иметь в виду две вещи. Для начала можно назначать только политики на уровне пользователя. Невозможно назначить пользователю глобальную политику. Например, эта команда завершится с ошибками:

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "global"

Эта команда завершается с ошибкой, так как не требуется назначать глобальную политику. Если вы хотите управлять пользователем с помощью глобальной политики, убедитесь, что вы не назначите этому пользователю политику на уровне пользователя. Если пользователю не назначена политика "на пользователя", он будет автоматически управляться с помощью глобальной политики.


> [!NOTE]  
> Что делать, если пользователю ранее была назначена политика на уровне пользователя, и вы хотите отменить назначение этой политики и присвоить ей пользователя глобальную политику? В этом случае сначала необходимо использовать следующий синтаксис, который отменяет политику на уровне пользователя, предоставляя этому пользователю политику NULL:<BR>Grant-CsVoicePolicy — Identity "Ken Myer" – PolicyName $Null



Во вторых, помните, что политики на уровне пользователей создаются в области тегов. Тем не менее **префикс** тега можно опустить при указании имени политики. Эти две команды идентичны:

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "tag:RedmondVoicePolicy"
    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

Если вы хотите вернуть удостоверения для всех политик на уровне пользователя (или, по крайней мере, для всех политик на уровне пользователя, таких как политики голосовой связи), используйте команду, аналогичную следующей:

    Get-CsVoicePolicy -Filter "tag:*"

Следующие командлеты используют как удостоверение пользователей, так и область тегов.

  - [Granting — CsClientPolicy](https://technet.microsoft.com/library/gg412942\(v=ocs.15\))

  - [Granting — CsConferencingPolicy](https://technet.microsoft.com/library/gg425937\(v=ocs.15\))

  - [Granting — CsDialPlan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\))

  - [Granting — CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425942\(v=ocs.15\))

  - [Granting — CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg412829\(v=ocs.15\))

  - [Granting — CsVoicePolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\))

## <a name="see-also"></a>См. также


[Удостоверения, области и клиенты в Skype для бизнеса Online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Командлеты Skype для бизнеса Online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

