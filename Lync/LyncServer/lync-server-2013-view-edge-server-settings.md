---
title: 'Lync Server 2013: Просмотр параметров пограничного сервера'
description: 'Lync Server 2013: Просмотр параметров пограничного сервера.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Edge Server settings
ms:assetid: 684154cc-cffc-4d2e-8baa-be52c625e5d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747890(v=OCS.15)
ms:contentKeyID: 63969612
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4318b8c97f53f267bb79953af504977f6437214d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569685"
---
# <a name="view-edge-server-settings-in-lync-server-2013"></a>Просмотр параметров пограничного сервера в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-05-20_

Общие конфигурации пограничных серверов следует проверить на соответствие данным в базе данных управления конфигурацией, чтобы обеспечить документирование всех изменений в соответствии с определенными процедурами управления изменениями.

Дополнительные проверки могут включать в себя те, что описаны в следующих разделах:

<div>

## <a name="verify-the-allow-and-block-lists"></a>Проверка списков разрешенных и заблокированных списков

Проверьте списки URI SIP "Allow" и "Block" для федеративных доменов, чтобы определить, являются ли указанные пространства имен действительными.

Вы можете использовать Windows PowerShell для просмотра разрешенных и заблокированных списков. Чтобы просмотреть домены в списке разрешенных доменов, выполните следующую команду Windows PowerShell:

`Get-CsAllowedDomain`

Эта команда возвращает сведения, аналогичные приведенным ниже, для доменов в списке разрешенных доменов:

Identity: contoso.com

Домен: contoso.com

ProxyFqdn

Комментарий

Маркформониторинг: false

Комментарий

Чтобы просмотреть домены в списке блокируемых доменов, выполните следующую команду:

`Get-CsBlockedDomain`

В свою очередь вы получите такие сведения, как, например, для каждого заблокированного домена:

Identity: tailspintoys.com

Домен: tailspintoys.com

Кроме того, Windows PowerShell позволяет убедиться, что вы можете подключиться к доменам в списке разрешенных доменов. Например, эта команда проверяет подключение между пограничным сервером (TargetFqdn) и contoso.com федеративного домена:

`Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"`

Эта команда проверяет подключение между пограничным сервером и всеми доменами, найденными в списке разрешенных доменов:

`Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Domain}`

</div>

<div>

## <a name="verify-multiple-edge-servers-are-identical"></a>Проверка того, что несколько пограничных серверов идентичны

Если в массиве с балансировкой нагрузки развернуты несколько пограничных серверов, рекомендуется проверить, что все пограничные серверы в массиве настроены одинаковым образом.

Параметры для пограничных серверов можно просмотреть в области сведений расширения Lync Server 2013 для оснастки "Управление компьютером".

</div>

<div>

## <a name="see-also"></a>См. также


[Get — CsAllowedDomain](https://docs.microsoft.com/powershell/module/skype/Get-CsAllowedDomain)  
[Get — CsBlockedDomain](https://docs.microsoft.com/powershell/module/skype/Get-CsBlockedDomain)  
[Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

