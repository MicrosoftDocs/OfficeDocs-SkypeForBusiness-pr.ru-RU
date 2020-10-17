---
title: 'Lync Server 2013: Настройка автоматической Sign-In клиента для использования директора'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Automatic Client Sign-In to use the Director
ms:assetid: 85369ffc-53ae-43be-8a23-84a094faecff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398678(v=OCS.15)
ms:contentKeyID: 48184703
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e174e55a2564dcf60b0405819e2996e4bf3d8f95
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522966"
---
# <a name="configure-automatic-client-sign-in-to-use-the-director-in-lync-server-2013"></a>Настройка автоматического клиентского Sign-In для использования директора в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-08_

При развертывании Lync Server 2013, Director или пул директоров рекомендуется использовать автоматические клиентские Sign-In. Сведения о настройке DNS-серверов для автоматического входа клиентов приведены в статье [требования к DNS для автоматического входа клиентов в Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md) в документации по планированию.

Если вы уже развернули функцию автоматического входа клиента, см. следующие разделы для получения инструкций по ее настройки в директорах.

<div>

## <a name="single-director-instance"></a>Один экземпляр директора

Если вы уже развернули автоматические клиентские Sign-In и указываете на сервер переднего плана или интерфейсный пул, необходимо изменить запись SRV DNS, чтобы она указывала на директорию.

</div>

<div>

## <a name="director-pool"></a>Пул директоров

Если вы уже развернули автоматические клиентские Sign-In и указываете на сервер переднего плана или интерфейсный пул, необходимо изменить запись SRV DNS, чтобы она указывала на пул директоров.

</div>

</div>

<span> </span>

</div>

</div>

</div>

