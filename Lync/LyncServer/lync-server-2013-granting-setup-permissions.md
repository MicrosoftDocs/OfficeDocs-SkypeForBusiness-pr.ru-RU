---
title: 'Lync Server 2013: предоставление разрешений на установку'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Granting setup permissions
ms:assetid: 15982bfe-6844-44f6-815a-72dcaf0e4d21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398225(v=OCS.15)
ms:contentKeyID: 48183491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 751ec9ba024780344596bfc0513c15f7e9eafec7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834118"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="granting-setup-permissions-in-lync-server-2013"></a><span data-ttu-id="9611d-102">Предоставление разрешений на установку в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9611d-102">Granting setup permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9611d-103">_**Тема последнего изменения:** 2012-08-27_</span><span class="sxs-lookup"><span data-stu-id="9611d-103">_**Topic Last Modified:** 2012-08-27_</span></span>

<span data-ttu-id="9611d-104">Вы можете использовать командлет **Grant-кссетуппермиссион** , чтобы добавить разрешения на чтение, запись, Реадспн и вритеспн для группы рткуниверсалсерверадминс для указанного организационного подразделения Active Directory (OU).</span><span class="sxs-lookup"><span data-stu-id="9611d-104">You can use the **Grant-CsSetupPermission** cmdlet to add Read, Write, ReadSPN, and WriteSPN permissions to the RTCUniversalServerAdmins group for a specified Active Directory organizational unit (OU).</span></span> <span data-ttu-id="9611d-105">Затем члены группы Рткуниверсалсерверадминс в этом подразделении могут устанавливать серверы, на которых запущен Lync Server 2013 в указанном домене, и не входить в группу администраторов домена.</span><span class="sxs-lookup"><span data-stu-id="9611d-105">Then members of the RTCUniversalServerAdmins group in that OU can install servers running Lync Server 2013 in the specified domain without being members of the Domain Admins group.</span></span>

<span data-ttu-id="9611d-106">Используйте командлет **Test-кссетуппермиссион** для проверки разрешений, настроенных с помощью командлета **Grant-кссетуппермиссион** .</span><span class="sxs-lookup"><span data-stu-id="9611d-106">Use the **Test-CsSetupPermission** cmdlet to verify the permissions you set up by using the **Grant-CsSetupPermission** cmdlet.</span></span>

<span data-ttu-id="9611d-107">Командлет **REVOKE-кссетуппермиссион** можно использовать для удаления разрешений, предоставленных с помощью командлета **Grant-кссетуппермиссион** .</span><span class="sxs-lookup"><span data-stu-id="9611d-107">You can use the **Revoke-CsSetupPermission** cmdlet to remove permissions that you granted by using the **Grant-CsSetupPermission** cmdlet.</span></span>

<div>

## <a name="to-grant-setup-permissions"></a><span data-ttu-id="9611d-108">Предоставление разрешений на настройку</span><span class="sxs-lookup"><span data-stu-id="9611d-108">To grant setup permissions</span></span>

1.  <span data-ttu-id="9611d-109">Войдите на компьютер, на котором работает Lync Server 2013, в домен, в котором вы хотите предоставить разрешения на установку.</span><span class="sxs-lookup"><span data-stu-id="9611d-109">Log on to a computer running Lync Server 2013 in the domain where you want to grant setup permissions.</span></span> <span data-ttu-id="9611d-110">Используйте учетную запись, которая входит в группу "Администраторы домена" или "Администраторы предприятия", если подразделение находится в другом дочернем домене.</span><span class="sxs-lookup"><span data-stu-id="9611d-110">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="9611d-111">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="9611d-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="9611d-112">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="9611d-112">Run:</span></span>
    
        Grant-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    <span data-ttu-id="9611d-113">Параметр Компутерау можно задать относительно контекста именования по умолчанию для указанного домена (например, CN = Computers).</span><span class="sxs-lookup"><span data-stu-id="9611d-113">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers).</span></span> <span data-ttu-id="9611d-114">Кроме того, вы можете указать этот параметр в качестве полного различающегося имени OU (DN), например "CN = Computers, DC = contoso, DC = com").</span><span class="sxs-lookup"><span data-stu-id="9611d-114">Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com").</span></span> <span data-ttu-id="9611d-115">В последнем случае необходимо указать различающееся имя OU, соответствующее указанному домену.</span><span class="sxs-lookup"><span data-stu-id="9611d-115">In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="9611d-116">Если параметр Domain не указан, значение по умолчанию — локальный домен.</span><span class="sxs-lookup"><span data-stu-id="9611d-116">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-verify-setup-permissions"></a><span data-ttu-id="9611d-117">Проверка разрешений на установку</span><span class="sxs-lookup"><span data-stu-id="9611d-117">To verify setup permissions</span></span>

1.  <span data-ttu-id="9611d-118">Войдите на компьютер, на котором работает Lync Server 2013, в домен, в котором вы хотите проверить разрешения на установку, предоставленные с помощью командлета **Grant-кссетуппермиссион** .</span><span class="sxs-lookup"><span data-stu-id="9611d-118">Log on to a computer running Lync Server 2013 in the domain where you want to verify setup permissions that you granted by using the **Grant-CsSetupPermission** cmdlet.</span></span> <span data-ttu-id="9611d-119">Используйте учетную запись, которая входит в группу "Администраторы домена" или "Администраторы предприятия", если подразделение находится в другом дочернем домене.</span><span class="sxs-lookup"><span data-stu-id="9611d-119">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="9611d-120">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="9611d-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="9611d-121">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="9611d-121">Run:</span></span>
    
        Test-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="9611d-122">Параметр Компутерау можно задать относительно контекста именования по умолчанию для указанного домена (например, CN = Computers).</span><span class="sxs-lookup"><span data-stu-id="9611d-122">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers).</span></span> <span data-ttu-id="9611d-123">Кроме того, вы можете указать этот параметр в качестве полного различающегося имени OU (DN), например "CN = Computers, DC = contoso, DC = com").</span><span class="sxs-lookup"><span data-stu-id="9611d-123">Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com").</span></span> <span data-ttu-id="9611d-124">В последнем случае необходимо указать различающееся имя OU, соответствующее указанному домену.</span><span class="sxs-lookup"><span data-stu-id="9611d-124">In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="9611d-125">Если параметр Domain не указан, значение по умолчанию — локальный домен.</span><span class="sxs-lookup"><span data-stu-id="9611d-125">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-revoke-setup-permissions"></a><span data-ttu-id="9611d-126">Отмена разрешений на установку</span><span class="sxs-lookup"><span data-stu-id="9611d-126">To revoke setup permissions</span></span>

1.  <span data-ttu-id="9611d-127">Войдите на компьютер, на котором работает Lync Server 2013, в домен, для которого вы хотите отозвать разрешения на установку, предоставленные командлетом **Grant-кссетуппермиссион** .</span><span class="sxs-lookup"><span data-stu-id="9611d-127">Log on to a computer running Lync Server 2013 in the domain where you want to revoke setup permissions that were granted by the **Grant-CsSetupPermission** cmdlet.</span></span> <span data-ttu-id="9611d-128">Используйте учетную запись, которая входит в группу "Администраторы домена" или "Администраторы предприятия", если подразделение находится в другом дочернем домене.</span><span class="sxs-lookup"><span data-stu-id="9611d-128">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="9611d-129">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="9611d-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="9611d-130">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="9611d-130">Run:</span></span>
    
        Revoke-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    <span data-ttu-id="9611d-131">Параметр Компутерау можно задать относительно контекста именования по умолчанию для указанного домена (например, CN = Computers).</span><span class="sxs-lookup"><span data-stu-id="9611d-131">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers).</span></span> <span data-ttu-id="9611d-132">Кроме того, вы можете указать этот параметр в качестве полного различающегося имени OU (DN), например "CN = Computers, DC = contoso, DC = com").</span><span class="sxs-lookup"><span data-stu-id="9611d-132">Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com").</span></span> <span data-ttu-id="9611d-133">В последнем случае необходимо указать различающееся имя OU, соответствующее указанному домену.</span><span class="sxs-lookup"><span data-stu-id="9611d-133">In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="9611d-134">Если параметр Domain не указан, значение по умолчанию — локальный домен.</span><span class="sxs-lookup"><span data-stu-id="9611d-134">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

