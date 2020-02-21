---
title: 'Lync Server 2013: создание или изменение объекта контактного телефона общего пользования'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a common area phone Contact object
ms:assetid: eec33ad1-e4f2-49b2-91d6-d5a9d2e1714b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994083(v=OCS.15)
ms:contentKeyID: 51803995
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83d2eb58df1e5c83f23fdb1d31ba73b408d107a3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180096"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-common-area-phone-contact-object-in-lync-server-2013"></a>Создание или изменение объекта контактного телефона общего пользования в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-20_

Чтобы создать объекты контактов доменных служб Active Directory для всех телефонов общедоступных телефонов, используйте командлет **New – CsCommonAreaPhone** . Этот командлет может создавать новые объекты контактов для использования с телефонными телефонами, а также связывать существующие объекты контактов с новым общим телефоном. Чтобы изменить свойства контактных объектов, связанных с телефонами на общих участках, используйте командлет **Set – CsCommonAreaPhone** . Необязательные параметры для **Set-CsCommonAreaPhone** позволяют изменять такие элементы, как отображаемое имя контакта Active Directory или универсальный код ресурса (URI), связанный с телефоном, а также включать и отключать учетную запись для использования с сервером Lync Server. Подробные сведения обо всех доступных изменениях можно найти в разделе Parameters (параметры [) на странице Set — CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone). Дополнительные сведения о параметрах **New – CsCommonAreaPhone** можно найти в статье [New — CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone).

Эти два командлета можно выполнить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.

<div>


<div>

## <a name="creating-a-common-area-phone-contact-object"></a>Создание объекта контактного телефона общего пользования

  - Чтобы создать новый объект контактного телефона для общей области, используйте командлет **New – CsCommonAreaPhone** . Как минимум, при создании объекта Contact необходимо указать следующие сведения:
    
      - **LineUri**: номер телефона, назначенный телефону общей области. Обратите внимание, что при указании номера телефона необходимо использовать формат E. 164.
    
      - **RegistrarPool**: полное доменное имя (FQDN) пула регистратора, в котором будет размещаться объект Contact.
    
      - **OU**: различающееся имя контейнера Active Directory, в котором будет создан объект Contact.
    
    Мы также рекомендуем указать отображаемое имя доменных служб Active Directory. В противном случае для указания удостоверения телефона необходимо использовать GUID. Например:
    
        New-CsCommonAreaPhone -LineUri "tel:+12065551219" -RegistrarPool "atl-cs-001.litwareinc.com" -OU "OU=Phones,dc=litwareinc,dc=com" -DisplayName "Lobby"

</div>

<div>

## <a name="modifying-a-common-area-phone-contact-object"></a>Изменение объекта контактного телефона для общей области

  - Чтобы изменить свойства существующего телефона, обратитесь к объекту Contact с помощью командлета **Set – CsCommonAreaPhone** . Например, эта команда настраивает SIP адрес для телефона общего пользования с отображаемым именем DisplayName:
    
        Set-CsCommonAreaPhone -Identity "Lobby" -SipAddress "sip:lobby@litwareinc.com"

</div>

Дополнительные сведения можно найти в разделах справки для командлета [New – CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone) и командлета [Set – CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

