---
title: 'Lync Server 2013: Настройка проверки подлинности Kerberos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Kerberos authentication
ms:assetid: dd8009ef-6265-4cc0-b2c7-e474cd1f4b09
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398976(v=OCS.15)
ms:contentKeyID: 48185601
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc4f354d985ed9e0fc85909e232e06e7c34dd593
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509656"
---
# <a name="setting-up-kerberos-authentication-in-lync-server-2013"></a>Настройка проверки подлинности Kerberos в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-21_

Lync Server 2013 поддерживает проверку подлинности NTLM и Kerberos для веб-служб. Office Communications Server 2007 и Office Communications Server 2007 R2 использовали Ртккомпонентсервице по умолчанию и Ртксервице в качестве учетных записей пользователей для запуска пулов приложений веб-служб, позволяя назначить учетным записям пользователей имя участника-службы (SPN) и выполнять роль субъекта проверки подлинности. Lync Server использует NetworkService для запуска веб-служб, а служба NetworkService не может иметь назначенные имена участников-служб.

Чтобы устранить проблему, связанную с отсутствием объектов Active Directory для хранения имен участников-служб, в панели управления Lync Server для этой цели можно использовать объекты учетной записи компьютера. Эти объекты могут содержать имена субъектов-служб и не имеют пароля с истекающим сроком действия, который затруднял использование учетных записей пользователей в предыдущих версиях.

Командлеты Windows PowerShell используются для настройки объектов компьютеров, обеспечивающих проверку подлинности Kerberos.

<div>

## <a name="in-this-section"></a>Содержание

  - [Необходимые условия для активации проверки подлинности Kerberos в Lync Server 2013](lync-server-2013-prerequisites-for-enabling-kerberos-authentication.md)

  - [Создание учетной записи проверки подлинности Kerberos в Lync Server 2013](lync-server-2013-create-a-kerberos-authentication-account.md)

  - [Назначение учетной записи проверки подлинности Kerberos для сайта в Lync Server 2013](lync-server-2013-assign-a-kerberos-authentication-account-to-a-site.md)

  - [Настройка паролей учетных записей проверки подлинности Kerberos в Lync Server 2013](lync-server-2013-setting-up-kerberos-authentication-account-passwords.md)

  - [В Lync Server 2013 добавить проверку подлинности Kerberos для других сайтов](lync-server-2013-add-kerberos-authentication-to-other-sites.md)

  - [В Lync Server 2013 удаление проверки подлинности Kerberos для сайта](lync-server-2013-remove-kerberos-authentication-from-a-site.md)

  - [Тестирование и составление отчетов о состоянии и назначении проверки подлинности Kerberos в Lync Server 2013](lync-server-2013-testing-and-reporting-the-status-and-assignment-of-kerberos-authentication.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

