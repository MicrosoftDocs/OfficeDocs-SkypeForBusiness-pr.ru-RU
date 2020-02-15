---
title: Настройка качества обслуживания на устройствах Microsoft Lync Phone Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Quality of Service on Microsoft Lync Phone Edition devices
ms:assetid: a6eb2620-a512-4ab6-bdfd-eb76be43bbfe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205137(v=OCS.15)
ms:contentKeyID: 48185004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b1dd5fd119022807fbc64218c80e24a33557aa1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046202"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-quality-of-service-on-microsoft-lync-phone-edition-devices-in-lync-server-2013"></a><span data-ttu-id="fdfbe-102">Настройка качества обслуживания на устройствах Microsoft Lync Phone Edition в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fdfbe-102">Configuring Quality of Service on Microsoft Lync Phone Edition devices in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fdfbe-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="fdfbe-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="fdfbe-104">Хотя качество обслуживания (QoS) не включено по умолчанию для устройств, таких как iPhone, качество обслуживания включено по умолчанию для устройств под управлением Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="fdfbe-104">Although Quality of Service (QoS) is not enabled by default for devices such as iPhones, QoS is enabled by default for devices running Lync Phone Edition.</span></span> <span data-ttu-id="fdfbe-105">(Эти устройства обычно называют телефонами Объединенных коммуникаций или объединенных коммуникаций). Чтобы убедиться в этом, выполните следующую команду Windows PowerShell в командной консоли Lync Server:</span><span class="sxs-lookup"><span data-stu-id="fdfbe-105">(These devices are commonly referred to as UC or Unified Communication phones.) To verify this, run the following Windows PowerShell command from within the Lync Server Management Shell:</span></span>

    Get-CsUCPhoneConfiguration

<span data-ttu-id="fdfbe-106">Если вы не изменяли параметры конфигурации телефона объединенных коммуникаций, то возвращаемые данные будут выглядеть примерно так:</span><span class="sxs-lookup"><span data-stu-id="fdfbe-106">If you have not made any changes to your UC phone configuration settings then you will get back information that looks like this:</span></span>

    Identity             : Global
    CalendarPollInterval : 00:03:00
    EnforcePhoneLock     : True
    PhoneLockTimeout     : 00:10:00
    MinPhonePinLength    : 6
    SIPSecurityMode      : High
    VoiceDiffServTag     : 40
    Voice8021p           : 0
    LoggingLevel         : Off

<span data-ttu-id="fdfbe-107">Для рассмотрения качества обслуживания нас интересует только свойство VoiceDiffServTag.</span><span class="sxs-lookup"><span data-stu-id="fdfbe-107">For Quality of Service purposes, only one of these properties is of interest: VoiceDiffServTag.</span></span> <span data-ttu-id="fdfbe-108">Воицедиффсервтаг представляет значение DSCP, назначенное для трафика голосовой связи, еманатинг с устройства Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="fdfbe-108">The VoiceDiffServTag represents the DSCP value assigned to voice traffic emanating from a Lync Phone Edition device.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="fdfbe-109">Параметр Voice8021p больше не поддерживается в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fdfbe-109">The Voice8021p parameter is no longer supported in Lync Server 2013.</span></span> <span data-ttu-id="fdfbe-110">Параметр по-прежнему действителен для обратной совместимости с Microsoft Lync Server 2010; Однако он не оказывает никакого действия на устройствах, используемых в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fdfbe-110">The parameter is still valid for backward compatibility with Microsoft Lync Server 2010; however, it has no effect on devices used with Lync Server 2013.</span></span>



</div>

<span data-ttu-id="fdfbe-111">В большинстве сетей маркировка пакетов Lync Phone Edition с помощью Воицедиффсервтаг 40 не приводит к возникновению проблем.</span><span class="sxs-lookup"><span data-stu-id="fdfbe-111">In most networks, marking Lync Phone Edition packets with a VoiceDiffServTag of 40 should not cause any problems.</span></span> <span data-ttu-id="fdfbe-112">Однако для голосового трафика вместо значения 40 практически всегда используется значение DSCP 46.</span><span class="sxs-lookup"><span data-stu-id="fdfbe-112">However, 40 is not the value typically used for audio traffic; instead, audio traffic is almost always marked with the DSCP code 46.</span></span> <span data-ttu-id="fdfbe-113">Для обеспечения согласованности вы можете изменить значение свойства VoiceDiffServTag на 46 для телефонов объединенных коммуникаций.</span><span class="sxs-lookup"><span data-stu-id="fdfbe-113">In order to maintain consistency throughout your network, you might want to change the VoiceDiffServTag property of your UC phones to 46.</span></span>

<span data-ttu-id="fdfbe-114">Для этого можно использовать либо Windows PowerShell, либо панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fdfbe-114">To do that, you can use either Windows PowerShell or the Lync Server Control Panel.</span></span> <span data-ttu-id="fdfbe-115">Чтобы изменить значение Воицедиффсервтаг с помощью Windows PowerShell, выполните следующую команду в командной консоли Lync Server:</span><span class="sxs-lookup"><span data-stu-id="fdfbe-115">To modify the VoiceDiffServTag value by using Windows PowerShell, run the following command from within the Lync Server Management Shell:</span></span>

    Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

<span data-ttu-id="fdfbe-p106">Предыдущая команда изменяет глобальный набор параметров конфигурации телефона объединенных коммуникаций. Обратите внимание, что параметры телефона объединенных коммуникаций также можно задать на уровне сайта. Для изменения параметров конфигурации телефона объединенных коммуникаций на уровне сайта необходимо указать идентификатор сайта. Пример:</span><span class="sxs-lookup"><span data-stu-id="fdfbe-p106">The preceding command modifies the global collection of UC phone configuration settings. Note, however, that UC phone settings can also be assigned to the site scope. To modify UC phone configuration settings at the site scope, you must specify the site Identity. For example:</span></span>

    Set-CsUCPhoneConfiguration -Identity "site:Redmond" -VoiceDiffServTag 46

<span data-ttu-id="fdfbe-120">Чтобы одновременно изменить все параметры конфигурации телефона объединенных коммуникаций, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="fdfbe-120">You can also use the following command to simultaneously modify all your UC phone configuration settings:</span></span>

    Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

<span data-ttu-id="fdfbe-121">Если вы предпочитаете внести это изменение с помощью панели управления Lync Server, откройте панель управления и выполните следующую процедуру:</span><span class="sxs-lookup"><span data-stu-id="fdfbe-121">If you prefer to make this change using Lync Server Control Panel, then start the Control Panel and then complete the following procedure:</span></span>

1.  <span data-ttu-id="fdfbe-122">Щелкните **Clients** (Клиенты) и затем щелкните **Device Configuration** (Конфигурация устройства).</span><span class="sxs-lookup"><span data-stu-id="fdfbe-122">Click **Clients** and then click **Device Configuration**.</span></span>

2.  <span data-ttu-id="fdfbe-123">На вкладке **Device Configuration** (Конфигурация устройства) дважды щелкните набор параметров, который необходимо изменить (например, **Global** (Глобальный)).</span><span class="sxs-lookup"><span data-stu-id="fdfbe-123">On the **Device Configuration** tab, double-click the collection of settings you want to modify (for example, **Global**).</span></span>

3.  <span data-ttu-id="fdfbe-124">В диалоговом окне **Edit Device Configuration** (Изменение конфигурации устройства) задайте в поле **Voice Quality of Service (QoS)** (Качество для голосовых служб) значение **46** и затем щелкните **Commit** (Применить).</span><span class="sxs-lookup"><span data-stu-id="fdfbe-124">In the **Edit Device Configuration** dialog box, set the value of the **Voice Quality of Service (QoS)** box to **46** and then click **Commit**.</span></span>

<span data-ttu-id="fdfbe-125">При наличии нескольких наборов параметров вам потребуется повторить эту процедуру для каждого набора параметров телефона объединенных коммуникаций.</span><span class="sxs-lookup"><span data-stu-id="fdfbe-125">If you have multiple collections you will need to repeat this process for each collection of UC phone settings.</span></span> <span data-ttu-id="fdfbe-126">Панель управления Lync Server не позволяет одновременно изменить несколько коллекций параметров.</span><span class="sxs-lookup"><span data-stu-id="fdfbe-126">Lync Server Control Panel will not allow you to simultaneously modify multiple setting collections.</span></span>

<span data-ttu-id="fdfbe-p108">Если в организации имеются устройства не на основе ОС Windows (например, iPhone), изменение параметра VoiceDiffServTag никак не повлияет на эти устройства. Дополнительные сведения об изменении значений DSCP на этих устройствах см. в соответствующих руководствах для устройств.</span><span class="sxs-lookup"><span data-stu-id="fdfbe-p108">If you have devices that are not based on the Windows operating system (such as iPhones) in your organization these devices will not be affected by changing the VoiceDiffServTag setting. If you want to change DSCP values on those devices you will need to refer to the administration manual for each of your device types.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

