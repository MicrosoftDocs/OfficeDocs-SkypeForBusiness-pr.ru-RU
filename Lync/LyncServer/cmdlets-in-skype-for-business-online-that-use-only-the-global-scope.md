---
title: Командлеты в Skype для бизнеса Online, использующие только глобальную область
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Cmdlets that use only the global scope
ms:assetid: 0ffd3bc9-a6a1-4c2e-8d52-e599acc49d2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362771(v=OCS.15)
ms:contentKeyID: 56558800
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 210e9116152ebe071ec81d2e0d48ff31b7c20a60
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233108"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-only-the-global-scope"></a>Командлеты в Skype для бизнеса Online, использующие только глобальную область

 


Ряд параметров Skype для бизнеса Online доступен только в *глобальной области*. Это означает, что существует единственная коллекция параметров, которая применяется ко всем пользователям, которые назначены этому клиенту. (У каждого клиента есть своя уникальная коллекция глобальных параметров.) При использовании командлетов, ограниченных глобальной областью, параметр Identity является необязательным. Например, чтобы получить параметры конфигурации собрания, можно использовать следующую команду:

    Get-CsMeetingConfiguration -Identity "global"

Кроме того, вы можете опустить параметр Identity и использовать эту простую команду вместо этого:

    Get-CsMeetingConfiguration

Так как имеется только одна глобальная коллекция параметров конфигурации собрания, две команды возвращают одни и те же данные. Параметр Identity также можно опустить при использовании одного из командлетов **Set-CS** . Эти две команды идентичны:

    Set-CsMeetingConfiguration -Identity "global" -AdmitAnonymousUsersByDefault $False
    Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False

Две команды идентичны, так как по умолчанию Windows PowerShell изменит глобальную коллекцию, если не включить параметр Identity.

Следующие командлеты работают только в глобальной области:

  - [Get-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/gg398980\(v=ocs.15\))

  - [Get-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/gg425875\(v=ocs.15\))

  - [Get-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/gg413002\(v=ocs.15\))

  - [Get-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994072\(v=ocs.15\))

  - [Get-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994034\(v=ocs.15\))

  - [Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/en-us/library/dn362770\(v=ocs.15\))

  - [Get-CsTenantPublicProvider](https://technet.microsoft.com/en-us/library/jj994016\(v=ocs.15\))

  - [Remove-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398309\(v=ocs.15\))

  - [Set-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/gg398648\(v=ocs.15\))

  - [Set-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/gg398484\(v=ocs.15\))

Обратите внимание, что командлет **Remove-ксвоицеполици** является какой-либо аномалией. Для начала для этого командлета требуется включить параметр Identity:

    Remove-CsVoicePolicy -Identity "global"

Во-вторых, командлет **Remove-ксвоицеполици** фактически не удаляет глобальную политику голосовой связи; В Skype для бизнеса Online запрещено удалять глобальные политики и параметры конфигурации. Действие командлета — это возможность сброса всех свойств в глобальной политике голосовой связи в значения по умолчанию. Например, по умолчанию для свойства Алловкаллфорвардинг задано значение false. Тем не менее, Алловкаллфорвардинг может быть изменено, и теперь для него установлено значение true. При запуске командлета **Remove-ксвоицеполици** свойству алловкаллфорвардинг будет возвращено значение по умолчанию: false. В приведенной ниже таблице перечислены сценарии.


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
<td><p>После запуска командлета <strong>Remove-ксвоицеполици</strong></p></td>
</tr>
</tbody>
</table>


## <a name="see-also"></a>См. также


[Удостоверения, области и клиенты в Skype для бизнеса Online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Командлеты Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))

