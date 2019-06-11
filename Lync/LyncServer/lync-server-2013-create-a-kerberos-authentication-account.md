---
title: 'Lync Server 2013: создание учетной записи для проверки подлинности Kerberos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a Kerberos authentication account
ms:assetid: 63f0cef6-562a-4209-ae25-71f8dc7c7295
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398449(v=OCS.15)
ms:contentKeyID: 48184348
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ab4f93d4204f7ed1f2b22d27ddb51328f8330c5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841133"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-kerberos-authentication-account-in-lync-server-2013"></a>Создание учетной записи для проверки подлинности Kerberos в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-01-02_

Для успешного выполнения этой процедуры необходимо войти в группу администраторов домена с учетной записью сервера или домена.

Вы можете создать учетные записи для проверки подлинности Kerberos для каждого сайта или создать одну учетную запись для проверки подлинности Kerberos и использовать ее для всех сайтов. Вы используете командлеты Windows PowerShell для создания учетных записей и управления ими, в том числе для идентификации учетных записей, назначенных каждому сайту. В построителе топологии и на панели управления Lync Server 2013 не отображаются учетные записи проверки подлинности Kerberos. Чтобы создать одну или несколько учетных записей пользователей, используемых для проверки подлинности Kerberos, выполните описанные ниже действия.

<div>

## <a name="to-create-a-kerberos-account"></a>Создание учетной записи Kerberos

1.  Войдя в группу администраторов домена, войдите на компьютер домена, на котором работает Lync Server 2013 или на компьютер, на котором установлены средства администрирования.

2.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

3.  В командной строке выполните следующую команду:
    
        New-CsKerberosAccount -UserAccount "Domain\UserAccount" -ContainerDN "CN=Users,DC=DomainName,DC=DomainExtension"
    
    Например:
    
        New-CsKerberosAccount -UserAccount "Contoso\KerbAuth" -ContainerDN "CN=Users,DC=contoso,DC=com"

4.  Убедитесь, что объект компьютера был создан с помощью оснастки "пользователи и компьютеры Active Directory", разверните контейнер **пользователей** и убедитесь, что объект компьютера для учетной записи пользователя находится в контейнере.

</div>

</div>

<span> </span>

</div>

</div>

</div>

