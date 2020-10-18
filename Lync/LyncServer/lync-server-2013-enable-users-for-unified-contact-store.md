---
title: 'Lync Server 2013: включение пользователей для единого хранилища контактов'
description: 'Lync Server 2013: включение пользователей для единого хранилища контактов.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable users for unified contact store
ms:assetid: 7b46a01f-beb5-4a33-adb0-35f0502b168d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205024(v=OCS.15)
ms:contentKeyID: 48184599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2249249d314e13d840b276e46f1fe38ad271664a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572735"
---
# <a name="enable-users-for-unified-contact-store-in-lync-server-2013"></a><span data-ttu-id="7a3d0-103">Включение пользователей для единого хранилища контактов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7a3d0-103">Enable users for unified contact store in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a3d0-104">_**Последнее изменение темы:** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="7a3d0-104">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="7a3d0-105">При развертывании Lync Server 2013 и публикации топологии единое хранилище контактов включено для всех пользователей по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7a3d0-105">When you deploy Lync Server 2013 and publish the topology, unified contact store is enabled for all users by default.</span></span> <span data-ttu-id="7a3d0-106">Для включения единого хранилища контактов после развертывания Lync Server 2013 не требуется предпринимать никаких дополнительных действий.</span><span class="sxs-lookup"><span data-stu-id="7a3d0-106">You do not need to take any additional action to enable unified contact store after you deploy Lync Server 2013.</span></span> <span data-ttu-id="7a3d0-107">Однако можно использовать командлет **Set-CsUserServicesPolicy**, чтобы указать, каким пользователям доступно единое хранилище контактов.</span><span class="sxs-lookup"><span data-stu-id="7a3d0-107">However, you can use the **Set-CsUserServicesPolicy** cmdlet to customize which users have unified contact store available.</span></span> <span data-ttu-id="7a3d0-108">Эту возможность можно включать глобально, по узлам, по клиентам, по отдельности или группами.</span><span class="sxs-lookup"><span data-stu-id="7a3d0-108">You can enable this feature globally, by site, by tenant, or by individuals or groups of individuals.</span></span>

<div>

## <a name="to-enable-users-for-unified-contact-store"></a><span data-ttu-id="7a3d0-109">Включение для пользователей единого хранилища контактов</span><span class="sxs-lookup"><span data-stu-id="7a3d0-109">To enable users for unified contact store</span></span>

1.  <span data-ttu-id="7a3d0-110">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="7a3d0-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="7a3d0-111">Выполните любые из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="7a3d0-111">Do any of the following:</span></span>
    
      - <span data-ttu-id="7a3d0-112">Чтобы включить единое хранилище контактов глобально для всех пользователей Lync Server, в командной строке введите:</span><span class="sxs-lookup"><span data-stu-id="7a3d0-112">To enable unified contact store globally for all Lync Server users, at the command line, type:</span></span>
        
            Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
    
      - <span data-ttu-id="7a3d0-113">Чтобы включить единое хранилище контактов для пользователей на конкретном сайте, в командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="7a3d0-113">To enable unified contact store for the users at a specific site, at the command line, type:</span></span>
        
            New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
        
        <span data-ttu-id="7a3d0-114">For example:</span><span class="sxs-lookup"><span data-stu-id="7a3d0-114">For example:</span></span>
        
            New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
    
      - <span data-ttu-id="7a3d0-115">Чтобы включить единое хранилище контактов по клиентам, в командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="7a3d0-115">To enable unified contact store by tenant, at the command line, type:</span></span>
        
            Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
        
        <span data-ttu-id="7a3d0-116">Например:</span><span class="sxs-lookup"><span data-stu-id="7a3d0-116">For example:</span></span>
        
            Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
    
      - <span data-ttu-id="7a3d0-117">Чтобы включить единое хранилище контактов для конкретных пользователей, в командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="7a3d0-117">To enable unified contact store for specific users, at the command line, type:</span></span>
        
            New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="7a3d0-118">Вместо отображаемых имен пользователей можно использовать псевдонимы или SIP URI.</span><span class="sxs-lookup"><span data-stu-id="7a3d0-118">You can also use user alias or SIP URI instead of the user display name.</span></span>

        
        </div>
        
        <span data-ttu-id="7a3d0-119">Например:</span><span class="sxs-lookup"><span data-stu-id="7a3d0-119">For example:</span></span>
        
            New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="7a3d0-p102">В предыдущем примере первая команда создает новую политику на уровне пользователя с именем <EM>UCS Enabled Users</EM> и с флагом UcsAllowed, установленным в значение True. Вторая команда назначает эту политику пользователю с отображаемым именем Ken Myer, что означает, что теперь Кену Майеру разрешен доступ к единому хранилищу контактов.</span><span class="sxs-lookup"><span data-stu-id="7a3d0-p102">In the preceding example, the first command creates a new per-user policy named <EM>UCS Enabled Users</EM> with the UcsAllowed flag set to True. The second command assigns the policy to the user with the display name Ken Myer, which means that Ken Myer is now enabled for unified contact store.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

