---
title: 'Lync Server 2013: планирование для частных телефонных линий'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for private telephone lines
ms:assetid: 9cc4f9e1-7b7a-4699-bd05-f16669ef2d21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412728(v=OCS.15)
ms:contentKeyID: 48184909
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8051fc18fd42c2c9773d4e0b8904f2923687fe2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184142"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-private-telephone-lines-with-lync-server-2013"></a><span data-ttu-id="77882-102">Планирование частных телефонных линий с помощью Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="77882-102">Planning for private telephone lines with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77882-103">_**Последнее изменение темы:** 2013-02-11_</span><span class="sxs-lookup"><span data-stu-id="77882-103">_**Topic Last Modified:** 2013-02-11_</span></span>

<span data-ttu-id="77882-104">Lync Server 2013 предоставляет возможность предоставить пользователям вторую и частную телефонную линию в дополнение к основной телефонной линии.</span><span class="sxs-lookup"><span data-stu-id="77882-104">Lync Server 2013 introduces the ability to give users a second, private telephone line in addition to their primary telephone line.</span></span> <span data-ttu-id="77882-105">Частные телефонные линии обычно выделяются руководителям и тем, кому нужен номер телефона, не внесенный в список, по которому с ними можно связаться напрямую.</span><span class="sxs-lookup"><span data-stu-id="77882-105">Private telephone lines are often assigned to executives and others who want an unlisted telephone number at which they can be reached directly.</span></span>

<span data-ttu-id="77882-106">Частные телефонные линии можно настроить только с помощью командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="77882-106">Private telephone lines can only be configured with the Lync Server Management Shell.</span></span> <span data-ttu-id="77882-107">Вы не можете настраивать частные телефонные линии с помощью панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="77882-107">You cannot configure private telephone lines with the Lync Server Control Panel.</span></span> <span data-ttu-id="77882-108">Частные телефонные линии следует настраивать только в развертываниях Lync Server, а не в смешанных развертываниях.</span><span class="sxs-lookup"><span data-stu-id="77882-108">Private telephone lines should be configured only in deployments of Lync Server and not in mixed deployments.</span></span>

<div>

## <a name="characteristics-of-private-telephone-lines"></a><span data-ttu-id="77882-109">Характеристики частных телефонных линий</span><span class="sxs-lookup"><span data-stu-id="77882-109">Characteristics of Private Telephone Lines</span></span>

<span data-ttu-id="77882-110">Хотя концепция дополнительной, частной телефонной линии в своей основе проста, важно понимать характеристики частных линий, а также в чем они подобны основным телефонным линиям пользователей, и в чем отличаются.</span><span class="sxs-lookup"><span data-stu-id="77882-110">Although the concept of a second, private telephone line is fundamentally simple, it is important to understand the characteristics of private lines and the ways in which they are similar to and different from users’ primary telephone lines.</span></span>

<div>

## <a name="general-characteristics-of-private-telephone-lines"></a><span data-ttu-id="77882-111">Основные характеристики частных телефонных линий</span><span class="sxs-lookup"><span data-stu-id="77882-111">General Characteristics of Private Telephone Lines</span></span>

  - <span data-ttu-id="77882-112">Пользователь может иметь только одну частную телефонную линию.</span><span class="sxs-lookup"><span data-stu-id="77882-112">A user can have only one private telephone line.</span></span>

  - <span data-ttu-id="77882-113">Пользователь с частной телефонной линией может иметь только один ящик голосовой почты и получает уведомления о пропущенных звонках только на один адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="77882-113">A user with a private telephone line has only one voice mailbox and receives missed call notifications at a single email address.</span></span>

  - <span data-ttu-id="77882-114">Пользователь с частной телефонной линией не имеет дополнительного SIP-адреса, а дополнительная частная телефонная линия не дает пользователю второе присутствие в сети (такое, как второе удостоверение в системе обмена мгновенными сообщениями).</span><span class="sxs-lookup"><span data-stu-id="77882-114">A user with a private telephone line does not have a second SIP address, and a second, private telephone line does not give a user a second presence on the network (such as a second instant messaging identity).</span></span>

  - <span data-ttu-id="77882-115">Частные телефонные линии доступны только для локальных развертываний.</span><span class="sxs-lookup"><span data-stu-id="77882-115">Private telephone lines are available for on-premises deployments only.</span></span> <span data-ttu-id="77882-116">Они недоступны в размещенных развертываниях Lync Server.</span><span class="sxs-lookup"><span data-stu-id="77882-116">They are not available with hosted deployments of Lync Server.</span></span>

</div>

<div>

## <a name="how-private-telephone-lines-differ-from-primary-telephone-lines"></a><span data-ttu-id="77882-117">Отличия частных телефонных линий от основных телефонных линий</span><span class="sxs-lookup"><span data-stu-id="77882-117">How Private Telephone Lines Differ from Primary Telephone Lines</span></span>

  - <span data-ttu-id="77882-118">Телефонные номера частных телефонных линий не отображаются в телефонных справочниках и в списках контактов, полученных из доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="77882-118">The telephone numbers for private telephone lines do not appear in the telephone directories or Contacts lists that are derived from Active Directory Domain Services.</span></span>

  - <span data-ttu-id="77882-119">В частной телефонной линии недоступны следующие функции: Переадресация звонков, групповой звонок, делегирование, групповой звонок, групповой ответ на звонки и приложение группы ответа.</span><span class="sxs-lookup"><span data-stu-id="77882-119">None of the following features are available with a private telephone line: call forwarding, team call, delegation, team ring, Group Call Pickup, and Response Group application.</span></span>

  - <span data-ttu-id="77882-120">Вызовы, поступающие на частную телефонную линию, имеют специальный сигнал, и системное уведомление о вызове сообщает пользователю, что на его частную линию поступил входящий вызов.</span><span class="sxs-lookup"><span data-stu-id="77882-120">Calls to a private telephone line have a special ring, and the system notification for the call tells the user that the incoming call is on his or her private line.</span></span>

  - <span data-ttu-id="77882-p104">Вызовы, поступающие на частную телефонную линию, всегда звонят. Они не следуют правилам "Не беспокоить".</span><span class="sxs-lookup"><span data-stu-id="77882-p104">Calls to the private telephone line always ring through. They do not follow "do not disturb" rules.</span></span>

  - <span data-ttu-id="77882-p105">Частные телефонные линии предназначены только для приема вызовов и не могут использоваться для выполнения исходящих вызовов. Когда пользователь с частной телефонной линией выполняет вызов, то этот вызов исходит из основной телефонной линии пользователя и не скрывает его имя и телефонный номер в основной линии от вызываемого лица.</span><span class="sxs-lookup"><span data-stu-id="77882-p105">Private telephone lines are inbound only and cannot be used to make outgoing calls. When a user with a private telephone line makes a call, the call originates from the user’s primary telephone line and does not hide the user’s name or the user’s primary telephone number from the person called.</span></span>

</div>

<div>

## <a name="how-private-telephone-lines-are-similar-to-primary-telephone-lines"></a><span data-ttu-id="77882-125">Сходство частных телефонных линий и основных телефонных линий</span><span class="sxs-lookup"><span data-stu-id="77882-125">How Private Telephone Lines Are Similar to Primary Telephone Lines</span></span>

  - <span data-ttu-id="77882-126">Неотвеченные вызовы, поступившие на частную телефонную линию, направляются в ту же папку "Входящие" голосовой почты, что и вызовы по основной телефонной линии (если голосовая почта включена).</span><span class="sxs-lookup"><span data-stu-id="77882-126">Unanswered calls to a private telephone line are routed to the same voice mail inbox as for the primary telephone line (if voice mail is enabled).</span></span>

  - <span data-ttu-id="77882-127">Парковка вызовов и захват вызова работают в частной телефонной линии точно так же, как в основной телефонной линии.</span><span class="sxs-lookup"><span data-stu-id="77882-127">Call park and call pickup work with private telephone lines in exactly the same manner as they do with the user’s primary telephone line.</span></span>

  - <span data-ttu-id="77882-128">Если одновременные звонки разрешены в основной телефонной линии пользователя, то они также разрешены и в его частной телефонной линии.</span><span class="sxs-lookup"><span data-stu-id="77882-128">When simultaneous ringing is enabled on a user’s primary telephone line, it is also enabled on the private telephone line.</span></span>

  - <span data-ttu-id="77882-129">Телефонный номер в частной телефонной линии записывается в регистрации вызовов точно так же, как телефонный номер в основной телефонной линии, но с указанием, что это частный телефонный номер.</span><span class="sxs-lookup"><span data-stu-id="77882-129">The telephone number for a private telephone line is recorded in the call detail record in the same manner as the telephone number for a user’s primary telephone line, but with an indication that it is a private telephone number.</span></span>

  - <span data-ttu-id="77882-130">После ответа пользователя на вызов по частной телефонной линии этот вызов обрабатывается точно так же, как вызов по основной телефонной линии.</span><span class="sxs-lookup"><span data-stu-id="77882-130">After a user answers a call on a private telephone line, the call is treated the same as a call on the user’s primary telephone line.</span></span> <span data-ttu-id="77882-131">Например, если пользователь, который получает вызов на частную телефонную линию, перенаправляет вызов или приглашает кого-либо на конференцию, имя пользователя отображается в Lync 2013, а телефонный номер основной телефонной линии пользователя отображается в поле идентификатор звонящего.</span><span class="sxs-lookup"><span data-stu-id="77882-131">For example, if a user who receives a call on a private telephone line forwards the call or invites others to a conference call, the user’s name appears in Lync 2013, and the telephone number for the user’s primary telephone line appears in caller ID.</span></span>

  - <span data-ttu-id="77882-132">Пользователь может отклонить поступивший по частной телефонной линии вызов (еще до ответа перенаправить его в другое место назначения, например на мобильный телефон или на домашний телефон) точно так же, как вызов, поступивший по основной телефонной линии.</span><span class="sxs-lookup"><span data-stu-id="77882-132">A user can deflect a call (redirect the call to another destination, such as a mobile phone or home phone, before answering) from the private telephone line in the same manner as with a primary telephone line.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="77882-133">Когда вызов по частной телефонной линии перенаправляется на другой телефонный номер, то телефонный номер в частной телефонной линии становится доступным для этого другого телефонного номера и может отображаться в журналах для этого номера.</span><span class="sxs-lookup"><span data-stu-id="77882-133">When a call to a private line is routed to an alternate telephone number, the telephone number for the private telephone line is made available to the alternate telephone number and can be displayed in the logs for that number.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="77882-134">Вызовы из конференции, поступившие в частную телефонную линию, не будут иметь указатель <EM>частная линия</EM> в системном уведомлении о входящих вызовах.</span><span class="sxs-lookup"><span data-stu-id="77882-134">Calls from a conference to the private telephone line will not have a <EM>private-line</EM> indication in the incoming system notification.</span></span>

    
    </div>

</div>

</div>

<div>

## <a name="administering-private-telephone-lines"></a><span data-ttu-id="77882-135">Администрирование частных телефонных линий</span><span class="sxs-lookup"><span data-stu-id="77882-135">Administering Private Telephone Lines</span></span>

<span data-ttu-id="77882-p107">Помимо технических аспектов создания частных телефонных линий и управления ими необходимо будет установить для них административные процедуры. Сюда входит установка политик для определения лиц, имеющих в организации право на частную телефонную линию, создание и обслуживание списков таких лиц и их телефонных линий, возможно создание закрытого телефонного справочника для руководства, организация обучения пользователей и связанные задачи.</span><span class="sxs-lookup"><span data-stu-id="77882-p107">In addition to the technical aspects of creating and managing private telephone lines, you will need to establish administrative procedures for them. This includes determining policies for who in the organization is eligible for a private line, creating and maintaining lists of people and their telephone lines, possibly creating a private telephone directory for executives, arranging for user training, and related tasks.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="77882-p108">Частная телефонная линия хранится в Active Directory как атрибут msRTCSIP-PrivateLine объекта-пользователя. По умолчанию любой член группы проверенных пользователей имеет доступ на чтение этого атрибута.</span><span class="sxs-lookup"><span data-stu-id="77882-p108">The private telephone line is stored in Active Directory as an msRTCSIP-PrivateLine attribute on the user object. By default any member of the Authenticated Users group has read access to this attribute.</span></span>



</div>

<div>

## <a name="assigning-telephone-numbers"></a><span data-ttu-id="77882-140">Назначение телефонных номеров</span><span class="sxs-lookup"><span data-stu-id="77882-140">Assigning Telephone Numbers</span></span>

<span data-ttu-id="77882-141">Учетные записи для новых пользователей, которым требуются частные телефонные линии, создаются так же, как учетные записи без частных телефонных линий, с помощью панели управления Lync Server или консоли управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="77882-141">Accounts for new users who need private telephone lines are created in the same manner as accounts without private telephone lines, using Lync Server Control Panel or Lync Server Management Shell.</span></span>

<span data-ttu-id="77882-142">Используйте командлет **Set – CsUser** в командной консоли Lync Server, чтобы назначить телефонный номер частной телефонной линии для пользователя, например, **Set — CsUser — Identity "SIP:joe@contoso.com" – PrivateLine "Tel: + 14255551212"**.</span><span class="sxs-lookup"><span data-stu-id="77882-142">Use the **Set-CsUser** cmdlet in the Lync Server Management Shell to assign a telephone number to a private telephone line for a user, for example, **Set-CsUser -Identity "sip:joe@contoso.com" -PrivateLine "Tel:+14255551212"**.</span></span>

<span data-ttu-id="77882-143">Номера телефонов частных телефонных линий могут иметь длину от 3 до 15 чисел и должны предшествовать префиксу "TEL:".</span><span class="sxs-lookup"><span data-stu-id="77882-143">Telephone numbers for private telephone lines can be between 3 and 15 numbers in length and must be preceded with the "TEL:" prefix.</span></span> <span data-ttu-id="77882-144">Они могут иметь любой код города и любой код страны или региона, если ваша организация имеет прямой входной набор для этого кода города и кода страны или региона.</span><span class="sxs-lookup"><span data-stu-id="77882-144">They can have any area code and any country/region code as long as your organization has direct inward dialing for that area code and country/region code.</span></span>

<span data-ttu-id="77882-145">Сведения о командлетах и командной консоли Lync Server представлены в документации по консоли [управления Lync server 2013](lync-server-2013-lync-server-management-shell.md) .</span><span class="sxs-lookup"><span data-stu-id="77882-145">For details about cmdlets and Lync Server Management Shell, see the [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation.</span></span>

</div>

<div>

## <a name="private-telephone-lines-in-mixed-deployments"></a><span data-ttu-id="77882-146">Частные телефонные линии в смешанных развертываниях</span><span class="sxs-lookup"><span data-stu-id="77882-146">Private Telephone Lines in Mixed Deployments</span></span>

<span data-ttu-id="77882-147">Частные телефонные линии должны быть настроены только для развертываний Lync Server.</span><span class="sxs-lookup"><span data-stu-id="77882-147">Private telephone lines should be configured only for deployments of Lync Server.</span></span> <span data-ttu-id="77882-148">В развертывании, в котором имеются серверы Lync Server и Office Communications Server 2007 или Office Communications Server 2007 R2, когда пользователь более ранней версии пытается позвонить на частную телефонную линию, маршрутизация вызова завершается с ошибкой, так как сервер не может выполнение обратного просмотра номера в частной телефонной линии.</span><span class="sxs-lookup"><span data-stu-id="77882-148">In a deployment in which there are both Lync Server and Office Communications Server 2007 or Office Communications Server 2007 R2 servers, when a user on earlier version attempts to call a private telephone line, routing of the call fails because the server cannot perform a reverse number lookup on a private telephone line.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

