---
title: 'Lync Server 2013: необходимые условия для включения проверки подлинности Kerberos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prerequisites for enabling Kerberos authentication
ms:assetid: 3f276a21-7476-4bc0-9fd1-59e844d2e9c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425909(v=OCS.15)
ms:contentKeyID: 48183945
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: adb722f69dcd975d7f346b6e4db8f8ff140f4ac3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724849"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-enabling-kerberos-authentication-in-lync-server-2013"></a>Необходимые условия для включения проверки подлинности Kerberos в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-21_

Перед включением проверки подлинности Kerberos убедитесь, что выполнены все необходимые требования к конфигурации и инфраструктуре.

  - Схема Active Directory расширена для Lync Server 2013.

  - Подготовка леса Active Directory для Lync Server 2013 завершена.

  - Подготовка домена Active Directory для Lync Server 2013 завершена.

  - Хранилище Central Management успешно установлено и доступно.

  - Топология создана и опубликована с помощью построителя топологии.

  - Серверы и роли, для которых требуются веб-службы, были определены и развернуты, в том числе серверы переднего плана, серверы Standard Edition и режиссеры.

  - Службы IIS настраиваются и развертываются с помощью рекомендованных служб ролей для поддержки веб-служб в Lync Server 2013.

После выполнения необходимых условий вы должны будете создать одну или несколько учетных записей для веб-служб, которые будут использоваться для проверки подлинности Kerberos для развертывания. Как минимум, вам нужно создать для каждого развертывания один из учетных записей проверки подлинности Kerberos. Однако вы можете создать учетную запись для каждого сайта, чтобы предоставить локальную проверку подлинности Kerberos на сайте. Вы можете указать только одну учетную запись для проверки подлинности Kerberos для сайта.

</div>

<span> </span>

</div>

</div>

</div>

