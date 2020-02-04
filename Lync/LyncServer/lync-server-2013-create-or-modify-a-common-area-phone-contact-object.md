---
title: 'Lync Server 2013: создание или изменение объекта контакта общего телефонного модуля'
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
ms.openlocfilehash: 1e9e7ddf1a4911b9afb3428531911223f62ea723
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758113"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-common-area-phone-contact-object-in-lync-server-2013"></a>Создание или изменение объекта контактного телефона для общего города в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-20_

Чтобы создать объекты-контакты доменных служб Active Directory для всех распространенных телефонов с областями, используйте командлет **New-кскоммонареафоне** . Этот командлет может создавать новые объекты контактов для использования с телефонами с общим заполнением, а также связывать существующие объекты контактов с новым стандартным телефоном. Чтобы изменить свойства объектов контакта, связанных с телефонами с общими областями, используйте командлет **Set-кскоммонареафоне** . Необязательные параметры для **Set-кскоммонареафоне** позволяют изменять такие элементы, как отображаемое имя или универсальный код ресурса (URI), связанный с телефонным подключением, а также включать и отключать учетную запись для использования с приложением Lync Server. Сведения обо всех доступных изменениях можно найти в разделе "Параметры" на странице [Set-кскоммонареафоне](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone). Подробные сведения о **новых параметрах-кскоммонареафоне** можно найти в статьях [New-кскоммонареафоне](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone).

Эти два командлета можно выполнить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.

<div>


<div>

## <a name="creating-a-common-area-phone-contact-object"></a>Создание объекта контакта общего телефонного модуля

  - Чтобы создать новый объект контакта с общим объемом на телефоне, используйте командлет **New-кскоммонареафоне** . Как минимум, при создании объекта контакта необходимо указать следующие данные:
    
      - **Линеури**: номер телефона, назначенный стандарту для телефонной сети. Обратите внимание, что при указании номера телефона необходимо использовать формат E. 164.
    
      - **Регистрарпул**: полное доменное имя (FQDN) пула регистраторов, на котором будет размещен объект-контакт.
    
      - **OU**: различающееся имя контейнера Active Directory, в котором будет создан объект контакта.
    
    Кроме того, мы рекомендуем предоставить отображаемое имя доменных служб Active Directory. В противном случае вы должны использовать GUID для указания идентификатора телефона. Например:
    
        New-CsCommonAreaPhone -LineUri "tel:+12065551219" -RegistrarPool "atl-cs-001.litwareinc.com" -OU "OU=Phones,dc=litwareinc,dc=com" -DisplayName "Lobby"

</div>

<div>

## <a name="modifying-a-common-area-phone-contact-object"></a>Изменение объекта контакта общего телефонного модуля

  - Чтобы изменить свойства существующего телефонного телефона, свяжитесь с помощью командлета **Set-кскоммонареафоне** . Например, эта команда конфигурирует адрес SIP для общего телефона с отображаемым именем DisplayName.
    
        Set-CsCommonAreaPhone -Identity "Lobby" -SipAddress "sip:lobby@litwareinc.com"

</div>

Подробные сведения можно найти в разделах справки по командлетам [New-кскоммонареафоне](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone) и командлету [Set-кскоммонареафоне](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

