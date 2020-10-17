---
title: 'Lync Server 2013: настройка AD FS 2,0 для поддержки проверки подлинности клиента'
description: 'Lync Server 2013: настройка AD FS 2,0 для поддержки проверки подлинности клиента.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring AD FS 2.0 to support client authentication
ms:assetid: 4d93d400-ccaa-4da8-a71b-d05d7ba79d93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308565(v=OCS.15)
ms:contentKeyID: 54973687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 156eb6d7e8af85dec04601ab8f88c55181db20d5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553255"
---
# <a name="configuring-ad-fs-20-to-support-client-authentication-in-lync-server-2013"></a>Настройка служб федерации Active Directory 2,0 для поддержки проверки подлинности клиентов в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-07-03_

Существует два типа проверки подлинности, которые можно настроить, чтобы разрешить AD FS 2,0 поддерживать проверку подлинности с помощью смарт-карт:

  - Проверка подлинности на основе форм (FBA)

  - Проверка подлинности клиента для TLS

С помощью проверки подлинности на основе форм можно разработать веб-страницу, которая позволит пользователям проходить проверку подлинности с помощью имени пользователя и пароля, а также с помощью смарт-карты и ПИН-кода. В этом разделе рассказывается, как реализовать проверку подлинности клиентов TLS с помощью служб федерации Active Directory 2,0. Дополнительные сведения о типах проверки подлинности AD FS 2,0 приведены в статье AD FS 2,0: как изменить тип локальной проверки подлинности по адресу [https://go.microsoft.com/fwlink/p/?LinkId=313384](https://go.microsoft.com/fwlink/p/?linkid=313384) .

<div>


**Настройка AD FS 2,0 для поддержки проверки подлинности клиента**

1.  Выполните вход на компьютер с AD FS 2,0 с помощью учетной записи администратора домена.

2.  Запустите проводник Windows.

3.  Переход на C: \\ Inetpub \\ ADFS \\ Ls

4.  Создайте резервную копию существующего файла web.config.

5.  Откройте существующий web.config файл с помощью блокнота.

6.  В строке меню выберите команду **изменить** , а затем нажмите кнопку **найти**.

7.  Выполните поиск **\<localAuthenticationTypes\>** .
    
    Обратите внимание на то, что указаны четыре типа проверки подлинности, по одному в строке.

8.  Переместите строку, содержащую тип проверки подлинности Тлсклиент, в верхнюю часть списка в разделе.

9.  Сохраните и закройте файл web.config.

10. Запустите командную строку с повышенными привилегиями.

11. Перезапустите службы IIS, выполнив следующую команду:
    
        IISReset /Restart /NoForce

</div>

</div>

<span> </span>

</div>

</div>

</div>

