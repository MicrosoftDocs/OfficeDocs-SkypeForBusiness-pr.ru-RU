---
title: Командлеты в Skype для бизнеса Online, использующие удостоверение пользователя и область тегов
ms.reviewer: ''
ms.author: kenwith
author: kenwith
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
ms.openlocfilehash: 24c197934705a86d91e0492949aa2a9e6484f903
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727569"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope"></a>Командлеты в Skype для бизнеса Online, использующие удостоверение пользователя и область тегов

 


Командлеты **Grant-CS** (используемые для назначения политик пользователям) необходимы два идентификатора: удостоверение пользователя (параметр Identity) и удостоверение политики для пользователя (параметр полицинаме). Например, чтобы назначить политику голосовой связи, Редмондвоицеполици, пользователю Кен мер, вы можете использовать следующую команду:

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

При назначении политик пользователям следует помнить о двух вещах. Во-первых, можно назначить только политики для пользователей. Пользователю нельзя назначить глобальную политику. Например, эта команда завершится сбоем:

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "global"

Эта команда завершается сбоем, так как не требуется назначать глобальную политику. Если вы хотите управлять пользователем с помощью глобальной политики, просто убедитесь в том, что вы не назначаете этот пользователь политике для пользователей. Если пользователю назначена политика "на пользователя", пользователь будет автоматически управлять с помощью глобальной политики.


> [!NOTE]  
> Что делать, если пользователю ранее был назначен параметр политики для пользователя, и вы хотите отменить назначение этой политики, а вместо этого использовать ее с помощью глобальной политики? В этом случае сначала используется следующий синтаксис, который отменяет политику для пользователя, предоставляя пользователю политику NULL:<BR>Grant-Ксвоицеполици – Identity "Кен мер" – Полицинаме $Null



Во-вторых, имейте в виду, что политики для каждого пользователя создаются в области тега. Тем не менее **префикс** тега можно опустить при указании имени политики. Эти две команды идентичны:

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "tag:RedmondVoicePolicy"
    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

Если вы хотите вернуть удостоверения для всех политик пользователей (или, по крайней мере, все политики для определенного типа, например политики голосовой связи), используйте следующую команду:

    Get-CsVoicePolicy -Filter "tag:*"

Следующие командлеты используют как удостоверение пользователя, так и область тегов.

  - [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/gg412942\(v=ocs.15\))

  - [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg425937\(v=ocs.15\))

  - [Grant-CsDialPlan](https://technet.microsoft.com/en-us/library/gg398547\(v=ocs.15\))

  - [Grant-Ксекстерналакцессполици](https://technet.microsoft.com/en-us/library/gg425942\(v=ocs.15\))

  - [Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/gg412829\(v=ocs.15\))

  - [Grant-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398828\(v=ocs.15\))

## <a name="see-also"></a>См. также


[Удостоверения, области и клиенты в Skype для бизнеса Online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Командлеты Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))

