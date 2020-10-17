---
title: 'Lync Server 2013: предоставление разрешений организационного подразделения'
description: 'Lync Server 2013: предоставление разрешений организационного подразделения.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting organizational unit permissions
ms:assetid: 95ee5ffa-39b1-4d80-87a2-27bb364f7396
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398763(v=OCS.15)
ms:contentKeyID: 48184849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47ad862241e409190620afa7dbf4fa73adf339de
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554515"
---
# <a name="granting-organizational-unit-permissions-in-lync-server-2013"></a><span data-ttu-id="c0fc2-103">Предоставление разрешений организационных подразделений в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c0fc2-103">Granting organizational unit permissions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0fc2-104">_**Последнее изменение темы:** 2012-05-14_</span><span class="sxs-lookup"><span data-stu-id="c0fc2-104">_**Topic Last Modified:** 2012-05-14_</span></span>

<span data-ttu-id="c0fc2-105">Вы можете использовать командлет **Grant-CsOuPermission**, чтобы предоставлять разрешения для объектов в указанных подразделениях, чтобы участники универсальных групп, созданных при подготовке леса, могли получать к ним доступ, не входя в группу администраторов домена.</span><span class="sxs-lookup"><span data-stu-id="c0fc2-105">You can use the **Grant-CsOuPermission** cmdlet to grant permissions to objects in specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access them without being members of the Domain Admins group.</span></span> <span data-ttu-id="c0fc2-106">Разрешения, добавляемые к указанному подразделению — это те же разрешения, которые командлет **Enable-CsAdDomain** добавляется для компьютеров и контейнеров пользователей при подготовке домена.</span><span class="sxs-lookup"><span data-stu-id="c0fc2-106">The permissions added to the specified OU are the same permissions that the **Enable-CsAdDomain** cmdlet adds to the computers and users containers during domain preparation.</span></span>

<span data-ttu-id="c0fc2-107">С помощью командлета **Test-CsOuPermission** можно проверить разрешения, заданные с использованием командлета **Grant-CsOuPermission**.</span><span class="sxs-lookup"><span data-stu-id="c0fc2-107">Use the **Test-CsOuPermission** cmdlet to verify the permissions you set up by using the **Grant-CsOuPermission** cmdlet.</span></span>

<span data-ttu-id="c0fc2-108">Вы можете использовать командлет **Revoke-CsOuPermission** для удаления разрешений, предоставленных с помощью командлета **Grant-CsOuPermission**.</span><span class="sxs-lookup"><span data-stu-id="c0fc2-108">You can use the **Revoke-CsOuPermission** cmdlet to remove permissions that you granted by using the **Grant-CsOuPermission** cmdlet.</span></span>

<div>

## <a name="to-grant-ou-permissions"></a><span data-ttu-id="c0fc2-109">Предоставление разрешений для подразделения</span><span class="sxs-lookup"><span data-stu-id="c0fc2-109">To grant OU permissions</span></span>

1.  <span data-ttu-id="c0fc2-110">Войдите на компьютер, на котором работает Lync Server 2013, в домене, в котором вы хотите предоставить разрешения для подразделения.</span><span class="sxs-lookup"><span data-stu-id="c0fc2-110">Log on to a computer running Lync Server 2013 in the domain where you want to grant OU permissions.</span></span> <span data-ttu-id="c0fc2-111">Используйте учетную запись, которая является членом группы администраторов домена или группы администраторов предприятия, если подразделение находится в другом дочернем домене.</span><span class="sxs-lookup"><span data-stu-id="c0fc2-111">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="c0fc2-112">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="c0fc2-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="c0fc2-113">Выполняем</span><span class="sxs-lookup"><span data-stu-id="c0fc2-113">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="c0fc2-114">Если не указать параметр Domain, значением по умолчанию является локальный домен.</span><span class="sxs-lookup"><span data-stu-id="c0fc2-114">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-verify-ou-permissions"></a><span data-ttu-id="c0fc2-115">Проверка разрешений для подразделения</span><span class="sxs-lookup"><span data-stu-id="c0fc2-115">To verify OU permissions</span></span>

1.  <span data-ttu-id="c0fc2-116">Войдите на компьютер, на котором работает Lync Server 2013, в домене, в котором необходимо проверить разрешения OU, предоставленные с помощью командлета **Grant – CsOuPermission** .</span><span class="sxs-lookup"><span data-stu-id="c0fc2-116">Log on to a computer running Lync Server 2013 in the domain where you want to verify OU permissions that you granted by using the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="c0fc2-117">Используйте учетную запись, которая является членом группы администраторов домена или группы администраторов предприятия, если подразделение находится в другом дочернем домене.</span><span class="sxs-lookup"><span data-stu-id="c0fc2-117">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="c0fc2-118">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="c0fc2-118">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="c0fc2-119">Выполняем</span><span class="sxs-lookup"><span data-stu-id="c0fc2-119">Run:</span></span>
    
        Test-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="c0fc2-120">Если не указать параметр Domain, значением по умолчанию является локальный домен.</span><span class="sxs-lookup"><span data-stu-id="c0fc2-120">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-revoke-ou-permissions"></a><span data-ttu-id="c0fc2-121">Отзыв разрешений для подразделения</span><span class="sxs-lookup"><span data-stu-id="c0fc2-121">To revoke OU permissions</span></span>

1.  <span data-ttu-id="c0fc2-122">Войдите на компьютер, на котором работает Lync Server 2013, в домене, в котором вы хотите отозвать разрешения OU, которые были предоставлены командлетом **Grant – CsOuPermission** .</span><span class="sxs-lookup"><span data-stu-id="c0fc2-122">Log on to a computer running Lync Server 2013 in the domain where you want to revoke OU permissions that were granted by the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="c0fc2-123">Используйте учетную запись, которая является членом группы администраторов домена или группы администраторов предприятия, если подразделение находится в другом дочернем домене.</span><span class="sxs-lookup"><span data-stu-id="c0fc2-123">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="c0fc2-124">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="c0fc2-124">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="c0fc2-125">Выполняем</span><span class="sxs-lookup"><span data-stu-id="c0fc2-125">Run:</span></span>
    
        Revoke-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="c0fc2-126">Если не указать параметр Domain, значением по умолчанию является локальный домен.</span><span class="sxs-lookup"><span data-stu-id="c0fc2-126">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

