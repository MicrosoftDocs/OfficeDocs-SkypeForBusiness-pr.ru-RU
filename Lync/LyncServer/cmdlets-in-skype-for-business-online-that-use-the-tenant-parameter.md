---
title: Командлеты в Skype для бизнеса Online, использующие параметр клиента
description: Командлеты в Skype для бизнеса Online, использующие параметр клиента.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use the Tenant parameter
ms:assetid: e7fe7c12-fbe0-49c1-9e8c-eef6958f27d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362850(v=OCS.15)
ms:contentKeyID: 56558865
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff2b8053dd855a854fa26699770d3dafaa0dcbd7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546805"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter"></a>Командлеты в Skype для бизнеса Online, использующие параметр клиента

 


При изменении параметров общедоступного поставщика необходимо всегда указывать идентификатор клиента; Это справедливо даже в том случае, если у вас только один клиент. Например, эта команда устанавливает Windows Live как единственный общедоступный поставщик, с которым пользователям разрешено связываться:

    Set-CsTenantPublicProvider -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -Provider "WindowsLive"

К счастью, вам не нужно вводить идентификатор клиента (например, bf19b7db-6960-41e5-A139-2aa373474354) каждый раз при запуске одного из этих командлетов. Вместо этого можно получить идентификатор клиента, выполнив командлет [Get – CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\)) , сохранив идентификатор клиента в переменной, а затем используя эту переменную при вызове одного из других командлетов. Например:

    $x = (Get-CsTenant).TenantId
    Set-CsTenantPublicProvider -Tenant $x -Provider "WindowsLive"

Кроме того, это можно сделать в одной команде, получая идентификатор клиента, а затем переконвейеровать это значение в командлет Set-CsTenantPublicProvider:

    Get-CsTenant | Select-Object TenantId | ForEach-Object {Set-CsTenantPublicProvider -Tenant $_.TenantId -Provider "WindowsLive"}

При вызове командлета **Get – CsTenant** не требуется указывать идентификатор клиента. Эта команда возвращает сведения о клиенте:

    Get-CsTenant

С помощью следующих командлетов вы принимаете удостоверение клиента. Однако в таких случаях параметр является необязательным и его не нужно вводить при вызове командлета. Вместо этого Windows PowerShell будет эффективно вводить удостоверение клиента на основе клиента Skype для бизнеса Online, к которому вы подключены:

  - [Get — CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\))

  - [Set — Кстенантфедератионконфигуратион](https://technet.microsoft.com/library/jj994080\(v=ocs.15\))

  - [Set — Кстенансибридконфигуратион](https://technet.microsoft.com/library/jj994046\(v=ocs.15\))

  - [Get — Кстенантфедератионконфигуратион](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))

  - [Get — Кстенансибридконфигуратион](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))

  - [Get — CsTenantLicensingConfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))

Например, командлет **Get – кстенантфедератионконфигуратион** можно вызвать с помощью следующей команды:

    Get-CsTenantFederationConfiguration

Хотя это не обязательно, вы можете включить параметр клиента при вызове Get-CsTenantFederationConfiguration:

    Get-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354"

## <a name="see-also"></a>См. также


[Удостоверения, области и клиенты в Skype для бизнеса Online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Командлеты Skype для бизнеса Online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

