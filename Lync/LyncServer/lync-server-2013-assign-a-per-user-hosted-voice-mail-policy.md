---
title: 'Lync Server 2013: назначение политики размещенной голосовой почты для отдельных пользователей'
description: 'Lync Server 2013: назначение политики размещенной голосовой почты на уровне пользователя.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user hosted voice mail policy
ms:assetid: d44c71a0-4407-4ab4-b7e0-d671dde3425f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398919(v=OCS.15)
ms:contentKeyID: 48185456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 071d504c452b4d3adb1b636cb5c4ff8835200107
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559895"
---
# <a name="assign-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="8910e-103">Назначение политики размещенной голосовой почты на уровне пользователя в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8910e-103">Assign a per-user hosted voice mail policy in Lync Server 2013</span></span>

 


<span data-ttu-id="8910e-p101">Развертывание одной или нескольких политик маршрутизации размещенной голосовой почты для отдельных пользователей выполняется по желанию. Если требуется выполнить развертывание для отдельных пользователей, необходимо явно назначить эти политики пользователям, группам или контактным объектам.</span><span class="sxs-lookup"><span data-stu-id="8910e-p101">Deploying one or more per-user hosted voice mail policies is optional. If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact objects.</span></span>

<span data-ttu-id="8910e-106">Для получения дополнительных сведений о назначении и удалении назначений политик голосовой почты, размещенных на уровне пользователя, обратитесь к документации по командной консоли Lync Server для следующих командлетов:</span><span class="sxs-lookup"><span data-stu-id="8910e-106">For details about assigning or removing the assignment of per-user hosted voice mail policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="8910e-107">Grant-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="8910e-107">Grant-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="8910e-108">Remove-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="8910e-108">Remove-CsHostedVoicemailPolicy</span></span>

## <a name="to-assign-a-per-user-hosted-voice-mail-policy"></a><span data-ttu-id="8910e-109">Назначение политики маршрутизации размещенной голосовой почты для отдельных пользователей</span><span class="sxs-lookup"><span data-stu-id="8910e-109">To assign a per-user hosted voice mail policy</span></span>

1.  <span data-ttu-id="8910e-110">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="8910e-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="8910e-p102">Запустите командлет Grant-CsHostedVoicemailPolicy, чтобы назначить политику маршрутизации размещенной голосовой почты отдельным пользователям, группам и контактным объектам. Например, выполните команду</span><span class="sxs-lookup"><span data-stu-id="8910e-p102">Run the Grant-CsHostedVoicemailPolicy cmdlet to assign the per-user hosted voice mail policy to individual users, groups, and contact objects. For example, run:</span></span>
    
        Grant-CsHostedVoicemailPolicy -Identity "Ken Myer" -PolicyName ExRedmond
    
    <span data-ttu-id="8910e-113">В этом примере политика маршрутизации размещенной голосовой почты ExRedmond назначается пользователю Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="8910e-113">This example assigned the ExRedmond hosted voice mail policy to user Ken Myer.</span></span>
    
    <span data-ttu-id="8910e-p103">Параметр **Identity** указывает изменяемую учетную запись. Значение параметра Identity (Удостоверение) можно указать в одном из следующих форматов:</span><span class="sxs-lookup"><span data-stu-id="8910e-p103">**Identity** specifies the user account to be modified. The Identity value can be specified using any of the following formats:</span></span>
    
      - <span data-ttu-id="8910e-116">SIP-адрес пользователя;</span><span class="sxs-lookup"><span data-stu-id="8910e-116">The user's SIP address</span></span>
    
      - <span data-ttu-id="8910e-117">имя участника-пользователя Active Directory пользователя;</span><span class="sxs-lookup"><span data-stu-id="8910e-117">The user's Active Directory User-Principal-Name</span></span>
    
      - <span data-ttu-id="8910e-118">Имя для входа в домен пользователя \\ (например, Contoso \\ kenmyer).</span><span class="sxs-lookup"><span data-stu-id="8910e-118">The user's domain\\logon name (for example, contoso\\kenmyer)</span></span>
    
      - <span data-ttu-id="8910e-119">отображаемое имя доменных служб Active Directory пользователя (например, Ken Myer).</span><span class="sxs-lookup"><span data-stu-id="8910e-119">The user's Active Directory Domain Services Display-Name (for example, Ken Myer).</span></span> <span data-ttu-id="8910e-120">При использовании Display-Name в качестве значения идентификатора можно использовать подстановочный знак "звездочка" ( \* ).</span><span class="sxs-lookup"><span data-stu-id="8910e-120">If using the Display-Name as the Identity value, you can use the asterisk (\*) wildcard character.</span></span> <span data-ttu-id="8910e-121">Например, идентификатор " \* Smith" возвращает всех пользователей, у которых есть Display-Name, заканчивающийся строковым значением "Smith".</span><span class="sxs-lookup"><span data-stu-id="8910e-121">For example, the Identity "\* Smith" returns all the users who have a Display-Name that ends with the string value "Smith".</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="8910e-122">Имя-учетной-записи-SAM Active Directory пользователя нельзя использовать в качестве значения параметра Identity, так как это имя может быть неуникальным в лесу.</span><span class="sxs-lookup"><span data-stu-id="8910e-122">The user’s Active Directory SAM-Account-Name cannot be used as the Identity value because the SAM-Account-Name is not necessarily unique in the forest.</span></span>


