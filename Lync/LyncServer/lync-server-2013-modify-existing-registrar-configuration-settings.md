---
title: 'Lync Server 2013: изменение параметров конфигурации существующего регистратора'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify existing Registrar configuration settings
ms:assetid: a8931511-3e66-49ed-a3ec-03bcd61ce1f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182566(v=OCS.15)
ms:contentKeyID: 48185095
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c11830fa7047a9a732b10888b392a367dc36451c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534376"
---
# <a name="modify-existing-registrar-configuration-settings-in-lync-server-2013"></a>Изменение параметров конфигурации существующего регистратора в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-11-01_

Для настройки протоколов проверки подлинности прокси-сервера можно использовать службу Регистратора. Сведения о доступных протоколах приведены в разделе [Create a Configuration регистратор Settings in Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md).

<div>


> [!NOTE]  
> Если сервер обеспечивает проверку подлинности удаленных клиентов и клиентов организации, то рекомендуется включить проверку подлинности Kerberos и NTLM. Пограничный сервер и внутренние серверы проверяют, включена ли проверка подлинности NTLM для удаленных клиентов. Если на этих серверах включена только проверка подлинности Kerberos, они не смогут выполнять проверку подлинности удаленных пользователей. Если пользователи организации проходят проверку подлинности на сервере, то используется протокол Kerberos.



</div>

Чтобы изменить параметры службы Регистратора, выполните действия, описанные в следующей процедуре.

<div>

## <a name="to-modify-existing-registrar-configuration-settings"></a>Изменение параметров конфигурации существующего регистратора

1.  Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsServerAdministrator или CsAdministrator, войдите на любой компьютер в сети, в которой развернут Lync Server 2013.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните **Security** (Безопасность) и затем щелкните **Registrar** (Регистратор).

4.  На странице **Registrar** (Регистратор) выберите службу, щелкните **Edit** (Изменить) и затем щелкните **Show details** (Показать сведения).

5.  На странице **Edit Registrar Setting** (Изменение параметров Регистратора) установите один флажок или несколько в соответствии с возможностями клиентов и среды:
    
      - **Enable Kerberos authentication** (Включить проверку подлинности Kerberos) — для запросов проверки подлинности серверы пула используют протокол Kerberos.
    
      - **Включить проверку подлинности NTLM** — чтобы серверы в пуле выдавали запросы с использованием NTLM.
    
      - **Включить проверку подлинности с помощью сертификата** — чтобы серверы в пуле выдавали сертификаты клиентам.

6.  Нажмите кнопку **Зафиксировать**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

