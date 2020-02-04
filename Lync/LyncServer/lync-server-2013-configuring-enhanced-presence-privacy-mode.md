---
title: 'Lync Server 2013: Настройка режима конфиденциальности для расширенного присутствия'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring enhanced presence privacy mode
ms:assetid: e7a6b873-486d-4dfb-a967-c48f61f237f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399028(v=OCS.15)
ms:contentKeyID: 48185664
ms.date: 12/09/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3cc68ad4e3200a268a2a6ea901167f211942c015
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736449"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-enhanced-presence-privacy-mode-in-lync-server-2013"></a><span data-ttu-id="de9b2-102">Настройка режима конфиденциальности для расширенного присутствия в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="de9b2-102">Configuring enhanced presence privacy mode in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="de9b2-103">_**Тема последнего изменения:** 2014-12-08_</span><span class="sxs-lookup"><span data-stu-id="de9b2-103">_**Topic Last Modified:** 2014-12-08_</span></span>

<span data-ttu-id="de9b2-104">С улучшенным режимом конфиденциальности сведений о присутствии пользователи могут ограничивать сведения о присутствии, чтобы они были видны только контактам, указанным в их списке контактов в Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="de9b2-104">With enhanced presence privacy mode, users can restrict their presence information so that it is visible only to the contacts listed in their Lync 2013 Contacts list.</span></span> <span data-ttu-id="de9b2-105">В командлетах **New-кспривациконфигуратион** и **Set-кспривациконфигуратион** этот параметр управляется параметром енаблепривацимоде.</span><span class="sxs-lookup"><span data-stu-id="de9b2-105">The **New-CsPrivacyConfiguration** and **Set-CsPrivacyConfiguration** cmdlets have an EnablePrivacyMode parameter controls this option.</span></span> <span data-ttu-id="de9b2-106">Если для Енаблепривацимоде установлено значение true, параметр ограничения сведений о присутствии для контактов становится доступен в параметрах состояния Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="de9b2-106">When EnablePrivacyMode is set to True, the option to restrict presence information to contacts becomes available in the Lync 2013 Status options.</span></span> <span data-ttu-id="de9b2-107">Если для Енаблепривацимоде задано значение false, пользователи могут выбрать, как всегда разрешать всем пользователям просматривать сведения о присутствии или придерживаться всех последующих изменений, внесенных администратором в режим конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="de9b2-107">When EnablePrivacyMode is set to False, users can choose either to always allow everyone to see their presence information or to adhere to any future changes the administrator makes to the privacy mode.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="de9b2-108">Параметры конфиденциальности для Lync 2013 и Lync 2010 не соблюдаются в предыдущих версиях (Microsoft Office Communicator 2007 R2 или Microsoft Office Communicator 2007).</span><span class="sxs-lookup"><span data-stu-id="de9b2-108">Lync 2013 and Lync 2010 privacy settings are not honored by previous versions (Microsoft Office Communicator 2007 R2 or Microsoft Office Communicator 2007).</span></span> <span data-ttu-id="de9b2-109">Если для предыдущих версий Office Communicator разрешен вход, состояние пользователя Lync 2013, контактные данные или изображение могут просматривать пользователи, у которых нет разрешения на его просмотр.</span><span class="sxs-lookup"><span data-stu-id="de9b2-109">If previous versions of Office Communicator are allowed to sign in, a Lync 2013 user’s status, contact information, or picture could be viewed by someone who has not been authorized to view it.</span></span> <span data-ttu-id="de9b2-110">Кроме того, параметры конфиденциальности пользователя Lync 2013 сбрасываются, если в дальнейшем он входит в предыдущую версию Communicator.</span><span class="sxs-lookup"><span data-stu-id="de9b2-110">Additionally, a Lync 2013 user’s privacy settings are reset if he or she later signs in with previous version of Communicator.</span></span><BR><span data-ttu-id="de9b2-111">По этим причинам перед включением режима конфиденциальности для расширенного присутствия в сценарии миграции выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="de9b2-111">For these reasons, in a migration scenario, before you enable enhanced presence privacy mode:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="de9b2-112">Убедитесь, что у каждого пользователя установлено приложение Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="de9b2-112">Ensure that every user has Lync 2013 installed.</span></span></P>
> <LI>
> <P><span data-ttu-id="de9b2-113">Определите правило политики для клиентской версии, чтобы не допустить вход из предыдущих версий Communicator.</span><span class="sxs-lookup"><span data-stu-id="de9b2-113">Define a client version policy rule to prevent previous versions of Communicator from signing in.</span></span></P></LI></UL>



</div>

<div>

## <a name="to-enable-enhanced-presence-privacy-mode"></a><span data-ttu-id="de9b2-114">Включение расширенного режима конфиденциальности присутствия</span><span class="sxs-lookup"><span data-stu-id="de9b2-114">To enable enhanced presence privacy mode</span></span>

1.  <span data-ttu-id="de9b2-115">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="de9b2-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="de9b2-116">Выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="de9b2-116">Run the following command:</span></span>
    
        Get-CsPrivacyConfiguration | Set-CsPrivacyConfiguration -EnablePrivacyMode $True
    
    <span data-ttu-id="de9b2-117">Эта команда включает режим конфиденциальности для всех параметров конфигурации конфиденциальности, которые в настоящее время используются в Организации.</span><span class="sxs-lookup"><span data-stu-id="de9b2-117">This command enables privacy mode for all the privacy configuration settings currently in use in the organization.</span></span> <span data-ttu-id="de9b2-118">Дополнительные сведения о том, как с помощью расширенных конфигураций политики режима конфиденциальности в Lync Server можно управлять присутствием контакта в клиенте Lync 2013, ознакомьтесь со статьей Microsoft KB, в которой [включен режим конфиденциальности Lync Server повышенное состояние "недоступен" для некоторых контактов Lync](http://support.microsoft.com/kb/3020057).</span><span class="sxs-lookup"><span data-stu-id="de9b2-118">For more information about how the Lync Server enhanced presence privacy mode policy configurations manages contact presence for the Lync 2013 client, see the Microsoft KB article [Enabling Lync Server enhanced presence privacy mode updates the presence status of some Lync contacts to "unavailable"](http://support.microsoft.com/kb/3020057).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="de9b2-119">См. также</span><span class="sxs-lookup"><span data-stu-id="de9b2-119">See Also</span></span>


[<span data-ttu-id="de9b2-120">Get-CsPrivacyConfiguration</span><span class="sxs-lookup"><span data-stu-id="de9b2-120">Get-CsPrivacyConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsPrivacyConfiguration)  
[<span data-ttu-id="de9b2-121">New-CsPrivacyConfiguration</span><span class="sxs-lookup"><span data-stu-id="de9b2-121">New-CsPrivacyConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsPrivacyConfiguration)  
[<span data-ttu-id="de9b2-122">Set-CsPrivacyConfiguration</span><span class="sxs-lookup"><span data-stu-id="de9b2-122">Set-CsPrivacyConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

