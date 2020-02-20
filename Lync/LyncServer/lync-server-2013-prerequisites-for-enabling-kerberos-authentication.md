---
title: 'Lync Server 2013: необходимые условия для активации проверки подлинности Kerberos'
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
ms.openlocfilehash: f5fa366ae27126ead478d66c3beb091581158d1a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152383"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-enabling-kerberos-authentication-in-lync-server-2013"></a>Необходимые условия для активации проверки подлинности Kerberos в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-21_

Перед включением проверки подлинности Kerberos убедитесь, что выполнены все необходимые требования к конфигурации и инфраструктуре.

  - Схема Active Directory расширена для Lync Server 2013.

  - Подготовка леса Active Directory завершена для Lync Server 2013.

  - Подготовка домена Active Directory завершена для Lync Server 2013.

  - Централизованное хранилище управления успешно установлено и доступно.

  - Топология была создана и опубликована с помощью построителя топологий.

  - Серверы и роли, которым требуются веб-службы, были определены и развернуты, в том числе серверы переднего плана, серверы Standard Edition и директора.

  - Службы IIS настроены и развернуты с помощью рекомендуемых служб ролей для поддержки веб-служб в Lync Server 2013.

После выполнения необходимых условий необходимо создать одну или несколько учетных записей для веб-служб, которые будут использоваться для проверки подлинности Kerberos в развертывании. Вам требуется создать хотя бы одну учетную запись для проверки подлинности Kerberos для каждого из развертываний. Однако вы можете создать учетную запись для каждого сайта, чтобы реализовать на этом сайте локальную проверку подлинности Kerberos. Для отдельного сайта можно указать только одну учетную запись для проверки подлинности Kerberos.

</div>

<span> </span>

</div>

</div>

</div>

