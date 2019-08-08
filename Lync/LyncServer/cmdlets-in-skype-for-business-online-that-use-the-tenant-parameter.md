---
title: Командлеты в Skype для бизнеса Online, в которых используется параметр "клиент"
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Cmdlets that use the Tenant parameter
ms:assetid: e7fe7c12-fbe0-49c1-9e8c-eef6958f27d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362850(v=OCS.15)
ms:contentKeyID: 56558865
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd58e375bcacfcb18cbc21e6ac352b8d98b56661
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233094"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter"></a>Командлеты в Skype для бизнеса Online, в которых используется параметр "клиент"

 


При изменении параметров вашего общедоступного поставщика необходимо всегда предоставлять удостоверение клиента; Это справедливо даже в том случае, если у вас есть только один клиент. Например, эта команда задает для Windows Live только общего поставщика, которому разрешено взаимодействовать пользователям:

    Set-CsTenantPublicProvider -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -Provider "WindowsLive"

К счастью, вам не нужно вводить код клиента (например, bf19b7db-6960-41e5-A139-2aa373474354) каждый раз при запуске одного из этих командлетов. Вместо этого вы можете получить идентификатор клиента, выполнив командлет [Get-кстенант](https://technet.microsoft.com/en-us/library/jj994044\(v=ocs.15\)) , сохранив идентификатор клиента в переменной, а затем используя эту переменную при вызове одного из других командлетов. Например:

    $x = (Get-CsTenant).TenantId
    Set-CsTenantPublicProvider -Tenant $x -Provider "WindowsLive"

Кроме того, вы можете сделать это в одной команде, получая идентификатор клиента, а затем переадресовать это значение командлету Set-Кстенантпубликпровидер:

    Get-CsTenant | Select-Object TenantId | ForEach-Object {Set-CsTenantPublicProvider -Tenant $_.TenantId -Provider "WindowsLive"}

При вызове командлета **Get-кстенант** вам не нужно указывать идентификатор клиента. Эта команда возвращает сведения о вашем клиенте:

    Get-CsTenant

Следующие командлеты допускают удостоверение клиента. Однако в этих случаях параметр является необязательным и его не нужно вводить при вызове командлета. Вместо этого Windows PowerShell будет вводить удостоверение клиента на основе клиента Skype для бизнеса Online, с которым вы уже подключены.

  - [Get-CsTenant](https://technet.microsoft.com/en-us/library/jj994044\(v=ocs.15\))

  - [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080\(v=ocs.15\))

  - [Set-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994046\(v=ocs.15\))

  - [Get-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994072\(v=ocs.15\))

  - [Get-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994034\(v=ocs.15\))

  - [Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/en-us/library/dn362770\(v=ocs.15\))

Например, командлет **Get-кстенантфедератионконфигуратион** можно вызвать с помощью следующей команды:

    Get-CsTenantFederationConfiguration

Хотя это не обязательно, вы можете включить параметр клиента при вызове get-Кстенантфедератионконфигуратион:

    Get-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354"

## <a name="see-also"></a>См. также


[Удостоверения, области и клиенты в Skype для бизнеса Online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Командлеты Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))

