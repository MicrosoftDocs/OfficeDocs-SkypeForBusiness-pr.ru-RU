---
title: 'Lync Server 2013: настройка паролей учетных записей проверки подлинности Kerberos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up Kerberos authentication account passwords
ms:assetid: b435f88e-4a77-4be7-b7e5-c17484303b74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412870(v=OCS.15)
ms:contentKeyID: 48185167
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06ca8bf5d1b3dc90b1ceacbe581e0426b5c0aaa9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849724"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-kerberos-authentication-account-passwords-in-lync-server-2013"></a>Настройка паролей учетных записей проверки подлинности Kerberos в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2010-11-03_

После того как вы создадите объект компьютера для учетной записи проверки подлинности Kerberos, вы можете настроить пароль для учетной записи. Вы запускаете командлет Windows PowerShell для задания пароля учетной записи Kerberos на одном сервере. Вы можете установить пароль для объекта, созданного для проверки подлинности Kerberos. Для пароля может быть задано известное значение, но по умолчанию используется случайный пароль. Пароль доступен для всех источников проверки подлинности Kerberos, использующих эту учетную запись. Вы можете использовать командлеты Windows PowerShell для настройки и управления паролями учетной записи Kerberos.

<div>


> [!NOTE]  
> Объект учетной записи Kerberos является объектом компьютера, но использует параметр UserAccount для операций в командлетах Windows PowerShell, на которые указывают ссылки. Обратите внимание, что это не ошибка, но предполагаемое поведение командлета при создании и обслуживании учетной записи Kerberos.



</div>

<div>

## <a name="in-this-section"></a>Содержание

  - [Установка пароля учетной записи Kerberos для проверки подлинности на сервере в Lync Server 2013](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md)

  - [Синхронизация пароля учетной записи проверки подлинности Kerberos с IIS в Lync Server 2013](lync-server-2013-synchronize-a-kerberos-authentication-account-password-to-iis.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

