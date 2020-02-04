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
ms.openlocfilehash: aa8068b69afa3e02a5634041c61be6f7711e8f30
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734819"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-quality-of-service-on-microsoft-lync-phone-edition-devices-in-lync-server-2013"></a><span data-ttu-id="1cb97-102">Настройка качества обслуживания на устройствах Microsoft Lync Phone Edition в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1cb97-102">Configuring Quality of Service on Microsoft Lync Phone Edition devices in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1cb97-103">_**Тема последнего изменения:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="1cb97-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="1cb97-104">Хотя качество обслуживания (QoS) не включено по умолчанию для устройств, таких как iPhone, Служба QoS включена по умолчанию для устройств под управлением Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="1cb97-104">Although Quality of Service (QoS) is not enabled by default for devices such as iPhones, QoS is enabled by default for devices running Lync Phone Edition.</span></span> <span data-ttu-id="1cb97-105">(Эти устройства обычно называются телефонами UC или единой системы связи.) Чтобы проверить это, выполните следующую команду Windows PowerShell в командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1cb97-105">(These devices are commonly referred to as UC or Unified Communication phones.) To verify this, run the following Windows PowerShell command from within the Lync Server Management Shell:</span></span>

    Get-CsUCPhoneConfiguration

<span data-ttu-id="1cb97-106">Если вы не внесли никаких изменений в параметры конфигурации телефона в UC, вы получите информацию, которая выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="1cb97-106">If you have not made any changes to your UC phone configuration settings then you will get back information that looks like this:</span></span>

    Identity             : Global
    CalendarPollInterval : 00:03:00
    EnforcePhoneLock     : True
    PhoneLockTimeout     : 00:10:00
    MinPhonePinLength    : 6
    SIPSecurityMode      : High
    VoiceDiffServTag     : 40
    Voice8021p           : 0
    LoggingLevel         : Off

<span data-ttu-id="1cb97-107">Для целей обеспечения качества обслуживания необходимо иметь только одно из этих свойств: Воицедиффсервтаг.</span><span class="sxs-lookup"><span data-stu-id="1cb97-107">For Quality of Service purposes, only one of these properties is of interest: VoiceDiffServTag.</span></span> <span data-ttu-id="1cb97-108">Воицедиффсервтаг представляет значение DSCP, назначенное на голосовой трафик еманатинг с устройства Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="1cb97-108">The VoiceDiffServTag represents the DSCP value assigned to voice traffic emanating from a Lync Phone Edition device.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="1cb97-109">Параметр Voice8021p больше не поддерживается в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1cb97-109">The Voice8021p parameter is no longer supported in Lync Server 2013.</span></span> <span data-ttu-id="1cb97-110">Этот параметр по-прежнему можно использовать для обеспечения обратной совместимости с Microsoft Lync Server 2010; Однако он не влияет на устройства, используемые в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1cb97-110">The parameter is still valid for backward compatibility with Microsoft Lync Server 2010; however, it has no effect on devices used with Lync Server 2013.</span></span>



</div>

<span data-ttu-id="1cb97-111">В большинстве сетей пометка пакетов Lync Phone Edition с помощью Воицедиффсервтаг в 40 не должна приводить к возникновению проблем.</span><span class="sxs-lookup"><span data-stu-id="1cb97-111">In most networks, marking Lync Phone Edition packets with a VoiceDiffServTag of 40 should not cause any problems.</span></span> <span data-ttu-id="1cb97-112">Однако 40 не является значением, которое обычно используется для передачи звука; Вместо этого голосовой трафик почти всегда помечается с помощью кода DSCP 46.</span><span class="sxs-lookup"><span data-stu-id="1cb97-112">However, 40 is not the value typically used for audio traffic; instead, audio traffic is almost always marked with the DSCP code 46.</span></span> <span data-ttu-id="1cb97-113">Для обеспечения согласованности в сети может потребоваться изменить свойство Воицедиффсервтаг для телефонов с родным на 46.</span><span class="sxs-lookup"><span data-stu-id="1cb97-113">In order to maintain consistency throughout your network, you might want to change the VoiceDiffServTag property of your UC phones to 46.</span></span>

<span data-ttu-id="1cb97-114">Для этого можно использовать либо Windows PowerShell, либо панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1cb97-114">To do that, you can use either Windows PowerShell or the Lync Server Control Panel.</span></span> <span data-ttu-id="1cb97-115">Чтобы изменить значение Воицедиффсервтаг с помощью Windows PowerShell, выполните в командной консоли Lync Server следующую команду:</span><span class="sxs-lookup"><span data-stu-id="1cb97-115">To modify the VoiceDiffServTag value by using Windows PowerShell, run the following command from within the Lync Server Management Shell:</span></span>

    Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

<span data-ttu-id="1cb97-116">Предыдущая команда изменяет глобальную коллекцию параметров конфигурации телефонной связи UC.</span><span class="sxs-lookup"><span data-stu-id="1cb97-116">The preceding command modifies the global collection of UC phone configuration settings.</span></span> <span data-ttu-id="1cb97-117">Однако обратите внимание, что параметры телефона в UC также можно назначить области сайта.</span><span class="sxs-lookup"><span data-stu-id="1cb97-117">Note, however, that UC phone settings can also be assigned to the site scope.</span></span> <span data-ttu-id="1cb97-118">Чтобы изменить параметры конфигурации телефона в UC на уровне сайта, необходимо указать идентификатор сайта.</span><span class="sxs-lookup"><span data-stu-id="1cb97-118">To modify UC phone configuration settings at the site scope, you must specify the site Identity.</span></span> <span data-ttu-id="1cb97-119">Например:</span><span class="sxs-lookup"><span data-stu-id="1cb97-119">For example:</span></span>

    Set-CsUCPhoneConfiguration -Identity "site:Redmond" -VoiceDiffServTag 46

<span data-ttu-id="1cb97-120">Вы также можете использовать следующую команду для одновременного изменения всех параметров настройки телефона в UC:</span><span class="sxs-lookup"><span data-stu-id="1cb97-120">You can also use the following command to simultaneously modify all your UC phone configuration settings:</span></span>

    Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

<span data-ttu-id="1cb97-121">Если вы предпочитаете внести это изменение с помощью панели управления Lync Server, откройте панель управления и выполните описанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="1cb97-121">If you prefer to make this change using Lync Server Control Panel, then start the Control Panel and then complete the following procedure:</span></span>

1.  <span data-ttu-id="1cb97-122">Откройте вкладку **Клиенты** и выберите пункт **Конфигурация устройства**.</span><span class="sxs-lookup"><span data-stu-id="1cb97-122">Click **Clients** and then click **Device Configuration**.</span></span>

2.  <span data-ttu-id="1cb97-123">На вкладке **Конфигурация устройства** дважды щелкните коллекцию параметров, которые вы хотите изменить (например, **Global**).</span><span class="sxs-lookup"><span data-stu-id="1cb97-123">On the **Device Configuration** tab, double-click the collection of settings you want to modify (for example, **Global**).</span></span>

3.  <span data-ttu-id="1cb97-124">В диалоговом окне **изменение конфигурации устройства** установите для поля **качество голоса службы (QoS)** значение **46** и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="1cb97-124">In the **Edit Device Configuration** dialog box, set the value of the **Voice Quality of Service (QoS)** box to **46** and then click **Commit**.</span></span>

<span data-ttu-id="1cb97-125">Если у вас несколько коллекций, вы должны повторить эти действия для каждой коллекции параметров телефона в UC.</span><span class="sxs-lookup"><span data-stu-id="1cb97-125">If you have multiple collections you will need to repeat this process for each collection of UC phone settings.</span></span> <span data-ttu-id="1cb97-126">На панели управления Lync Server не разрешается одновременное изменение нескольких наборов параметров.</span><span class="sxs-lookup"><span data-stu-id="1cb97-126">Lync Server Control Panel will not allow you to simultaneously modify multiple setting collections.</span></span>

<span data-ttu-id="1cb97-127">Если у вас есть устройства, не основанные на операционной системе Windows (например, iPhone) в вашей организации, это не повлияет на эти устройства, изменяя параметр Воицедиффсервтаг.</span><span class="sxs-lookup"><span data-stu-id="1cb97-127">If you have devices that are not based on the Windows operating system (such as iPhones) in your organization these devices will not be affected by changing the VoiceDiffServTag setting.</span></span> <span data-ttu-id="1cb97-128">Если вы хотите изменить значения DSCP на этих устройствах, вы должны будете ссылаться на руководство по администрированию для каждого из типов устройств.</span><span class="sxs-lookup"><span data-stu-id="1cb97-128">If you want to change DSCP values on those devices you will need to refer to the administration manual for each of your device types.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

