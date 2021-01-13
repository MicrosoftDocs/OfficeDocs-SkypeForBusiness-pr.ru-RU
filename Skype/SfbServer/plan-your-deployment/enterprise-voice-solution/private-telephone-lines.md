---
title: Планирование частных телефонных линий в Skype для бизнеса
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9cc4f9e1-7b7a-4699-bd05-f16669ef2d21
description: Планирование частных (дополнительных) телефонных линий в Skype для бизнеса Server Корпоративная голосовая связь.
ms.openlocfilehash: 0ae62c4ee56a16583106c89b5ca1b190ee242e2c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813599"
---
# <a name="plan-for-private-telephone-lines-with-skype-for-business"></a><span data-ttu-id="3786c-103">Планирование частных телефонных линий в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="3786c-103">Plan for private telephone lines with Skype for Business</span></span>
 
<span data-ttu-id="3786c-104">Планирование частных (дополнительных) телефонных линий в Skype для бизнеса Server Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="3786c-104">Planning for private (secondary) telephone lines in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="3786c-105">Skype для бизнеса Server позволяет предоставить пользователям вторую частную телефонную линию в дополнение к основной телефонной линии.</span><span class="sxs-lookup"><span data-stu-id="3786c-105">Skype for Business Server enables you to give users a second, private telephone line in addition to their primary telephone line.</span></span> <span data-ttu-id="3786c-106">Частные телефонные линии обычно выделяются руководителям и тем, кому нужен номер телефона, не внесенный в список, по которому с ними можно связаться напрямую.</span><span class="sxs-lookup"><span data-stu-id="3786c-106">Private telephone lines are often assigned to executives and others who want an unlisted telephone number at which they can be reached directly.</span></span>
  
<span data-ttu-id="3786c-107">Частные телефонные линии можно настроить только с помощью оболочки управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="3786c-107">Private telephone lines can only be configured with the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="3786c-108">Нельзя настроить частные телефонные линии с помощью панели управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="3786c-108">You cannot configure private telephone lines with the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="3786c-109">Частные телефонные линии следует настраивать только в развертываниях Skype для бизнеса Server, а не в смешанных развертываниях.</span><span class="sxs-lookup"><span data-stu-id="3786c-109">Private telephone lines should be configured only in deployments of Skype for Business Server and not in mixed deployments.</span></span>
  
## <a name="characteristics-of-private-telephone-lines"></a><span data-ttu-id="3786c-110">Характеристики частных телефонных линий</span><span class="sxs-lookup"><span data-stu-id="3786c-110">Characteristics of Private Telephone Lines</span></span>

<span data-ttu-id="3786c-111">Хотя концепция второй частной телефонной линии в корне проста, важно понимать характеристики частных линий и способы их сходства с основными телефонными линиями пользователей и отличаются от них.</span><span class="sxs-lookup"><span data-stu-id="3786c-111">Although the concept of a second, private telephone line is fundamentally simple, it is important to understand the characteristics of private lines and the ways in which they are similar to and different from users' primary telephone lines.</span></span>
  
### <a name="general-characteristics-of-private-telephone-lines"></a><span data-ttu-id="3786c-112">Основные характеристики частных телефонных линий</span><span class="sxs-lookup"><span data-stu-id="3786c-112">General Characteristics of Private Telephone Lines</span></span>

- <span data-ttu-id="3786c-113">Пользователь может иметь только одну частную телефонную линию.</span><span class="sxs-lookup"><span data-stu-id="3786c-113">A user can have only one private telephone line.</span></span>
    
- <span data-ttu-id="3786c-114">Пользователь с частной телефонной линией может иметь только один ящик голосовой почты и получает уведомления о пропущенных звонках только на один адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="3786c-114">A user with a private telephone line has only one voice mailbox and receives missed call notifications at a single email address.</span></span>
    
- <span data-ttu-id="3786c-115">Пользователь с частной телефонной линией не имеет дополнительного SIP-адреса, а дополнительная частная телефонная линия не дает пользователю второе присутствие в сети (такое, как второе удостоверение в системе обмена мгновенными сообщениями).</span><span class="sxs-lookup"><span data-stu-id="3786c-115">A user with a private telephone line does not have a second SIP address, and a second, private telephone line does not give a user a second presence on the network (such as a second instant messaging identity).</span></span> 
    
- <span data-ttu-id="3786c-116">Частные телефонные линии доступны только для локальных развертываний.</span><span class="sxs-lookup"><span data-stu-id="3786c-116">Private telephone lines are available for on-premises deployments only.</span></span> <span data-ttu-id="3786c-117">Они недоступны в размещенном развертывании Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="3786c-117">They are not available with hosted deployments of Skype for Business Server.</span></span>
    
### <a name="how-private-telephone-lines-differ-from-primary-telephone-lines"></a><span data-ttu-id="3786c-118">Отличия частных телефонных линий от основных телефонных линий</span><span class="sxs-lookup"><span data-stu-id="3786c-118">How Private Telephone Lines Differ from Primary Telephone Lines</span></span>

- <span data-ttu-id="3786c-119">Телефонные номера частных телефонных линий не отображаются в телефонных справочниках и в списках контактов, полученных из доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3786c-119">The telephone numbers for private telephone lines do not appear in the telephone directories or Contacts lists that are derived from Active Directory Domain Services.</span></span>
    
- <span data-ttu-id="3786c-120">С частной телефонной линией недоступны следующие функции: переад вызовы, групповые звонки, делегирования, групповой звонок, групповой ответ на звонки и приложение группы ответа.</span><span class="sxs-lookup"><span data-stu-id="3786c-120">None of the following features are available with a private telephone line: call forwarding, team call, delegation, team ring, Group Call Pickup, and Response Group application.</span></span>
    
- <span data-ttu-id="3786c-121">Вызовы, поступающие на частную телефонную линию, имеют специальный сигнал, и системное уведомление о вызове сообщает пользователю, что на его частную линию поступил входящий вызов.</span><span class="sxs-lookup"><span data-stu-id="3786c-121">Calls to a private telephone line have a special ring, and the system notification for the call tells the user that the incoming call is on his or her private line.</span></span>
    
- <span data-ttu-id="3786c-p104">Вызовы, поступающие на частную телефонную линию, всегда звонят. Они не следуют правилам "Не беспокоить".</span><span class="sxs-lookup"><span data-stu-id="3786c-p104">Calls to the private telephone line always ring through. They do not follow "do not disturb" rules.</span></span>
    
- <span data-ttu-id="3786c-124">Частные телефонные линии предназначены только для приема вызовов и не могут использоваться для выполнения исходящих вызовов.</span><span class="sxs-lookup"><span data-stu-id="3786c-124">Private telephone lines are inbound only and cannot be used to make outgoing calls.</span></span> <span data-ttu-id="3786c-125">Когда пользователь с частной телефонной линией совершает звонок, вызов поступает из основной телефонной линии пользователя и не скрывает имя пользователя или основной телефонный номер пользователя от вызываемого пользователя.</span><span class="sxs-lookup"><span data-stu-id="3786c-125">When a user with a private telephone line makes a call, the call originates from the user's primary telephone line and does not hide the user's name or the user's primary telephone number from the person called.</span></span>
    
### <a name="how-private-telephone-lines-are-similar-to-primary-telephone-lines"></a><span data-ttu-id="3786c-126">Сходство частных телефонных линий и основных телефонных линий</span><span class="sxs-lookup"><span data-stu-id="3786c-126">How Private Telephone Lines Are Similar to Primary Telephone Lines</span></span>

- <span data-ttu-id="3786c-127">Неотвеченные вызовы, поступившие на частную телефонную линию, направляются в ту же папку "Входящие" голосовой почты, что и вызовы по основной телефонной линии (если голосовая почта включена).</span><span class="sxs-lookup"><span data-stu-id="3786c-127">Unanswered calls to a private telephone line are routed to the same voice mail inbox as for the primary telephone line (if voice mail is enabled).</span></span>
    
- <span data-ttu-id="3786c-128">Парковка вызовов и их раздатка работают с частными телефонными линиями точно так же, как и с основной телефонной линией пользователя.</span><span class="sxs-lookup"><span data-stu-id="3786c-128">Call park and call pickup work with private telephone lines in exactly the same manner as they do with the user's primary telephone line.</span></span>
    
- <span data-ttu-id="3786c-129">Если одновременные звонки включены на основной телефонной линии пользователя, он также включен на частной телефонной линии.</span><span class="sxs-lookup"><span data-stu-id="3786c-129">When simultaneous ringing is enabled on a user's primary telephone line, it is also enabled on the private telephone line.</span></span>
    
- <span data-ttu-id="3786c-130">Телефонный номер для частной телефонной линии записи в записи сведения о вызове так же, как номер телефона для основной телефонной линии пользователя, но с указанием, что это частный телефонный номер.</span><span class="sxs-lookup"><span data-stu-id="3786c-130">The telephone number for a private telephone line is recorded in the call detail record in the same manner as the telephone number for a user's primary telephone line, but with an indication that it is a private telephone number.</span></span>
    
- <span data-ttu-id="3786c-131">После того как пользователь отвечает на звонок по частной телефонной линии, он будет рассматриваться так же, как и вызов на основной телефонной линии пользователя.</span><span class="sxs-lookup"><span data-stu-id="3786c-131">After a user answers a call on a private telephone line, the call is treated the same as a call on the user's primary telephone line.</span></span> <span data-ttu-id="3786c-132">Например, если пользователь, который получает звонок по частной телефонной линии, переададирует звонок или приглашает других пользователей в конференц-связь, имя пользователя отображается в Skype для бизнеса, а номер телефона для основной телефонной линии пользователя отображается в ИД вызывающего.</span><span class="sxs-lookup"><span data-stu-id="3786c-132">For example, if a user who receives a call on a private telephone line forwards the call or invites others to a conference call, the user's name appears in Skype for Business, and the telephone number for the user's primary telephone line appears in caller ID.</span></span>
    
- <span data-ttu-id="3786c-133">Пользователь может отклонить поступивший по частной телефонной линии вызов (еще до ответа перенаправить его в другое место назначения, например на мобильный телефон или на домашний телефон) точно так же, как вызов, поступивший по основной телефонной линии.</span><span class="sxs-lookup"><span data-stu-id="3786c-133">A user can deflect a call (redirect the call to another destination, such as a mobile phone or home phone, before answering) from the private telephone line in the same manner as with a primary telephone line.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="3786c-134">Когда вызов по частной телефонной линии перенаправляется на другой телефонный номер, то телефонный номер в частной телефонной линии становится доступным для этого другого телефонного номера и может отображаться в журналах для этого номера.</span><span class="sxs-lookup"><span data-stu-id="3786c-134">When a call to a private line is routed to an alternate telephone number, the telephone number for the private telephone line is made available to the alternate telephone number and can be displayed in the logs for that number.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="3786c-135">Вызовы из конференции на частную  телефонную линию не будут иметь индикацию частной линии в уведомлении системы входящих вызовов.</span><span class="sxs-lookup"><span data-stu-id="3786c-135">Calls from a conference to the private telephone line will not have a  *private-line*  indication in the incoming system notification.</span></span>
  
## <a name="administering-private-telephone-lines"></a><span data-ttu-id="3786c-136">Администрирование частных телефонных линий</span><span class="sxs-lookup"><span data-stu-id="3786c-136">Administering Private Telephone Lines</span></span>

<span data-ttu-id="3786c-p107">Помимо технических аспектов создания частных телефонных линий и управления ими необходимо будет установить для них административные процедуры. Сюда входит установка политик для определения лиц, имеющих в организации право на частную телефонную линию, создание и обслуживание списков таких лиц и их телефонных линий, возможно создание закрытого телефонного справочника для руководства, организация обучения пользователей и связанные задачи.</span><span class="sxs-lookup"><span data-stu-id="3786c-p107">In addition to the technical aspects of creating and managing private telephone lines, you will need to establish administrative procedures for them. This includes determining policies for who in the organization is eligible for a private line, creating and maintaining lists of people and their telephone lines, possibly creating a private telephone directory for executives, arranging for user training, and related tasks.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3786c-p108">Частная телефонная линия хранится в Active Directory как атрибут msRTCSIP-PrivateLine объекта-пользователя. По умолчанию любой член группы проверенных пользователей имеет доступ на чтение этого атрибута.</span><span class="sxs-lookup"><span data-stu-id="3786c-p108">The private telephone line is stored in Active Directory as an msRTCSIP-PrivateLine attribute on the user object. By default any member of the Authenticated Users group has read access to this attribute.</span></span> 
  
### <a name="assigning-telephone-numbers"></a><span data-ttu-id="3786c-141">Назначение телефонных номеров</span><span class="sxs-lookup"><span data-stu-id="3786c-141">Assigning Telephone Numbers</span></span>

 <span data-ttu-id="3786c-142">Учетные записи для новых пользователей, которым требуются частные телефонные линии, создаются так же, как и учетные записи без частных телефонных линий, с помощью панели управления Skype для бизнеса Server или skype для бизнеса Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="3786c-142">Accounts for new users who need private telephone lines are created in the same manner as accounts without private telephone lines, using Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="3786c-143">Используйте cmdlet **Set-CsUser** в оболочке управления Skype для бизнеса Server, чтобы назначить телефонный номер частной телефонной линии для пользователя, например **Set-CsUser -Identity "sip:joe@contoso.com" -PrivateLine "Tel:+14255551212"**.</span><span class="sxs-lookup"><span data-stu-id="3786c-143">Use the **Set-CsUser** cmdlet in the Skype for Business Server Management Shell to assign a telephone number to a private telephone line for a user, for example, **Set-CsUser -Identity "sip:joe@contoso.com" -PrivateLine "Tel:+14255551212"**.</span></span>
  
<span data-ttu-id="3786c-144">Телефонные номера частных телефонных линий могут быть длиной от 3 до 15 номеров и должны иметь префикс "TEL:".</span><span class="sxs-lookup"><span data-stu-id="3786c-144">Telephone numbers for private telephone lines can be between 3 and 15 numbers in length and must be preceded with the "TEL:" prefix.</span></span> <span data-ttu-id="3786c-145">Они могут иметь любой код города и любой код страны или региона, если ваша организация имеет прямой входной набор для этого кода города и кода страны или региона.</span><span class="sxs-lookup"><span data-stu-id="3786c-145">They can have any area code and any country/region code as long as your organization has direct inward dialing for that area code and country/region code.</span></span> 
  
<span data-ttu-id="3786c-146">For details about cmdlets and Skype for Business Server Management Shell, see the Skype for Business Server Management Shell documentation.</span><span class="sxs-lookup"><span data-stu-id="3786c-146">For details about cmdlets and Skype for Business Server Management Shell, see the Skype for Business Server Management Shell documentation.</span></span>
  
### <a name="private-telephone-lines-in-mixed-deployments"></a><span data-ttu-id="3786c-147">Частные телефонные линии в смешанных развертываниях</span><span class="sxs-lookup"><span data-stu-id="3786c-147">Private Telephone Lines in Mixed Deployments</span></span>

<span data-ttu-id="3786c-148">Частные телефонные линии должны быть настроены только для развертывания Skype для бизнеса Server или Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3786c-148">Private telephone lines should be configured only for deployments of Skype for Business Server or Lync Server 2013.</span></span> <span data-ttu-id="3786c-149">В развертывании, где существуют серверы с более ранними версиями Lync Server, когда пользователь в более ранних версиях пытается позвонить по частной телефонной линии, перенаправка вызова заканчивается неудачей, так как сервер не может выполнить обратный просмотр номера в частной телефонной линии.</span><span class="sxs-lookup"><span data-stu-id="3786c-149">In a deployment in which there are servers running earlier versions of Lync Server, when a user on earlier version attempts to call a private telephone line, routing of the call fails because the server cannot perform a reverse number lookup on a private telephone line.</span></span>
  

