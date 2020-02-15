---
title: 'Lync Server 2013: предоставление разрешений на установку'
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
ms.openlocfilehash: 61fb0f5eac11016cf21dd8691ed9fa5f97bc804f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030412"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="granting-setup-permissions-in-lync-server-2013"></a><span data-ttu-id="e7d7e-102">Предоставление разрешений на установку в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7d7e-102">Granting setup permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7d7e-103">_**Последнее изменение темы:** 2012-08-27_</span><span class="sxs-lookup"><span data-stu-id="e7d7e-103">_**Topic Last Modified:** 2012-08-27_</span></span>

<span data-ttu-id="e7d7e-104">Командлет **Grant-CsSetupPermission** можно использовать для добавления разрешений уровня Read, Write, ReadSPN и WriteSPN в группу RTCUniversalServerAdmins для указанного подразделения Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e7d7e-104">You can use the **Grant-CsSetupPermission** cmdlet to add Read, Write, ReadSPN, and WriteSPN permissions to the RTCUniversalServerAdmins group for a specified Active Directory organizational unit (OU).</span></span> <span data-ttu-id="e7d7e-105">Затем члены группы RTCUniversalServerAdmins в этом подразделении могут устанавливать серверы, на которых работает Lync Server 2013, в указанном домене, не выполняя членство в группе "Администраторы домена".</span><span class="sxs-lookup"><span data-stu-id="e7d7e-105">Then members of the RTCUniversalServerAdmins group in that OU can install servers running Lync Server 2013 in the specified domain without being members of the Domain Admins group.</span></span>

<span data-ttu-id="e7d7e-106">Используйте командлет **Test-CsSetupPermission** для проверки разрешений, заданных с помощью командлета **Grant-CsSetupPermission**.</span><span class="sxs-lookup"><span data-stu-id="e7d7e-106">Use the **Test-CsSetupPermission** cmdlet to verify the permissions you set up by using the **Grant-CsSetupPermission** cmdlet.</span></span>

<span data-ttu-id="e7d7e-107">Командлет **Revoke-CsSetupPermission** можно использовать для удаления разрешений, предоставленных с помощью командлета **Grant-CsSetupPermission**.</span><span class="sxs-lookup"><span data-stu-id="e7d7e-107">You can use the **Revoke-CsSetupPermission** cmdlet to remove permissions that you granted by using the **Grant-CsSetupPermission** cmdlet.</span></span>

<div>

## <a name="to-grant-setup-permissions"></a><span data-ttu-id="e7d7e-108">Порядок предоставления разрешений на установку</span><span class="sxs-lookup"><span data-stu-id="e7d7e-108">To grant setup permissions</span></span>

1.  <span data-ttu-id="e7d7e-109">Войдите на компьютер, на котором работает Lync Server 2013, в домене, в котором вы хотите предоставить разрешения на установку.</span><span class="sxs-lookup"><span data-stu-id="e7d7e-109">Log on to a computer running Lync Server 2013 in the domain where you want to grant setup permissions.</span></span> <span data-ttu-id="e7d7e-110">Используйте учетную запись, которая является членом группы администраторов домена или группы администраторов предприятия, если подразделение находится в другом дочернем домене.</span><span class="sxs-lookup"><span data-stu-id="e7d7e-110">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="e7d7e-111">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="e7d7e-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="e7d7e-112">Выполняем</span><span class="sxs-lookup"><span data-stu-id="e7d7e-112">Run:</span></span>
    
        Grant-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    <span data-ttu-id="e7d7e-p103">Можно указать параметр ComputerOu в соответствии с контекстом именования по умолчанию указанного домена (например, CN=Computers). Кроме того, можно указать этот параметр как полное различающееся имя подразделения (например, CN=Computers, DC=Contoso, dc=com). В последнем случае необходимо указать полное различающееся имя подразделения, соответствующее указанному домену.</span><span class="sxs-lookup"><span data-stu-id="e7d7e-p103">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers). Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com"). In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="e7d7e-116">Если параметр «Домен» не указан, по умолчанию в качестве значения используется локальный домен.</span><span class="sxs-lookup"><span data-stu-id="e7d7e-116">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-verify-setup-permissions"></a><span data-ttu-id="e7d7e-117">Проверка разрешений на установку</span><span class="sxs-lookup"><span data-stu-id="e7d7e-117">To verify setup permissions</span></span>

1.  <span data-ttu-id="e7d7e-118">Войдите на компьютер, на котором работает Lync Server 2013, в домене, в котором необходимо проверить разрешения программы установки, предоставленные с помощью командлета **Grant – CsSetupPermission** .</span><span class="sxs-lookup"><span data-stu-id="e7d7e-118">Log on to a computer running Lync Server 2013 in the domain where you want to verify setup permissions that you granted by using the **Grant-CsSetupPermission** cmdlet.</span></span> <span data-ttu-id="e7d7e-119">Используйте учетную запись, которая является членом группы администраторов домена или группы администраторов предприятия, если подразделение находится в другом дочернем домене.</span><span class="sxs-lookup"><span data-stu-id="e7d7e-119">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="e7d7e-120">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="e7d7e-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="e7d7e-121">Выполняем</span><span class="sxs-lookup"><span data-stu-id="e7d7e-121">Run:</span></span>
    
        Test-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="e7d7e-p105">Можно указать параметр ComputerOu в соответствии с контекстом именования по умолчанию указанного домена (например, CN=Computers). Кроме того, можно указать этот параметр как полное различающееся имя подразделения (например, CN=Computers, DC=Contoso, dc=com). В последнем случае необходимо указать полное различающееся имя подразделения, соответствующее указанному домену.</span><span class="sxs-lookup"><span data-stu-id="e7d7e-p105">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers). Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com"). In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="e7d7e-125">Если параметр «Домен» не указан, по умолчанию в качестве значения используется локальный домен.</span><span class="sxs-lookup"><span data-stu-id="e7d7e-125">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-revoke-setup-permissions"></a><span data-ttu-id="e7d7e-126">Аннулирование разрешений на установку</span><span class="sxs-lookup"><span data-stu-id="e7d7e-126">To revoke setup permissions</span></span>

1.  <span data-ttu-id="e7d7e-127">Войдите на компьютер, на котором работает Lync Server 2013, в домене, для которого требуется отозвать разрешения на установку, предоставленные командлетом **Grant – CsSetupPermission** .</span><span class="sxs-lookup"><span data-stu-id="e7d7e-127">Log on to a computer running Lync Server 2013 in the domain where you want to revoke setup permissions that were granted by the **Grant-CsSetupPermission** cmdlet.</span></span> <span data-ttu-id="e7d7e-128">Используйте учетную запись, которая является членом группы администраторов домена или группы администраторов предприятия, если подразделение находится в другом дочернем домене.</span><span class="sxs-lookup"><span data-stu-id="e7d7e-128">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="e7d7e-129">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="e7d7e-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="e7d7e-130">Выполняем</span><span class="sxs-lookup"><span data-stu-id="e7d7e-130">Run:</span></span>
    
        Revoke-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    <span data-ttu-id="e7d7e-p107">Можно указать параметр ComputerOu в соответствии с контекстом именования по умолчанию указанного домена (например, CN=Computers). Кроме того, можно указать этот параметр как полное различающееся имя подразделения (например, CN=Computers, DC=Contoso, dc=com). В последнем случае необходимо указать полное различающееся имя подразделения, соответствующее указанному домену.</span><span class="sxs-lookup"><span data-stu-id="e7d7e-p107">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers). Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com"). In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="e7d7e-134">Если параметр «Домен» не указан, по умолчанию в качестве значения используется локальный домен.</span><span class="sxs-lookup"><span data-stu-id="e7d7e-134">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

