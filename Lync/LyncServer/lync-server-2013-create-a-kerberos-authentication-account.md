---
title: 'Lync Server 2013: создание учетной записи проверки подлинности Kerberos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a Kerberos authentication account
ms:assetid: 63f0cef6-562a-4209-ae25-71f8dc7c7295
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398449(v=OCS.15)
ms:contentKeyID: 48184348
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b41a19a46a23d24a680b3987f7d5eca01daab89
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207335"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-kerberos-authentication-account-in-lync-server-2013"></a>Создание учетной записи проверки подлинности Kerberos в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-01-02_

Чтобы успешно выполнить процедуру, необходимо выполнить вход на сервер или в домен по крайней мере с правами члена группы "Администраторы домена".

Вы можете создать учетные записи проверки подлинности Kerberos для каждого сайта или одну учетную запись для всех сайтов. С помощью командлетов Windows PowerShell можно создавать учетные записи и управлять ими, в том числе определять учетные записи, назначенные каждому сайту. В построителе топологий и на панели управления Lync Server 2013 не отображаются учетные записи проверки подлинности Kerberos. Чтобы создать одну или несколько учетных записей пользователей для проверки подлинности Kerberos используйте следующую процедуру.

<div>

## <a name="to-create-a-kerberos-account"></a>Создание учетной записи Kerberos

1.  В качестве члена группы администраторов домена войдите на компьютер в домене, на котором работает Lync Server 2013 или на компьютер, на котором установлены средства администрирования.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  В командной строке выполните следующую команду:
    
        New-CsKerberosAccount -UserAccount "Domain\UserAccount" -ContainerDN "CN=Users,DC=DomainName,DC=DomainExtension"
    
    Пример:
    
        New-CsKerberosAccount -UserAccount "Contoso\KerbAuth" -ContainerDN "CN=Users,DC=contoso,DC=com"

4.  Убедитесь в том, что был создан объект компьютера. Для этого откройте оснастку "Active Directory — пользователи и компьютеры", разверните контейнер **Пользователи** и проверьте, имеется ли в нем объект компьютера для учетной записи пользователя.

</div>

</div>

<span> </span>

</div>

</div>

</div>

