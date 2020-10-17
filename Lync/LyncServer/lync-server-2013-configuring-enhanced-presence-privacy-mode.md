---
title: 'Lync Server 2013: Настройка режима конфиденциальности расширенного присутствия'
description: 'Lync Server 2013: Настройка режима конфиденциальности расширенного присутствия.'
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
ms.openlocfilehash: c8eab347d233c23a9a4becf119dee673d3021dfa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548455"
---
# <a name="configuring-enhanced-presence-privacy-mode-in-lync-server-2013"></a><span data-ttu-id="45515-103">Настройка режима конфиденциальности расширенных сведений о присутствии в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="45515-103">Configuring enhanced presence privacy mode in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45515-104">_**Последнее изменение темы:** 2014-12-08_</span><span class="sxs-lookup"><span data-stu-id="45515-104">_**Topic Last Modified:** 2014-12-08_</span></span>

<span data-ttu-id="45515-105">Благодаря расширенному режиму конфиденциальности пользователей пользователи могут ограничить сведения о присутствии, чтобы они отображались только для контактов, перечисленных в списке контактов в Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="45515-105">With enhanced presence privacy mode, users can restrict their presence information so that it is visible only to the contacts listed in their Lync 2013 Contacts list.</span></span> <span data-ttu-id="45515-106">В командлетах **New – CsPrivacyConfiguration**   и **Set CsPrivacyConfiguration** этот параметр управляется с помощью параметра енаблепривацимоде.</span><span class="sxs-lookup"><span data-stu-id="45515-106">The **New-CsPrivacyConfiguration** and **Set-CsPrivacyConfiguration** cmdlets have an EnablePrivacyMode parameter controls this option.</span></span> <span data-ttu-id="45515-107">Если для Енаблепривацимоде задано значение true, возможность ограничения сведений о присутствии для контактов становится доступной в параметрах состояния Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="45515-107">When EnablePrivacyMode is set to True, the option to restrict presence information to contacts becomes available in the Lync 2013 Status options.</span></span> <span data-ttu-id="45515-108">Когда для EnablePrivacyMode задано значение False, пользователи могут либо разрешить всем остальным просматривать свои сведения, либо принять настройку режима конфиденциальности, выполненную администратором.</span><span class="sxs-lookup"><span data-stu-id="45515-108">When EnablePrivacyMode is set to False, users can choose either to always allow everyone to see their presence information or to adhere to any future changes the administrator makes to the privacy mode.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="45515-109">Параметры конфиденциальности Lync 2013 и Lync 2010 не принимаются в предыдущих версиях (Microsoft Office Communicator 2007 R2 или Microsoft Office Communicator 2007).</span><span class="sxs-lookup"><span data-stu-id="45515-109">Lync 2013 and Lync 2010 privacy settings are not honored by previous versions (Microsoft Office Communicator 2007 R2 or Microsoft Office Communicator 2007).</span></span> <span data-ttu-id="45515-110">Если более ранним версиям Office Communicator разрешено входить в систему, пользователи Lync 2013 могут просмотреть сведения о контакте, контактные данные или фотографию, если кто-то не получил разрешение на просмотр.</span><span class="sxs-lookup"><span data-stu-id="45515-110">If previous versions of Office Communicator are allowed to sign in, a Lync 2013 user’s status, contact information, or picture could be viewed by someone who has not been authorized to view it.</span></span> <span data-ttu-id="45515-111">Кроме того, параметры конфиденциальности пользователя Lync 2013 сбрасываются, если позже он подписывается с помощью предыдущей версии Communicator.</span><span class="sxs-lookup"><span data-stu-id="45515-111">Additionally, a Lync 2013 user’s privacy settings are reset if he or she later signs in with previous version of Communicator.</span></span><BR><span data-ttu-id="45515-112">Поэтому перед включением улучшенного режима конфиденциальности для сведений о присутствии во время миграции выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="45515-112">For these reasons, in a migration scenario, before you enable enhanced presence privacy mode:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="45515-113">Убедитесь, что у каждого пользователя установлен Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="45515-113">Ensure that every user has Lync 2013 installed.</span></span></P>
> <LI>
> <P><span data-ttu-id="45515-114">Определите правило политики для версий клиента, чтобы предотвратить вход с использованием более ранних версий Communicator.</span><span class="sxs-lookup"><span data-stu-id="45515-114">Define a client version policy rule to prevent previous versions of Communicator from signing in.</span></span></P></LI></UL>



</div>

<div>

## <a name="to-enable-enhanced-presence-privacy-mode"></a><span data-ttu-id="45515-115">Включение улучшенного режима конфиденциальности для сведений о присутствии</span><span class="sxs-lookup"><span data-stu-id="45515-115">To enable enhanced presence privacy mode</span></span>

1.  <span data-ttu-id="45515-116">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="45515-116">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="45515-117">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="45515-117">Run the following command:</span></span>
    
        Get-CsPrivacyConfiguration | Set-CsPrivacyConfiguration -EnablePrivacyMode $True
    
    <span data-ttu-id="45515-118">Эта команда включает режим конфиденциальности для всех параметров конфигурации конфиденциальности, которые в текущий момент используются в организации.</span><span class="sxs-lookup"><span data-stu-id="45515-118">This command enables privacy mode for all the privacy configuration settings currently in use in the organization.</span></span> <span data-ttu-id="45515-119">Дополнительные сведения о том, как конфигурации политики режима конфиденциальности для расширенного присутствия в Lync Server управляют присутствием контакта для клиента Lync 2013, в статье базы знаний Майкрософт, которая [Включение режима конфиденциальности Lync Server позволяет обновить состояние присутствия некоторых контактов Lync до "недоступно"](https://support.microsoft.com/kb/3020057).</span><span class="sxs-lookup"><span data-stu-id="45515-119">For more information about how the Lync Server enhanced presence privacy mode policy configurations manages contact presence for the Lync 2013 client, see the Microsoft KB article [Enabling Lync Server enhanced presence privacy mode updates the presence status of some Lync contacts to "unavailable"](https://support.microsoft.com/kb/3020057).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="45515-120">См. также</span><span class="sxs-lookup"><span data-stu-id="45515-120">See Also</span></span>


[<span data-ttu-id="45515-121">Get — CsPrivacyConfiguration</span><span class="sxs-lookup"><span data-stu-id="45515-121">Get-CsPrivacyConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsPrivacyConfiguration)  
[<span data-ttu-id="45515-122">New — CsPrivacyConfiguration</span><span class="sxs-lookup"><span data-stu-id="45515-122">New-CsPrivacyConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsPrivacyConfiguration)  
[<span data-ttu-id="45515-123">Set — CsPrivacyConfiguration</span><span class="sxs-lookup"><span data-stu-id="45515-123">Set-CsPrivacyConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

