---
title: 'Lync Server 2013: предоставление разрешений на установку'
description: 'Lync Server 2013: предоставление разрешений на установку.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting setup permissions
ms:assetid: 15982bfe-6844-44f6-815a-72dcaf0e4d21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398225(v=OCS.15)
ms:contentKeyID: 48183491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5523494219d07907caeefc1bd139c41856effa54
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554485"
---
# <a name="granting-setup-permissions-in-lync-server-2013"></a><span data-ttu-id="4f676-103">Предоставление разрешений на установку в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f676-103">Granting setup permissions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f676-104">_**Последнее изменение темы:** 2012-08-27_</span><span class="sxs-lookup"><span data-stu-id="4f676-104">_**Topic Last Modified:** 2012-08-27_</span></span>

<span data-ttu-id="4f676-105">Командлет **Grant-CsSetupPermission** можно использовать для добавления разрешений уровня Read, Write, ReadSPN и WriteSPN в группу RTCUniversalServerAdmins для указанного подразделения Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4f676-105">You can use the **Grant-CsSetupPermission** cmdlet to add Read, Write, ReadSPN, and WriteSPN permissions to the RTCUniversalServerAdmins group for a specified Active Directory organizational unit (OU).</span></span> <span data-ttu-id="4f676-106">Затем члены группы RTCUniversalServerAdmins в этом подразделении могут устанавливать серверы, на которых работает Lync Server 2013, в указанном домене, не выполняя членство в группе "Администраторы домена".</span><span class="sxs-lookup"><span data-stu-id="4f676-106">Then members of the RTCUniversalServerAdmins group in that OU can install servers running Lync Server 2013 in the specified domain without being members of the Domain Admins group.</span></span>

<span data-ttu-id="4f676-107">Используйте командлет **Test-CsSetupPermission** для проверки разрешений, заданных с помощью командлета **Grant-CsSetupPermission**.</span><span class="sxs-lookup"><span data-stu-id="4f676-107">Use the **Test-CsSetupPermission** cmdlet to verify the permissions you set up by using the **Grant-CsSetupPermission** cmdlet.</span></span>

<span data-ttu-id="4f676-108">Командлет **Revoke-CsSetupPermission** можно использовать для удаления разрешений, предоставленных с помощью командлета **Grant-CsSetupPermission**.</span><span class="sxs-lookup"><span data-stu-id="4f676-108">You can use the **Revoke-CsSetupPermission** cmdlet to remove permissions that you granted by using the **Grant-CsSetupPermission** cmdlet.</span></span>

<div>

## <a name="to-grant-setup-permissions"></a><span data-ttu-id="4f676-109">Порядок предоставления разрешений на установку</span><span class="sxs-lookup"><span data-stu-id="4f676-109">To grant setup permissions</span></span>

1.  <span data-ttu-id="4f676-110">Войдите на компьютер, на котором работает Lync Server 2013, в домене, в котором вы хотите предоставить разрешения на установку.</span><span class="sxs-lookup"><span data-stu-id="4f676-110">Log on to a computer running Lync Server 2013 in the domain where you want to grant setup permissions.</span></span> <span data-ttu-id="4f676-111">Используйте учетную запись, которая является членом группы администраторов домена или группы администраторов предприятия, если подразделение находится в другом дочернем домене.</span><span class="sxs-lookup"><span data-stu-id="4f676-111">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="4f676-112">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="4f676-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="4f676-113">Выполняем</span><span class="sxs-lookup"><span data-stu-id="4f676-113">Run:</span></span>
    
        Grant-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    <span data-ttu-id="4f676-p103">Можно указать параметр ComputerOu в соответствии с контекстом именования по умолчанию указанного домена (например, CN=Computers). Кроме того, можно указать этот параметр как полное различающееся имя подразделения (например, CN=Computers, DC=Contoso, dc=com). В последнем случае необходимо указать полное различающееся имя подразделения, соответствующее указанному домену.</span><span class="sxs-lookup"><span data-stu-id="4f676-p103">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers). Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com"). In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="4f676-117">Если параметр «Домен» не указан, по умолчанию в качестве значения используется локальный домен.</span><span class="sxs-lookup"><span data-stu-id="4f676-117">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-verify-setup-permissions"></a><span data-ttu-id="4f676-118">Проверка разрешений на установку</span><span class="sxs-lookup"><span data-stu-id="4f676-118">To verify setup permissions</span></span>

1.  <span data-ttu-id="4f676-119">Войдите на компьютер, на котором работает Lync Server 2013, в домене, в котором необходимо проверить разрешения программы установки, предоставленные с помощью командлета **Grant – CsSetupPermission** .</span><span class="sxs-lookup"><span data-stu-id="4f676-119">Log on to a computer running Lync Server 2013 in the domain where you want to verify setup permissions that you granted by using the **Grant-CsSetupPermission** cmdlet.</span></span> <span data-ttu-id="4f676-120">Используйте учетную запись, которая является членом группы администраторов домена или группы администраторов предприятия, если подразделение находится в другом дочернем домене.</span><span class="sxs-lookup"><span data-stu-id="4f676-120">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="4f676-121">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="4f676-121">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="4f676-122">Выполняем</span><span class="sxs-lookup"><span data-stu-id="4f676-122">Run:</span></span>
    
        Test-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="4f676-p105">Можно указать параметр ComputerOu в соответствии с контекстом именования по умолчанию указанного домена (например, CN=Computers). Кроме того, можно указать этот параметр как полное различающееся имя подразделения (например, CN=Computers, DC=Contoso, dc=com). В последнем случае необходимо указать полное различающееся имя подразделения, соответствующее указанному домену.</span><span class="sxs-lookup"><span data-stu-id="4f676-p105">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers). Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com"). In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="4f676-126">Если параметр «Домен» не указан, по умолчанию в качестве значения используется локальный домен.</span><span class="sxs-lookup"><span data-stu-id="4f676-126">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-revoke-setup-permissions"></a><span data-ttu-id="4f676-127">Аннулирование разрешений на установку</span><span class="sxs-lookup"><span data-stu-id="4f676-127">To revoke setup permissions</span></span>

1.  <span data-ttu-id="4f676-128">Войдите на компьютер, на котором работает Lync Server 2013, в домене, для которого требуется отозвать разрешения на установку, предоставленные командлетом **Grant – CsSetupPermission** .</span><span class="sxs-lookup"><span data-stu-id="4f676-128">Log on to a computer running Lync Server 2013 in the domain where you want to revoke setup permissions that were granted by the **Grant-CsSetupPermission** cmdlet.</span></span> <span data-ttu-id="4f676-129">Используйте учетную запись, которая является членом группы администраторов домена или группы администраторов предприятия, если подразделение находится в другом дочернем домене.</span><span class="sxs-lookup"><span data-stu-id="4f676-129">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="4f676-130">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="4f676-130">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="4f676-131">Выполняем</span><span class="sxs-lookup"><span data-stu-id="4f676-131">Run:</span></span>
    
        Revoke-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    <span data-ttu-id="4f676-p107">Можно указать параметр ComputerOu в соответствии с контекстом именования по умолчанию указанного домена (например, CN=Computers). Кроме того, можно указать этот параметр как полное различающееся имя подразделения (например, CN=Computers, DC=Contoso, dc=com). В последнем случае необходимо указать полное различающееся имя подразделения, соответствующее указанному домену.</span><span class="sxs-lookup"><span data-stu-id="4f676-p107">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers). Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com"). In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="4f676-135">Если параметр «Домен» не указан, по умолчанию в качестве значения используется локальный домен.</span><span class="sxs-lookup"><span data-stu-id="4f676-135">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

