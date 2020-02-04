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
ms.openlocfilehash: 084fb8cdebeda06d4441879f08f830021b65d2e3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763913"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="granting-organizational-unit-permissions-in-lync-server-2013"></a><span data-ttu-id="7590e-102">Предоставление разрешений организационного подразделения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7590e-102">Granting organizational unit permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7590e-103">_**Тема последнего изменения:** 2012-05-14_</span><span class="sxs-lookup"><span data-stu-id="7590e-103">_**Topic Last Modified:** 2012-05-14_</span></span>

<span data-ttu-id="7590e-104">Командлет **Grant-ксаупермиссион** можно использовать, чтобы предоставить разрешения на доступ к объектам в указанных организационных подразделениях (OU) таким образом, чтобы пользователи универсальных групп RTC, созданные с помощью подготовки леса, могли получать к ним доступа, не прибегая к группе администраторов домена.</span><span class="sxs-lookup"><span data-stu-id="7590e-104">You can use the **Grant-CsOuPermission** cmdlet to grant permissions to objects in specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access them without being members of the Domain Admins group.</span></span> <span data-ttu-id="7590e-105">Разрешения, добавленные в указанный ОРГАНИЗАЦИОНный элемент, являются теми же разрешениями, которые командлет **Enable-ксаддомаин** добавляет к контейнерам компьютеров и пользователей во время подготовки домена.</span><span class="sxs-lookup"><span data-stu-id="7590e-105">The permissions added to the specified OU are the same permissions that the **Enable-CsAdDomain** cmdlet adds to the computers and users containers during domain preparation.</span></span>

<span data-ttu-id="7590e-106">Используйте командлет **Test-ксаупермиссион** для проверки разрешений, настроенных с помощью командлета **Grant-ксаупермиссион** .</span><span class="sxs-lookup"><span data-stu-id="7590e-106">Use the **Test-CsOuPermission** cmdlet to verify the permissions you set up by using the **Grant-CsOuPermission** cmdlet.</span></span>

<span data-ttu-id="7590e-107">Командлет **REVOKE-ксаупермиссион** можно использовать для удаления разрешений, предоставленных с помощью командлета **Grant-ксаупермиссион** .</span><span class="sxs-lookup"><span data-stu-id="7590e-107">You can use the **Revoke-CsOuPermission** cmdlet to remove permissions that you granted by using the **Grant-CsOuPermission** cmdlet.</span></span>

<div>

## <a name="to-grant-ou-permissions"></a><span data-ttu-id="7590e-108">Предоставление разрешений на доступ к подразделению</span><span class="sxs-lookup"><span data-stu-id="7590e-108">To grant OU permissions</span></span>

1.  <span data-ttu-id="7590e-109">Войдите на компьютер, на котором работает Lync Server 2013, в домен, в котором вы хотите предоставить разрешения на доступ к подразделению.</span><span class="sxs-lookup"><span data-stu-id="7590e-109">Log on to a computer running Lync Server 2013 in the domain where you want to grant OU permissions.</span></span> <span data-ttu-id="7590e-110">Используйте учетную запись, которая входит в группу "Администраторы домена" или "Администраторы предприятия", если подразделение находится в другом дочернем домене.</span><span class="sxs-lookup"><span data-stu-id="7590e-110">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="7590e-111">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="7590e-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="7590e-112">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="7590e-112">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="7590e-113">Если параметр Domain не указан, значение по умолчанию — локальный домен.</span><span class="sxs-lookup"><span data-stu-id="7590e-113">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-verify-ou-permissions"></a><span data-ttu-id="7590e-114">Проверка разрешений на доступ к подразделению</span><span class="sxs-lookup"><span data-stu-id="7590e-114">To verify OU permissions</span></span>

1.  <span data-ttu-id="7590e-115">Войдите на компьютер, на котором работает Lync Server 2013, в домен, в котором вы хотите проверить разрешения на доступ к подразделению, предоставленные с помощью командлета **Grant-ксаупермиссион** .</span><span class="sxs-lookup"><span data-stu-id="7590e-115">Log on to a computer running Lync Server 2013 in the domain where you want to verify OU permissions that you granted by using the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="7590e-116">Используйте учетную запись, которая входит в группу "Администраторы домена" или "Администраторы предприятия", если подразделение находится в другом дочернем домене.</span><span class="sxs-lookup"><span data-stu-id="7590e-116">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="7590e-117">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="7590e-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="7590e-118">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="7590e-118">Run:</span></span>
    
        Test-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="7590e-119">Если параметр Domain не указан, значение по умолчанию — локальный домен.</span><span class="sxs-lookup"><span data-stu-id="7590e-119">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-revoke-ou-permissions"></a><span data-ttu-id="7590e-120">Отмена разрешений на доступ к подразделению</span><span class="sxs-lookup"><span data-stu-id="7590e-120">To revoke OU permissions</span></span>

1.  <span data-ttu-id="7590e-121">Войдите на компьютер, на котором работает Lync Server 2013, в домен, в котором вы хотите отозвать разрешения на доступ к подразделению, предоставленные командлетом **Grant-ксаупермиссион** .</span><span class="sxs-lookup"><span data-stu-id="7590e-121">Log on to a computer running Lync Server 2013 in the domain where you want to revoke OU permissions that were granted by the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="7590e-122">Используйте учетную запись, которая входит в группу "Администраторы домена" или "Администраторы предприятия", если подразделение находится в другом дочернем домене.</span><span class="sxs-lookup"><span data-stu-id="7590e-122">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="7590e-123">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="7590e-123">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="7590e-124">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="7590e-124">Run:</span></span>
    
        Revoke-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="7590e-125">Если параметр Domain не указан, значение по умолчанию — локальный домен.</span><span class="sxs-lookup"><span data-stu-id="7590e-125">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

