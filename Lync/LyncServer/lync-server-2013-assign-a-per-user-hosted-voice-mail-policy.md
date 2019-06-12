---
title: 'Lync Server 2013: назначение политики для размещенной голосовой почты для отдельных пользователей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user hosted voice mail policy
ms:assetid: d44c71a0-4407-4ab4-b7e0-d671dde3425f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398919(v=OCS.15)
ms:contentKeyID: 48185456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2202e1b4c03eb25d12e46c3a533313a54bc76c4f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849796"
---
# <a name="assign-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="0524f-102">Назначение политики размещенной голосовой почты для отдельных пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0524f-102">Assign a per-user hosted voice mail policy in Lync Server 2013</span></span>

 


<span data-ttu-id="0524f-103">Развертывание одной или нескольких политик голосовой почты, размещенных отдельно для пользователей, не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="0524f-103">Deploying one or more per-user hosted voice mail policies is optional.</span></span> <span data-ttu-id="0524f-104">Если вы выполняете развертывание политик для пользователей, необходимо явным образом назначать их пользователям, группам и контактным объектам.</span><span class="sxs-lookup"><span data-stu-id="0524f-104">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact objects.</span></span>

<span data-ttu-id="0524f-105">Сведения о назначении и удалении назначений политик голосовой почты, размещенных на уровне пользователя, можно найти в документации по оболочке Lync Server Management Shell для следующих командлетов:</span><span class="sxs-lookup"><span data-stu-id="0524f-105">For details about assigning or removing the assignment of per-user hosted voice mail policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="0524f-106">Grant-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="0524f-106">Grant-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="0524f-107">Remove-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="0524f-107">Remove-CsHostedVoicemailPolicy</span></span>

## <a name="to-assign-a-per-user-hosted-voice-mail-policy"></a><span data-ttu-id="0524f-108">Назначение политики размещенной голосовой почты для пользователя</span><span class="sxs-lookup"><span data-stu-id="0524f-108">To assign a per-user hosted voice mail policy</span></span>

1.  <span data-ttu-id="0524f-109">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="0524f-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="0524f-110">Запустите командлет Grant-Кшостедвоицемаилполици, чтобы назначить политику размещенной голосовой почты отдельным пользователям, группам и контактным объектам.</span><span class="sxs-lookup"><span data-stu-id="0524f-110">Run the Grant-CsHostedVoicemailPolicy cmdlet to assign the per-user hosted voice mail policy to individual users, groups, and contact objects.</span></span> <span data-ttu-id="0524f-111">Например, выполните командлет:</span><span class="sxs-lookup"><span data-stu-id="0524f-111">For example, run:</span></span>
    
        Grant-CsHostedVoicemailPolicy -Identity "Ken Myer" -PolicyName ExRedmond
    
    <span data-ttu-id="0524f-112">В этом примере политика размещенной голосовой почты Ексредмонд для пользователя Кен мер.</span><span class="sxs-lookup"><span data-stu-id="0524f-112">This example assigned the ExRedmond hosted voice mail policy to user Ken Myer.</span></span>
    
    <span data-ttu-id="0524f-113">**Identity** указывает учетную запись пользователя, который нужно изменить.</span><span class="sxs-lookup"><span data-stu-id="0524f-113">**Identity** specifies the user account to be modified.</span></span> <span data-ttu-id="0524f-114">Значение идентификатора можно задать в одном из следующих форматов:</span><span class="sxs-lookup"><span data-stu-id="0524f-114">The Identity value can be specified using any of the following formats:</span></span>
    
      - <span data-ttu-id="0524f-115">Адрес SIP пользователя</span><span class="sxs-lookup"><span data-stu-id="0524f-115">The user's SIP address</span></span>
    
      - <span data-ttu-id="0524f-116">Имя субъекта-пользователя в службе каталогов Active Directory</span><span class="sxs-lookup"><span data-stu-id="0524f-116">The user's Active Directory User-Principal-Name</span></span>
    
      - <span data-ttu-id="0524f-117">Доменное\\имя пользователя (например, Contoso\\кенмер).</span><span class="sxs-lookup"><span data-stu-id="0524f-117">The user's domain\\logon name (for example, contoso\\kenmyer)</span></span>
    
      - <span data-ttu-id="0524f-118">Отображаемое имя доменных служб Active Directory (например, Кен мер).</span><span class="sxs-lookup"><span data-stu-id="0524f-118">The user's Active Directory Domain Services Display-Name (for example, Ken Myer).</span></span> <span data-ttu-id="0524f-119">Если в качестве значения удостоверения используется имя для отображения, можно использовать подстановочный знак "звездочка" (\*).</span><span class="sxs-lookup"><span data-stu-id="0524f-119">If using the Display-Name as the Identity value, you can use the asterisk (\*) wildcard character.</span></span> <span data-ttu-id="0524f-120">Например, удостоверение "\* Иванов" возвращает всех пользователей, у которых есть имя отображения, которое оканчивается строковым значением Смит.</span><span class="sxs-lookup"><span data-stu-id="0524f-120">For example, the Identity "\* Smith" returns all the users who have a Display-Name that ends with the string value "Smith".</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="0524f-121">Имя учетной записи SAM в Active Directory не может использоваться в качестве значения удостоверения, так как имя SAM-Account-Name не обязательно должно быть уникальным в лесу.</span><span class="sxs-lookup"><span data-stu-id="0524f-121">The user’s Active Directory SAM-Account-Name cannot be used as the Identity value because the SAM-Account-Name is not necessarily unique in the forest.</span></span>


