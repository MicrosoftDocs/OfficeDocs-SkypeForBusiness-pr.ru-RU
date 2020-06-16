---
title: Командлеты в Skype для бизнеса Online, использующие только глобальную область
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use only the global scope
ms:assetid: 0ffd3bc9-a6a1-4c2e-8d52-e599acc49d2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362771(v=OCS.15)
ms:contentKeyID: 56558800
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b97f3c8d9ca7dda0b96db211192350184cbf27b1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755101"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-only-the-global-scope"></a>Командлеты в Skype для бизнеса Online, использующие только глобальную область

 


Некоторые параметры Skype для бизнеса Online доступны только в *глобальной области*. Это означает, что существует одна коллекция параметров, которая применяется ко всем пользователям, назначенным этому клиенту. (У каждого клиента есть собственная уникальная коллекция глобальных параметров.) При использовании командлетов, ограниченных глобальной областью, параметр Identity является необязательным. Например, для получения параметров конфигурации собраний можно использовать следующую команду:

    Get-CsMeetingConfiguration -Identity "global"

Кроме того, вы можете опустить параметр Identity и использовать эту упрощенную команду вместо этого:

    Get-CsMeetingConfiguration

Так как существует только одна глобальная коллекция параметров конфигурации собраний, две команды возвращают одни и те же сведения. Параметр Identity также можно опустить при использовании одного из командлетов **Set – CS** . Эти две команды идентичны:

    Set-CsMeetingConfiguration -Identity "global" -AdmitAnonymousUsersByDefault $False
    Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False

Две команды идентичны из-за того, что по умолчанию Windows PowerShell изменит глобальную коллекцию, если не включить параметр Identity.

Следующие командлеты работают только в глобальной области:

  - [Get — Ксимфилтерконфигуратион](https://technet.microsoft.com/library/gg398980\(v=ocs.15\))

  - [Get — CsMeetingConfiguration](https://technet.microsoft.com/library/gg425875\(v=ocs.15\))

  - [Get — CsPrivacyConfiguration](https://technet.microsoft.com/library/gg413002\(v=ocs.15\))

  - [Get — Кстенантфедератионконфигуратион](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))

  - [Get — Кстенансибридконфигуратион](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))

  - [Get — CsTenantLicensingConfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))

  - [Get — Кстенантпубликпровидер](https://technet.microsoft.com/library/jj994016\(v=ocs.15\))

  - [Remove — CsVoicePolicy](https://technet.microsoft.com/library/gg398309\(v=ocs.15\))

  - [Set — CsMeetingConfiguration](https://technet.microsoft.com/library/gg398648\(v=ocs.15\))

  - [Set — CsPrivacyConfiguration](https://technet.microsoft.com/library/gg398484\(v=ocs.15\))

Обратите внимание на то, что командлет **Remove-CsVoicePolicy** является каким-либо из аномалий. Для начала этот командлет должен включать параметр Identity.

    Remove-CsVoicePolicy -Identity "global"

Во вторых, командлет **Remove – CsVoicePolicy** фактически не удаляет глобальную политику голосовой связи; Skype для бизнеса Online не позволяет удалять глобальные политики и параметры конфигурации. Действия, выполняемые командлетом, позволяют восстановить значения по умолчанию для всех свойств в глобальной политике голосовой связи. Например, по умолчанию для свойства Алловкаллфорвардинг задано значение false. Однако Алловкаллфорвардинг может быть изменено, и значение этого параметра теперь равно true. При запуске командлета **Remove – CsVoicePolicy** свойство алловкаллфорвардинг будет восстановлено до значения по умолчанию: false. В следующей таблице приведена сводка этого сценария:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Значение Алловкаллфорвардинг</th>
<th>Сценарий</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>False</p></td>
<td><p>Значение по умолчанию</p></td>
</tr>
<tr class="even">
<td><p>True</p></td>
<td><p>После изменения глобальной политики</p></td>
</tr>
<tr class="odd">
<td><p>False</p></td>
<td><p>После выполнения командлета <strong>Remove – CsVoicePolicy</strong></p></td>
</tr>
</tbody>
</table>


## <a name="see-also"></a>См. также


[Удостоверения, области и клиенты в Skype для бизнеса Online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Командлеты Skype для бизнеса Online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

