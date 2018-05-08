---
title: Планирование частных телефонных линий в Skype для бизнеса 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9cc4f9e1-7b7a-4699-bd05-f16669ef2d21
description: Планирование частных (дополнительный) телефонных линий в Скайп Business Server корпоративной голосовой связи.
ms.openlocfilehash: 67be5d65be7d97399309934aff52eadf1869cc50
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="plan-for-private-telephone-lines-with-skype-for-business-2015"></a><span data-ttu-id="fc445-103">Планирование частных телефонных линий в Skype для бизнеса 2015</span><span class="sxs-lookup"><span data-stu-id="fc445-103">Plan for private telephone lines with Skype for Business 2015</span></span>
 
<span data-ttu-id="fc445-104">Планирование частных (дополнительный) телефонных линий в Скайп Business Server корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="fc445-104">Planning for private (secondary) telephone lines in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="fc445-105">Скайп для Business Server позволяет предоставить пользователям второй, частной телефонной линии, в дополнение к их основной телефонной линии.</span><span class="sxs-lookup"><span data-stu-id="fc445-105">Skype for Business Server enables you to give users a second, private telephone line in addition to their primary telephone line.</span></span> <span data-ttu-id="fc445-106">Такие частные телефонные линии часто назначаются руководителям и тем, кто хочет получить номер, не внесенный в телефонную книгу, на который им можно звонить напрямую.</span><span class="sxs-lookup"><span data-stu-id="fc445-106">Private telephone lines are often assigned to executives and others who want an unlisted telephone number at which they can be reached directly.</span></span>
  
<span data-ttu-id="fc445-107">Частных телефонных линий можно настроить только с Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="fc445-107">Private telephone lines can only be configured with the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="fc445-108">Нельзя настроить частных телефонных линий с Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="fc445-108">You cannot configure private telephone lines with the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="fc445-109">Частных телефонных линий, необходимо настроить только в развертываниях Скайп для Business Server, а не в смешанных развертываниях.</span><span class="sxs-lookup"><span data-stu-id="fc445-109">Private telephone lines should be configured only in deployments of Skype for Business Server and not in mixed deployments.</span></span>
  
## <a name="characteristics-of-private-telephone-lines"></a><span data-ttu-id="fc445-110">Характеристики частных телефонных линий</span><span class="sxs-lookup"><span data-stu-id="fc445-110">Characteristics of Private Telephone Lines</span></span>

<span data-ttu-id="fc445-111">Несмотря на то, что концепция второй, частной телефонной линии существенно простой, это важно понимать характеристики частных линий и способы, в котором они аналогичны и отличаются от основных телефонных линий пользователей.</span><span class="sxs-lookup"><span data-stu-id="fc445-111">Although the concept of a second, private telephone line is fundamentally simple, it is important to understand the characteristics of private lines and the ways in which they are similar to and different from users' primary telephone lines.</span></span>
  
### <a name="general-characteristics-of-private-telephone-lines"></a><span data-ttu-id="fc445-112">Основные характеристики частных телефонных линий</span><span class="sxs-lookup"><span data-stu-id="fc445-112">General Characteristics of Private Telephone Lines</span></span>

- <span data-ttu-id="fc445-113">Пользователь может иметь только одну частную телефонную линию.</span><span class="sxs-lookup"><span data-stu-id="fc445-113">A user can have only one private telephone line.</span></span>
    
- <span data-ttu-id="fc445-114">Пользователь с частной телефонной линией может иметь только один ящик голосовой почты и получает уведомления о пропущенных звонках только на один адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="fc445-114">A user with a private telephone line has only one voice mailbox and receives missed call notifications at a single email address.</span></span>
    
- <span data-ttu-id="fc445-115">Пользователь с частной телефонной линией не имеет дополнительного SIP-адреса, а дополнительная частная телефонная линия не дает пользователю второе присутствие в сети (такое, как второе удостоверение в системе обмена мгновенными сообщениями).</span><span class="sxs-lookup"><span data-stu-id="fc445-115">A user with a private telephone line does not have a second SIP address, and a second, private telephone line does not give a user a second presence on the network (such as a second instant messaging identity).</span></span> 
    
- <span data-ttu-id="fc445-116">Частные телефонные линии доступны только для локальных развертываний.</span><span class="sxs-lookup"><span data-stu-id="fc445-116">Private telephone lines are available for on-premises deployments only.</span></span> <span data-ttu-id="fc445-117">Они не доступны в размещенных развертываний Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="fc445-117">They are not available with hosted deployments of Skype for Business Server.</span></span>
    
### <a name="how-private-telephone-lines-differ-from-primary-telephone-lines"></a><span data-ttu-id="fc445-118">Отличия частных телефонных линий от основных телефонных линий</span><span class="sxs-lookup"><span data-stu-id="fc445-118">How Private Telephone Lines Differ from Primary Telephone Lines</span></span>

- <span data-ttu-id="fc445-119">Телефонные номера частных телефонных линий не отображаются в телефонных справочниках и в списках контактов, полученных из доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fc445-119">The telephone numbers for private telephone lines do not appear in the telephone directories or Contacts lists that are derived from Active Directory Domain Services.</span></span>
    
- <span data-ttu-id="fc445-120">В частных телефонных линиях недоступны следующие функции: переадресация звонков, групповой звонок, делегирование, групповой сигнал звонка, групповой ответ на звонки, а также приложение "Группа ответа".</span><span class="sxs-lookup"><span data-stu-id="fc445-120">None of the following features are available with a private telephone line: call forwarding, team call, delegation, team ring, Group Call Pickup, and Response Group application.</span></span>
    
- <span data-ttu-id="fc445-121">Вызовы, поступающие на частную телефонную линию, имеют специальный сигнал, и системное уведомление о вызове сообщает пользователю, что на его частную линию поступил входящий вызов.</span><span class="sxs-lookup"><span data-stu-id="fc445-121">Calls to a private telephone line have a special ring, and the system notification for the call tells the user that the incoming call is on his or her private line.</span></span>
    
- <span data-ttu-id="fc445-p104">Вызовы, поступающие на частную телефонную линию, всегда звонят. Они не следуют правилам "Не беспокоить".</span><span class="sxs-lookup"><span data-stu-id="fc445-p104">Calls to the private telephone line always ring through. They do not follow "do not disturb" rules.</span></span>
    
- <span data-ttu-id="fc445-124">Частные телефонные линии предназначены только для приема вызовов и не могут использоваться для выполнения исходящих вызовов.</span><span class="sxs-lookup"><span data-stu-id="fc445-124">Private telephone lines are inbound only and cannot be used to make outgoing calls.</span></span> <span data-ttu-id="fc445-125">Когда вызывает пользователь с частной телефонной линии, вызова исходит из основной телефонной линии пользователя и не скрывает имя пользователя или основной телефонный номер пользователя с именем пользователя.</span><span class="sxs-lookup"><span data-stu-id="fc445-125">When a user with a private telephone line makes a call, the call originates from the user's primary telephone line and does not hide the user's name or the user's primary telephone number from the person called.</span></span>
    
### <a name="how-private-telephone-lines-are-similar-to-primary-telephone-lines"></a><span data-ttu-id="fc445-126">Сходство частных телефонных линий и основных телефонных линий</span><span class="sxs-lookup"><span data-stu-id="fc445-126">How Private Telephone Lines Are Similar to Primary Telephone Lines</span></span>

- <span data-ttu-id="fc445-127">Неотвеченные вызовы, поступившие на частную телефонную линию, направляются в ту же папку "Входящие" голосовой почты, что и вызовы по основной телефонной линии (если голосовая почта включена).</span><span class="sxs-lookup"><span data-stu-id="fc445-127">Unanswered calls to a private telephone line are routed to the same voice mail inbox as for the primary telephone line (if voice mail is enabled).</span></span>
    
- <span data-ttu-id="fc445-128">Парковка вызовов и захват вызова работают частной телефонной линии точно так же, как и с основной телефонной линии пользователя.</span><span class="sxs-lookup"><span data-stu-id="fc445-128">Call park and call pickup work with private telephone lines in exactly the same manner as they do with the user's primary telephone line.</span></span>
    
- <span data-ttu-id="fc445-129">Одновременные звонки разрешены в основной телефонной линии пользователя, также включены в частной телефонной линии.</span><span class="sxs-lookup"><span data-stu-id="fc445-129">When simultaneous ringing is enabled on a user's primary telephone line, it is also enabled on the private telephone line.</span></span>
    
- <span data-ttu-id="fc445-130">Телефонный номер частной телефонной линии записывается в записи сведений о вызове в так же, как номер телефона для пользователя основной телефонной линии, но это свидетельствует о том, что это частный телефонный номер.</span><span class="sxs-lookup"><span data-stu-id="fc445-130">The telephone number for a private telephone line is recorded in the call detail record in the same manner as the telephone number for a user's primary telephone line, but with an indication that it is a private telephone number.</span></span>
    
- <span data-ttu-id="fc445-131">После пользователем ответов, которые звонок на частную телефонную линию, вызов обрабатывается так же, как вызов на основной телефонной линии пользователя.</span><span class="sxs-lookup"><span data-stu-id="fc445-131">After a user answers a call on a private telephone line, the call is treated the same as a call on the user's primary telephone line.</span></span> <span data-ttu-id="fc445-132">Например, если пользователь, который получает вызов на частную телефонную линию, перенаправляет вызов или приглашает другим пользователям для конференц-связи, имя пользователя отображается в Скайп для бизнеса и номер телефона для основной телефонной линии пользователя отображается в вызывающего абонента по идентификатору.</span><span class="sxs-lookup"><span data-stu-id="fc445-132">For example, if a user who receives a call on a private telephone line forwards the call or invites others to a conference call, the user's name appears in Skype for Business, and the telephone number for the user's primary telephone line appears in caller ID.</span></span>
    
- <span data-ttu-id="fc445-133">Пользователь может отклонить поступивший по частной телефонной линии вызов (еще до ответа перенаправить его в другое место назначения, например на мобильный телефон или на домашний телефон) точно так же, как вызов, поступивший по основной телефонной линии.</span><span class="sxs-lookup"><span data-stu-id="fc445-133">A user can deflect a call (redirect the call to another destination, such as a mobile phone or home phone, before answering) from the private telephone line in the same manner as with a primary telephone line.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="fc445-134">Когда вызов по частной телефонной линии перенаправляется на другой телефонный номер, то телефонный номер в частной телефонной линии становится доступным для этого другого телефонного номера и может отображаться в журналах для этого номера.</span><span class="sxs-lookup"><span data-stu-id="fc445-134">When a call to a private line is routed to an alternate telephone number, the telephone number for the private telephone line is made available to the alternate telephone number and can be displayed in the logs for that number.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="fc445-135">Вызовы из конференции частную телефонную линию не будут иметь указатель *частная линия* входящих уведомление о системе.</span><span class="sxs-lookup"><span data-stu-id="fc445-135">Calls from a conference to the private telephone line will not have a  *private-line*  indication in the incoming system notification.</span></span>
  
## <a name="administering-private-telephone-lines"></a><span data-ttu-id="fc445-136">Администрирование частных телефонных линий</span><span class="sxs-lookup"><span data-stu-id="fc445-136">Administering Private Telephone Lines</span></span>

<span data-ttu-id="fc445-p107">Помимо технических аспектов создания частных телефонных линий и управления ими необходимо будет установить для них административные процедуры. Сюда входит установка политик для определения лиц, имеющих в организации право на частную телефонную линию, создание и обслуживание списков таких лиц и их телефонных линий, возможно создание закрытого телефонного справочника для руководства, организация обучения пользователей и связанные задачи.</span><span class="sxs-lookup"><span data-stu-id="fc445-p107">In addition to the technical aspects of creating and managing private telephone lines, you will need to establish administrative procedures for them. This includes determining policies for who in the organization is eligible for a private line, creating and maintaining lists of people and their telephone lines, possibly creating a private telephone directory for executives, arranging for user training, and related tasks.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fc445-p108">Частная телефонная линия хранится в Active Directory как атрибут msRTCSIP-PrivateLine объекта-пользователя. По умолчанию любой член группы проверенных пользователей имеет доступ на чтение этого атрибута.</span><span class="sxs-lookup"><span data-stu-id="fc445-p108">The private telephone line is stored in Active Directory as an msRTCSIP-PrivateLine attribute on the user object. By default any member of the Authenticated Users group has read access to this attribute.</span></span> 
  
### <a name="assigning-telephone-numbers"></a><span data-ttu-id="fc445-141">Назначение телефонных номеров</span><span class="sxs-lookup"><span data-stu-id="fc445-141">Assigning Telephone Numbers</span></span>

 <span data-ttu-id="fc445-142">Учетные записи для новых пользователей, которым требуются частные телефонные линии, создаются в так же, как учетные записи без частных телефонных линий, с помощью Скайп для панели управления Business Server или Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="fc445-142">Accounts for new users who need private telephone lines are created in the same manner as accounts without private telephone lines, using Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="fc445-143">Командлет **Set-CsUser** в Скайп для консоли Business Server для назначить телефонный номер частной телефонной линии для пользователя, например, **Set-CsUser-Identity «sip:joe@contoso.com» - PrivateLine «Tel: + 14255551212 "**.</span><span class="sxs-lookup"><span data-stu-id="fc445-143">Use the **Set-CsUser** cmdlet in the Skype for Business Server Management Shell to assign a telephone number to a private telephone line for a user, for example, **Set-CsUser -Identity "sip:joe@contoso.com" -PrivateLine "Tel:+14255551212"**.</span></span>
  
<span data-ttu-id="fc445-144">Телефонные номера частных телефонных линий может быть между 3 и 15 числа в длину и должно начинаться с «TEL:» префикс.</span><span class="sxs-lookup"><span data-stu-id="fc445-144">Telephone numbers for private telephone lines can be between 3 and 15 numbers in length and must be preceded with the "TEL:" prefix.</span></span> <span data-ttu-id="fc445-145">Они могут иметь любой код города и любой код страны или региона, если ваша организация имеет прямой входной набор для этого кода города и кода страны или региона.</span><span class="sxs-lookup"><span data-stu-id="fc445-145">They can have any area code and any country/region code as long as your organization has direct inward dialing for that area code and country/region code.</span></span> 
  
<span data-ttu-id="fc445-146">Для получения дополнительных сведений о командлетов и Скайп для консоли Business Server см Скайп для документации по консоли управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="fc445-146">For details about cmdlets and Skype for Business Server Management Shell, see the Skype for Business Server Management Shell documentation.</span></span>
  
### <a name="private-telephone-lines-in-mixed-deployments"></a><span data-ttu-id="fc445-147">Частные телефонные линии в смешанных развертываниях</span><span class="sxs-lookup"><span data-stu-id="fc445-147">Private Telephone Lines in Mixed Deployments</span></span>

<span data-ttu-id="fc445-148">Частных телефонных линий, необходимо настроить только для развертываний Скайп Business Server и Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fc445-148">Private telephone lines should be configured only for deployments of Skype for Business Server or Lync Server 2013.</span></span> <span data-ttu-id="fc445-149">В развертывании, в котором существуют серверов с более ранних версий Lync Server, когда пользователь на более ранней версии, пытается вызвать частную телефонную линию маршрутизации вызовов, происходит сбой, так как сервер не может выполнить обратный поиск номера на частную телефонную линию.</span><span class="sxs-lookup"><span data-stu-id="fc445-149">In a deployment in which there are servers running earlier versions of Lync Server, when a user on earlier version attempts to call a private telephone line, routing of the call fails because the server cannot perform a reverse number lookup on a private telephone line.</span></span>
  

