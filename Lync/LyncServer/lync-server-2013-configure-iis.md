---
title: 'Lync Server 2013: Настройка IIS'
description: 'Lync Server 2013: Настройка IIS.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure IIS
ms:assetid: bc4ae8cc-ec0c-42f1-9034-058930e530d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412918(v=OCS.15)
ms:contentKeyID: 48185248
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cdd08e47d05f2e32f14178eaaa3a100f8c445dda
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553265"
---
# <a name="configure-iis-for-lync-server-2013"></a><span data-ttu-id="0f0cd-103">Настройка служб IIS для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f0cd-103">Configure IIS for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f0cd-104">_**Последнее изменение темы:** 2011-12-16_</span><span class="sxs-lookup"><span data-stu-id="0f0cd-104">_**Topic Last Modified:** 2011-12-16_</span></span>

<span data-ttu-id="0f0cd-105">При настройке служб IIS для Lync Server 2013 включается установка правильных компонентов для поддержки веб-служб, необходимых для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0f0cd-105">Configuring Internet Information Services (IIS) for Lync Server 2013 involves installing the correct components to support the Web Services needed by Lync Server 2013.</span></span> <span data-ttu-id="0f0cd-106">Более подробную информацию об установке IIS можно узнать [в статье Конфигурация IIS в Lync Server 2013](lync-server-2013-iis-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="0f0cd-106">For details about installing IIS, see [IIS configuration in Lync Server 2013](lync-server-2013-iis-configuration.md).</span></span> <span data-ttu-id="0f0cd-107">Если у вас есть политика для запуска мастера настройки безопасности на серверах перед их включением в службу или в качестве типичной части обслуживания, обратитесь к разделу [Повторная активация сервера после закрытия портов в IIS мастером настройки безопасности](lync-server-2013-re-activate-server-after-security-configuration-wizard-closes-ports-in-iis.md) для получения сведений о побочном влиянии на работу мастера, который будет закрывать порты в конфигурации IIS Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0f0cd-107">If you have a policy to run the Security Configuration Wizard on servers before putting them into service or as a typical part of your maintenance, see [Re-activate server after Security Configuration Wizard closes ports in IIS](lync-server-2013-re-activate-server-after-security-configuration-wizard-closes-ports-in-iis.md) for information about a side effect of running the wizard that will close ports on a Lync Server 2013 IIS configuration.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0f0cd-108">Содержание</span><span class="sxs-lookup"><span data-stu-id="0f0cd-108">In This Section</span></span>

  - [<span data-ttu-id="0f0cd-109">Конфигурация IIS в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f0cd-109">IIS configuration in Lync Server 2013</span></span>](lync-server-2013-iis-configuration.md)

  - [<span data-ttu-id="0f0cd-110">Повторная активация сервера после закрытия портов в IIS мастером настройки безопасности</span><span class="sxs-lookup"><span data-stu-id="0f0cd-110">Re-activate server after Security Configuration Wizard closes ports in IIS</span></span>](lync-server-2013-re-activate-server-after-security-configuration-wizard-closes-ports-in-iis.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

