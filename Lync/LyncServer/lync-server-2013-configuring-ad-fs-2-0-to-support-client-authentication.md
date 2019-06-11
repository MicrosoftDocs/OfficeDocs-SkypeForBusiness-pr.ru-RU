---
title: 'Lync Server 2013: настройка AD FS 2,0 для поддержки проверки подлинности клиента'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring AD FS 2.0 to support client authentication
ms:assetid: 4d93d400-ccaa-4da8-a71b-d05d7ba79d93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308565(v=OCS.15)
ms:contentKeyID: 54973687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12f7cad4b36eb96f7b36925aa91e6363b8cdd264
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841294"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-ad-fs-20-to-support-client-authentication-in-lync-server-2013"></a>Настройка службы AD FS 2,0 для поддержки проверки подлинности клиента в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-07-03_

Чтобы разрешить в AD FS 2.0 поддержку проверки подлинности с использованием смарт-карт, можно настроить два указанных ниже типа проверки подлинности.

  - Проверка подлинности на основе форм

  - Проверка подлинности клиента по протоколу TLS

На основе проверки подлинности по формам можно разработать веб-страницу, где подлинность пользователей будет проверяться по имени и паролю или по смарт-карте и PIN‑коду. В этой статье рассматривается преимущественно реализация проверки подлинности клиента по протоколу TLS с помощью AD FS 2.0. Дополнительные сведения о типах проверки подлинности AD FS 2,0 можно найти в статье AD FS 2,0: как изменить тип локальной [http://go.microsoft.com/fwlink/p/?LinkId=313384](http://go.microsoft.com/fwlink/p/?linkid=313384)проверки подлинности по адресу.

<div>


**Настройка AD FS 2.0 для поддержки проверки подлинности клиента**

1.  Войдите в систему на компьютере с AD FS 2.0 с помощью учетной записи администратора домена.

2.  Запустите проводник.

3.  Переход на C:\\инетпуб\\ADFS\\Ls

4.  Сделайте резервную копию файла web.config.

5.  Откройте файл web.config с помощью Блокнота.

6.  В строке меню выберите **Правка**, затем **Найти**.

7.  Поиск ** \<локалаусентикатионтипес\>**.
    
    Обратите внимание, что здесь будут перечислены четыре типа проверки подлинности, по одному на строку.

8.  Переместите строку, содержащую тип проверки подлинности TLSClient, в начало списка в разделе.

9.  Сохраните и закройте файл web.config.

10. Запустите командную строку с повышенными привилегиями.

11. Перезапустите службу IIS, выполнив следующую команду:
    
        IISReset /Restart /NoForce

</div>

</div>

<span> </span>

</div>

</div>

</div>

