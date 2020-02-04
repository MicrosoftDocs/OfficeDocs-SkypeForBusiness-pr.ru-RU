---
title: 'Lync Server 2013: настройка IIS'
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
ms.openlocfilehash: 6c5eb1d20997ab05f6b40c3d8b527230eef04174
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729829"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-iis-for-lync-server-2013"></a><span data-ttu-id="3f36d-102">Настройка IIS для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f36d-102">Configure IIS for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f36d-103">_**Тема последнего изменения:** 2011-12-16_</span><span class="sxs-lookup"><span data-stu-id="3f36d-103">_**Topic Last Modified:** 2011-12-16_</span></span>

<span data-ttu-id="3f36d-104">Настройка служб IIS для Lync Server 2013 включает установку правильных компонентов для поддержки веб-служб, необходимых для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3f36d-104">Configuring Internet Information Services (IIS) for Lync Server 2013 involves installing the correct components to support the Web Services needed by Lync Server 2013.</span></span> <span data-ttu-id="3f36d-105">Подробнее об установке IIS можно узнать [в разделе Конфигурация IIS в Lync Server 2013](lync-server-2013-iis-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="3f36d-105">For details about installing IIS, see [IIS configuration in Lync Server 2013](lync-server-2013-iis-configuration.md).</span></span> <span data-ttu-id="3f36d-106">Если у вас есть политика для запуска мастера настройки безопасности на серверах, прежде чем они появятся в службе или как типичная часть обслуживания, ознакомьтесь со статьей [Реактивация сервера после того, как мастер настройки безопасности закроет порт в IIS](lync-server-2013-re-activate-server-after-security-configuration-wizard-closes-ports-in-iis.md) , чтобы получить информацию о побочном эффекте запуска мастера, который будет закрывать порты в конфигурации IIS 2013 для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3f36d-106">If you have a policy to run the Security Configuration Wizard on servers before putting them into service or as a typical part of your maintenance, see [Re-activate server after Security Configuration Wizard closes ports in IIS](lync-server-2013-re-activate-server-after-security-configuration-wizard-closes-ports-in-iis.md) for information about a side effect of running the wizard that will close ports on a Lync Server 2013 IIS configuration.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3f36d-107">Содержание</span><span class="sxs-lookup"><span data-stu-id="3f36d-107">In This Section</span></span>

  - [<span data-ttu-id="3f36d-108">Конфигурация IIS в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f36d-108">IIS configuration in Lync Server 2013</span></span>](lync-server-2013-iis-configuration.md)

  - [<span data-ttu-id="3f36d-109">Повторная активация сервера после закрытия портов в IIS мастером настройки безопасности</span><span class="sxs-lookup"><span data-stu-id="3f36d-109">Re-activate server after Security Configuration Wizard closes ports in IIS</span></span>](lync-server-2013-re-activate-server-after-security-configuration-wizard-closes-ports-in-iis.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

