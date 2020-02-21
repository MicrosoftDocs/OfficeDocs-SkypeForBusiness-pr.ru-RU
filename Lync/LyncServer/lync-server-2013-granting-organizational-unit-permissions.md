---
title: 'Lync Server 2013: предоставление разрешений организационного подразделения'
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
ms.openlocfilehash: 85c43cb727b83b06d6427e2bf3b6027d78dc025e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199342"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="granting-organizational-unit-permissions-in-lync-server-2013"></a><span data-ttu-id="5e54a-102">Предоставление разрешений организационных подразделений в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e54a-102">Granting organizational unit permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e54a-103">_**Последнее изменение темы:** 2012-05-14_</span><span class="sxs-lookup"><span data-stu-id="5e54a-103">_**Topic Last Modified:** 2012-05-14_</span></span>

<span data-ttu-id="5e54a-104">Вы можете использовать командлет **Grant-CsOuPermission**, чтобы предоставлять разрешения для объектов в указанных подразделениях, чтобы участники универсальных групп, созданных при подготовке леса, могли получать к ним доступ, не входя в группу администраторов домена.</span><span class="sxs-lookup"><span data-stu-id="5e54a-104">You can use the **Grant-CsOuPermission** cmdlet to grant permissions to objects in specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access them without being members of the Domain Admins group.</span></span> <span data-ttu-id="5e54a-105">Разрешения, добавляемые к указанному подразделению — это те же разрешения, которые командлет **Enable-CsAdDomain** добавляется для компьютеров и контейнеров пользователей при подготовке домена.</span><span class="sxs-lookup"><span data-stu-id="5e54a-105">The permissions added to the specified OU are the same permissions that the **Enable-CsAdDomain** cmdlet adds to the computers and users containers during domain preparation.</span></span>

<span data-ttu-id="5e54a-106">С помощью командлета **Test-CsOuPermission** можно проверить разрешения, заданные с использованием командлета **Grant-CsOuPermission**.</span><span class="sxs-lookup"><span data-stu-id="5e54a-106">Use the **Test-CsOuPermission** cmdlet to verify the permissions you set up by using the **Grant-CsOuPermission** cmdlet.</span></span>

<span data-ttu-id="5e54a-107">Вы можете использовать командлет **Revoke-CsOuPermission** для удаления разрешений, предоставленных с помощью командлета **Grant-CsOuPermission**.</span><span class="sxs-lookup"><span data-stu-id="5e54a-107">You can use the **Revoke-CsOuPermission** cmdlet to remove permissions that you granted by using the **Grant-CsOuPermission** cmdlet.</span></span>

<div>

## <a name="to-grant-ou-permissions"></a><span data-ttu-id="5e54a-108">Предоставление разрешений для подразделения</span><span class="sxs-lookup"><span data-stu-id="5e54a-108">To grant OU permissions</span></span>

1.  <span data-ttu-id="5e54a-109">Войдите на компьютер, на котором работает Lync Server 2013, в домене, в котором вы хотите предоставить разрешения для подразделения.</span><span class="sxs-lookup"><span data-stu-id="5e54a-109">Log on to a computer running Lync Server 2013 in the domain where you want to grant OU permissions.</span></span> <span data-ttu-id="5e54a-110">Используйте учетную запись, которая является членом группы администраторов домена или группы администраторов предприятия, если подразделение находится в другом дочернем домене.</span><span class="sxs-lookup"><span data-stu-id="5e54a-110">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="5e54a-111">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="5e54a-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="5e54a-112">Выполняем</span><span class="sxs-lookup"><span data-stu-id="5e54a-112">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="5e54a-113">Если параметр Domain не указан, значением по умолчанию является локальный домен.</span><span class="sxs-lookup"><span data-stu-id="5e54a-113">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-verify-ou-permissions"></a><span data-ttu-id="5e54a-114">Проверка разрешений для подразделения</span><span class="sxs-lookup"><span data-stu-id="5e54a-114">To verify OU permissions</span></span>

1.  <span data-ttu-id="5e54a-115">Войдите на компьютер, на котором работает Lync Server 2013, в домене, в котором необходимо проверить разрешения OU, предоставленные с помощью командлета **Grant – CsOuPermission** .</span><span class="sxs-lookup"><span data-stu-id="5e54a-115">Log on to a computer running Lync Server 2013 in the domain where you want to verify OU permissions that you granted by using the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="5e54a-116">Используйте учетную запись, которая является членом группы администраторов домена или группы администраторов предприятия, если подразделение находится в другом дочернем домене.</span><span class="sxs-lookup"><span data-stu-id="5e54a-116">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="5e54a-117">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="5e54a-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="5e54a-118">Выполняем</span><span class="sxs-lookup"><span data-stu-id="5e54a-118">Run:</span></span>
    
        Test-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="5e54a-119">Если параметр Domain не указан, значением по умолчанию является локальный домен.</span><span class="sxs-lookup"><span data-stu-id="5e54a-119">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-revoke-ou-permissions"></a><span data-ttu-id="5e54a-120">Отзыв разрешений для подразделения</span><span class="sxs-lookup"><span data-stu-id="5e54a-120">To revoke OU permissions</span></span>

1.  <span data-ttu-id="5e54a-121">Войдите на компьютер, на котором работает Lync Server 2013, в домене, в котором вы хотите отозвать разрешения OU, которые были предоставлены командлетом **Grant – CsOuPermission** .</span><span class="sxs-lookup"><span data-stu-id="5e54a-121">Log on to a computer running Lync Server 2013 in the domain where you want to revoke OU permissions that were granted by the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="5e54a-122">Используйте учетную запись, которая является членом группы администраторов домена или группы администраторов предприятия, если подразделение находится в другом дочернем домене.</span><span class="sxs-lookup"><span data-stu-id="5e54a-122">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="5e54a-123">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="5e54a-123">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="5e54a-124">Выполняем</span><span class="sxs-lookup"><span data-stu-id="5e54a-124">Run:</span></span>
    
        Revoke-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="5e54a-125">Если не указать параметр Domain, значением по умолчанию является локальный домен.</span><span class="sxs-lookup"><span data-stu-id="5e54a-125">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

