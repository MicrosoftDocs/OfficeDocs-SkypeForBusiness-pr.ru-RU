---
title: 'Lync Server 2013: Настройка паролей учетных записей проверки подлинности Kerberos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Kerberos authentication account passwords
ms:assetid: b435f88e-4a77-4be7-b7e5-c17484303b74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412870(v=OCS.15)
ms:contentKeyID: 48185167
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bef30a82479c876dbb4b4e6e6e9b55b3c2b37dc3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143191"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-kerberos-authentication-account-passwords-in-lync-server-2013"></a>Настройка паролей учетных записей проверки подлинности Kerberos в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2010-11-03_

После создания объекта-компьютера для учетной записи проверки подлинности Kerberos можно задать пароль для учетной записи. Для задания пароля учетной записи Kerberos на одном сервере выполните командлет Windows PowerShell. Кроме того, можно задать пароль для объекта, созданного для проверки подлинности Kerberos. В качестве пароля можно использовать известное значение, однако по умолчанию используется случайный пароль. Пароль доступен всем источникам проверки подлинности Kerberos, которые используют учетную запись. Командлеты Windows PowerShell используются для настройки паролей учетных записей Kerberos и управления ими.

<div>


> [!NOTE]  
> Объект учетной записи Kerberos является объектом Computer, но использует параметр UserAccount для операций в командлетах Windows PowerShell, на которые указывают ссылки. Обратите внимание, что это не ошибка, а намеренное поведение командлета при использовании с учетной записью создания и поддержки Kerberos.



</div>

<div>

## <a name="in-this-section"></a>Содержание

  - [Установка пароля учетной записи проверки подлинности Kerberos на сервере в Lync Server 2013](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md)

  - [Синхронизация пароля учетной записи проверки подлинности Kerberos с IIS в Lync Server 2013](lync-server-2013-synchronize-a-kerberos-authentication-account-password-to-iis.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

