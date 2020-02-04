---
title: 'Lync Server 2013: вопросы миграции для собраний'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration considerations for meetings
ms:assetid: a9807d58-99a3-4cff-b4c6-74950d106a2b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412800(v=OCS.15)
ms:contentKeyID: 61097556
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6af94514360509d4f608a21228b2fecf9a522007
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727739"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-considerations-for-meetings-in-lync-server-2013"></a><span data-ttu-id="64e91-102">Вопросы миграции для собраний в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="64e91-102">Migration considerations for meetings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="64e91-103">_**Тема последнего изменения:** 2014-02-10_</span><span class="sxs-lookup"><span data-stu-id="64e91-103">_**Topic Last Modified:** 2014-02-10_</span></span>

<span data-ttu-id="64e91-104">В этом разделе рассматриваются следующие темы:</span><span class="sxs-lookup"><span data-stu-id="64e91-104">The following topics are discussed in this section:</span></span>

  - <span data-ttu-id="64e91-105">Изменения в собраниях в Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="64e91-105">Changes to meetings in Microsoft Lync Server 2013</span></span>

  - <span data-ttu-id="64e91-106">Миграция пользователей в соответствии с их потребностями в конференц-связи</span><span class="sxs-lookup"><span data-stu-id="64e91-106">Migrating users based on their conferencing needs</span></span>

  - <span data-ttu-id="64e91-107">Миграция существующих собраний и содержимого собраний</span><span class="sxs-lookup"><span data-stu-id="64e91-107">Migrating existing meetings and meeting content</span></span>

  - <span data-ttu-id="64e91-108">Взаимодействие с пользователем во время миграции Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="64e91-108">User experience during Lync Server 2010 migration</span></span>

  - <span data-ttu-id="64e91-109">Взаимодействие с пользователем во время миграции Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="64e91-109">User Experience during Office Communications Server 2007 R2 migration</span></span>

  - <span data-ttu-id="64e91-110">Совместимость Microsoft Lync 2013 с собраниями в более ранних версиях сервера</span><span class="sxs-lookup"><span data-stu-id="64e91-110">Microsoft Lync 2013 compatibility with meetings on earlier server versions</span></span>

<div>

## <a name="changes-to-meetings-in-lync-server-2013"></a><span data-ttu-id="64e91-111">Изменения собраний в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="64e91-111">Changes to Meetings in Lync Server 2013</span></span>

<span data-ttu-id="64e91-112">**Возможности Lync Server 2013.**    Lync Server 2013 предлагает новые функции для конференций, которые становятся доступны пользователям после перемещения учетных записей на lync Server 2013 и входа в систему с помощью клиента Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="64e91-112">**Lync Server 2013 features.**   Lync Server 2013 provides new conferencing features that become available to users after their accounts are moved to Lync Server 2013 and they sign in with the Lync 2013 client.</span></span> <span data-ttu-id="64e91-113">Новые возможности, описанные в [новых функциях Конференции в Lync server 2013](lync-server-2013-new-conferencing-features.md) и [новые возможности для клиентов в Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span><span class="sxs-lookup"><span data-stu-id="64e91-113">New features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

<span data-ttu-id="64e91-114">**URL-адрес собрания.**    Как и в lync Server 2010, для всех новых запланированных собраний в lync Server 2013 есть префикс URL-адреса HTTPS://, а существующие собрания переносятся вместе с учетными записями пользователей.</span><span class="sxs-lookup"><span data-stu-id="64e91-114">**Meeting URL.**   As in Lync Server 2010, all newly scheduled meetings in Lync Server 2013 have a URL prefix of https:// and existing meetings migrate along with user accounts.</span></span> <span data-ttu-id="64e91-115">Однако Lync Server 2013 не поддерживает вызов конференции Office Communications Server 2007 R2 (префикс URL-адреса conf://) или веб-конференция (префикс URL-адреса meet://).</span><span class="sxs-lookup"><span data-stu-id="64e91-115">However, Lync Server 2013 does not support the Office Communications Server 2007 R2 conference call (conf:// URL prefix) or web conference (meet:// URL prefix).</span></span> <span data-ttu-id="64e91-116">Дополнительные сведения приведены в разделе "перенос собраний из Office Communications Server 2007 R2" ниже.</span><span class="sxs-lookup"><span data-stu-id="64e91-116">See “Migrating Meetings from Office Communications Server 2007 R2” later in this topic for more information.</span></span>

<span data-ttu-id="64e91-117">**Поддержка клиентов.**    В отличие от lync Server 2010, lync Server 2013 не поддерживает клиентов Office Communicator для конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="64e91-117">**Client support.**   Unlike Lync Server 2010, Lync Server 2013 does not support Office Communicator clients for conferencing.</span></span> <span data-ttu-id="64e91-118">Вы не можете использовать следующие клиенты для присоединения к собраниям, запланированным с помощью надстройки "собрание по сети" для Lync 2013:</span><span class="sxs-lookup"><span data-stu-id="64e91-118">You cannot use the following clients to join meetings scheduled through the Online Meeting Add-in for Lync 2013:</span></span>

  - <span data-ttu-id="64e91-119">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="64e91-119">Office Communicator 2007 R2</span></span>

  - <span data-ttu-id="64e91-120">Microsoft Office Communications Server 2007 R2 Attendant</span><span class="sxs-lookup"><span data-stu-id="64e91-120">Microsoft Office Communications Server 2007 R2 Attendant</span></span>

  - <span data-ttu-id="64e91-121">Office Communicator 2007</span><span class="sxs-lookup"><span data-stu-id="64e91-121">Office Communicator 2007</span></span>

  - <span data-ttu-id="64e91-122">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="64e91-122">Office Live Meeting 2007</span></span>

<span data-ttu-id="64e91-123">Во время миграции пользователи Office Communicator 2007 R2 должны использовать Lync Web App 2013 для присоединения к собраниям Lync Server 2013, пока их клиенты не будут обновлены.</span><span class="sxs-lookup"><span data-stu-id="64e91-123">During migration, Office Communicator 2007 R2 users should use Lync Web App 2013 to join Lync Server 2013 meetings until their clients are upgraded.</span></span> <span data-ttu-id="64e91-124">Обратите внимание, что пользователи Office Communicator 2007 R2 могут по-прежнему использовать существующий клиент для Lync Server 2013 для функций присутствия и обмена мгновенными сообщениями, но функции Конференции не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="64e91-124">Note that Office Communicator 2007 R2 users can continue to use their existing client against Lync Server 2013 for presence and IM features, but conferencing features are not supported.</span></span>

<div>


</div>

</div>

<div>

## <a name="migrating-users-based-on-their-conferencing-needs"></a><span data-ttu-id="64e91-125">Миграция пользователей в соответствии с их потребностями в конференц-связи</span><span class="sxs-lookup"><span data-stu-id="64e91-125">Migrating Users Based on Their Conferencing Needs</span></span>

<span data-ttu-id="64e91-126">**Частые организаторов собраний.**    Рассматривайте организаторов на раннем этапе собрания, чтобы они могли использовать новые функции lync Server 2013 и Lync 2013, описанные в разделе [новые возможности конференции в Lync Server 2013](lync-server-2013-new-conferencing-features.md) и [новые версии для клиентов в Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span><span class="sxs-lookup"><span data-stu-id="64e91-126">**Frequent meeting organizers.**   Consider migrating frequent meeting organizers early in the process so that they can take advantage of the new Lync Server 2013 and Lync 2013 features outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

<span data-ttu-id="64e91-127">**Пользователи Live Meeting.**    Если вы выполняете миграцию с Office Communications Server 2007 R2 и у вас есть пользователи, которым нужны возможности веб-конференций, специфичные для собрания по сети, особенно поддержка крупных собраний и перерывов, вы можете использовать следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="64e91-127">**Live Meeting users.**   If you are migrating from Office Communications Server 2007 R2 and you have users who need web conferencing features specific to Live Meeting—particularly support for large meetings and break-out rooms—you have the following options:</span></span>

  - <span data-ttu-id="64e91-128">Посоветуйте организаторов использовать службу Live Meeting, если она доступна в Организации.</span><span class="sxs-lookup"><span data-stu-id="64e91-128">Advise organizers to use the Live Meeting service, if available in your organization.</span></span>

  - <span data-ttu-id="64e91-129">Оставьте организаторов на веб-сайте более ранней версии Office Communications Server, чтобы они могли планировать сетевые конференции в реальном собрании на основе сервера.</span><span class="sxs-lookup"><span data-stu-id="64e91-129">Leave the organizers homed on the earlier version of Office Communications Server, so they can continue to schedule server-based Live Meeting web conferences.</span></span>

</div>

<div>

## <a name="migrating-existing-meetings-and-meeting-content"></a><span data-ttu-id="64e91-130">Миграция существующих собраний и содержимого собраний</span><span class="sxs-lookup"><span data-stu-id="64e91-130">Migrating Existing Meetings and Meeting Content</span></span>

<div>

## <a name="migrating-meetings-from-lync-server-2010"></a><span data-ttu-id="64e91-131">Перенос собраний из Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="64e91-131">Migrating Meetings from Lync Server 2010</span></span>

<span data-ttu-id="64e91-132">При перемещении пользователя из Lync Server 2010 в Lync Server 2013 следующие данные перемещаются с помощью учетной записи пользователя:</span><span class="sxs-lookup"><span data-stu-id="64e91-132">When you move a user from Lync Server 2010 to Lync Server 2013, the following information moves with the user’s account:</span></span>

  - <span data-ttu-id="64e91-133">Собрания, уже запланированные пользователем.</span><span class="sxs-lookup"><span data-stu-id="64e91-133">Meetings already scheduled by the user.</span></span> <span data-ttu-id="64e91-134">Сюда входят каталоги конференций и данные конференций.</span><span class="sxs-lookup"><span data-stu-id="64e91-134">This includes conferencing directories and conferencing data.</span></span>

  - <span data-ttu-id="64e91-135">Персональный идентификационный номер пользователя (ПИН-код).</span><span class="sxs-lookup"><span data-stu-id="64e91-135">The user’s personal identification number (PIN).</span></span> <span data-ttu-id="64e91-136">Текущий ПИН-код пользователя продолжает работать, пока не истечет срок действия или пользователь запросит новый ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="64e91-136">The user’s current PIN continues to work until it expires or the user requests a new PIN.</span></span>

<span data-ttu-id="64e91-137">Однако указанные ниже сведения об учетной записи пользователя не перемещаются на новый сервер.</span><span class="sxs-lookup"><span data-stu-id="64e91-137">However, the following user account information does not move to the new server:</span></span>

  - <span data-ttu-id="64e91-138">Содержимое собрания (например, презентации PowerPoint, содержимое доски и данные опросов)</span><span class="sxs-lookup"><span data-stu-id="64e91-138">Meeting content, for example PowerPoint presentations, whiteboard content, and poll data</span></span>

<span data-ttu-id="64e91-139">Чтобы переместить содержимое, совместно используемое в собраниях, используйте параметр Мовемитингконтент командлета Move-CsUser.</span><span class="sxs-lookup"><span data-stu-id="64e91-139">To move the content that has been shared in meetings, use the MoveMeetingContent parameter of the Move-CsUser cmdlet.</span></span> <span data-ttu-id="64e91-140">Подробнее об использовании этого командлета можно найти в документации по командлетам Lync Server 2013, описанным в разделе [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) .</span><span class="sxs-lookup"><span data-stu-id="64e91-140">For details about using this cmdlet, see [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) in the Lync Server 2013 cmdlets documentation.</span></span>

</div>

<div>

## <a name="migrating-meetings-from-office-communications-server-2007-r2"></a><span data-ttu-id="64e91-141">Миграция собраний из Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="64e91-141">Migrating Meetings from Office Communications Server 2007 R2</span></span>

<span data-ttu-id="64e91-142">Office Communications Server 2007 R2 — это либо телефонные конференции (префикс URL-адреса conf://), либо веб-конференции (meet://prefix URL-адрес).</span><span class="sxs-lookup"><span data-stu-id="64e91-142">Office Communications Server 2007 R2 meetings are either conference calls (conf:// URL prefix) or web conferences (meet:// URL prefix).</span></span> <span data-ttu-id="64e91-143">Lync Server 2013 не поддерживает эти более ранние конференции conf://и meet://, и они не переносятся вместе с учетной записью пользователя.</span><span class="sxs-lookup"><span data-stu-id="64e91-143">Lync Server 2013 does not support these earlier conf:// and meet:// conferences, and they are not migrated along with the user account.</span></span> <span data-ttu-id="64e91-144">После миграции вы должны попросить пользователей обновить ссылки для запланированных собраний по сети.</span><span class="sxs-lookup"><span data-stu-id="64e91-144">After migration, you should instruct users to update the links for any online meetings they have scheduled.</span></span> <span data-ttu-id="64e91-145">Они могут сделать это после установки клиента Lync 2013, открыв запланированное приглашение на собрание (которое обновляет URL-адрес собрания) и повторно отправляет приглашение участникам.</span><span class="sxs-lookup"><span data-stu-id="64e91-145">They can do this after installing the Lync 2013 client by opening a scheduled meeting invitation—which updates the meeting URL—and resending the invitation to participants.</span></span>

</div>

</div>

<div>

## <a name="user-experience-during-lync-server-2010-migration"></a><span data-ttu-id="64e91-146">Взаимодействие с пользователем во время миграции Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="64e91-146">User Experience during Lync Server 2010 Migration</span></span>

<span data-ttu-id="64e91-147">В этом разделе приведены краткие сведения о средствах конференц-связи пользователей при переходе с Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="64e91-147">This section provides a summary of users’ conferencing experience when migrating from Lync 2010.</span></span> <span data-ttu-id="64e91-148">Дополнительные сведения о том, как пользователи Lync Server 2013 могут сосуществовать и взаимодействовать с предыдущими версиями клиента и сервера, приведены [в разделе взаимодействие с клиентами в Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).</span><span class="sxs-lookup"><span data-stu-id="64e91-148">For more details about how Lync Server 2013 clients can coexist and interact with previous client and server versions, see [Client interoperability in Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).</span></span>

<div>

## <a name="joining-lync-server-2010-meetings-with-a-lync-2013-client"></a><span data-ttu-id="64e91-149">Присоединение к собраниям Lync Server 2010 с помощью клиента Lync 2013</span><span class="sxs-lookup"><span data-stu-id="64e91-149">Joining Lync Server 2010 Meetings with a Lync 2013 Client</span></span>

<span data-ttu-id="64e91-150">Во время миграции с Lync Server 2010 может возникнуть срок сосуществования, когда пользователи присоединяются к собраниям Lync Server 2010 с помощью клиента Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="64e91-150">During migration from Lync Server 2010, there may be a period of coexistence when users join Lync Server 2010 meetings with a Lync 2013 client.</span></span> <span data-ttu-id="64e91-151">Эти пользователи имеют доступ к функциям клиента Lync 2013 со следующими исключениями:</span><span class="sxs-lookup"><span data-stu-id="64e91-151">These users have access to Lync 2013 client features with the following exceptions:</span></span>

  - <span data-ttu-id="64e91-152">В параметрах управления **участниками** , доступ к которым осуществляется с помощью значка "люди" в окне собрания, не будет работать параметр " **мгновенное сообщение о собрании** ".</span><span class="sxs-lookup"><span data-stu-id="64e91-152">In the **Participants** management options, which are accessible by pointing to the people icon in the meeting window, the **No Meeting IM** option does not function.</span></span>

  - <span data-ttu-id="64e91-153">Представление коллекции не может работать в видеоконференциях.</span><span class="sxs-lookup"><span data-stu-id="64e91-153">Gallery View does not function in video conferences.</span></span> <span data-ttu-id="64e91-154">Пользователь видит только активный динамик, а не все динамики.</span><span class="sxs-lookup"><span data-stu-id="64e91-154">The user sees only the active speaker instead of all speakers.</span></span> <span data-ttu-id="64e91-155">В списке выбора параметров **разметки** недоступен **режим коллекции**</span><span class="sxs-lookup"><span data-stu-id="64e91-155">In the list of **Pick a Layout** options, **Gallery View** is unavailable</span></span>

  - <span data-ttu-id="64e91-156">Список участников по умолчанию отображается в видеоконференциях.</span><span class="sxs-lookup"><span data-stu-id="64e91-156">The participant list displays by default in video conferences.</span></span>

  - <span data-ttu-id="64e91-157">Если щелкнуть пользователя правой кнопкой мыши в списке участников, вы не **сможете получить** **доступ к** параметрам управления участниками коллекции.</span><span class="sxs-lookup"><span data-stu-id="64e91-157">When right-clicking a user in the participants list, the **Lock the Video Spotlight** and **Pin to Gallery** participant management options are unavailable.</span></span>

</div>

</div>

<div>

## <a name="user-experience-during-office-communications-server-2007-r2-migration"></a><span data-ttu-id="64e91-158">Взаимодействие с пользователем во время миграции Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="64e91-158">User Experience during Office Communications Server 2007 R2 Migration</span></span>

<span data-ttu-id="64e91-159">В этом разделе приведены краткие сведения о средствах конференц-связи пользователей при переходе с Office Communications Server 2007 R2 до и после установки Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="64e91-159">This section provides a summary of users’ conferencing experience when migrating from Office Communications Server 2007 R2, both before and after Lync 2013 is installed.</span></span> <span data-ttu-id="64e91-160">Дополнительные сведения о том, как пользователи Lync Server 2013 могут сосуществовать и взаимодействовать с предыдущими версиями клиента и сервера, приведены [в разделе взаимодействие с клиентами в Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).</span><span class="sxs-lookup"><span data-stu-id="64e91-160">For more details about how Lync Server 2013 clients can coexist and interact with previous client and server versions, see [Client interoperability in Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).</span></span>

<div>

## <a name="after-user-account-is-migrated-before-lync-2013-is-installed"></a><span data-ttu-id="64e91-161">После миграции учетной записи пользователя до установки Lync 2013</span><span class="sxs-lookup"><span data-stu-id="64e91-161">After User Account is Migrated, Before Lync 2013 Is Installed</span></span>

<span data-ttu-id="64e91-162">После того как пользователь будет перенесен на сервер Lync Server 2013, но перед установкой новых клиентов, пользователи Office Communicator 2007 R2 смогут продолжать использовать существующий клиент для Lync Server 2013 для функций присутствия и обмена мгновенными сообщениями, но функции Конференции не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="64e91-162">After a user is migrated to the Lync Server 2013 server, but before new clients are installed, Office Communicator 2007 R2 users can continue to use their existing client against Lync Server 2013 for presence and IM features, but conferencing features are not supported.</span></span>

</div>

<div>

## <a name="after-user-account-is-migrated-after-lync-2013-is-installed"></a><span data-ttu-id="64e91-163">После того как вы переносите учетную запись пользователя, после установки Lync 2013</span><span class="sxs-lookup"><span data-stu-id="64e91-163">After User Account is Migrated, After Lync 2013 Is Installed</span></span>

<span data-ttu-id="64e91-164">При установке Lync 2013 для пользователя, для которого выполнена миграция, будет установлена надстройка "собрание по сети" для Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="64e91-164">When a migrated user installs Lync 2013, the Online Meeting Add-in for Lync 2013 is installed too.</span></span> <span data-ttu-id="64e91-165">Ниже перечислены некоторые последствия.</span><span class="sxs-lookup"><span data-stu-id="64e91-165">This has the following effects:</span></span>

  - <span data-ttu-id="64e91-166">Во всех запланированных собраниях используется новый формат собрания, который использует https://адрес вместо старого адреса meet://Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="64e91-166">All subsequently scheduled meetings use the new meeting format, which uses an https:// address instead of the legacy meet:// Live Meeting address.</span></span>

  - <span data-ttu-id="64e91-167">При развертывании Lync 2013 администратор может удалить надстройку конференц-связи для Microsoft Office Outlook, которая используется для планирования сервера Live Meeting и собраний на основе служб.</span><span class="sxs-lookup"><span data-stu-id="64e91-167">In an IT-managed deployment of Lync 2013, the administrator has the option of uninstalling the Conferencing Add-in for Microsoft Office Outlook, which is used to schedule Live Meeting server and service-based meetings.</span></span> <span data-ttu-id="64e91-168">Однако вы можете иметь пользователей, которые должны продолжать планировать собрания в службе Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="64e91-168">However, you may have users who need to continue to schedule Live Meeting service meetings.</span></span> <span data-ttu-id="64e91-169">В этом случае обе надстройки можно разрешать сосуществование.</span><span class="sxs-lookup"><span data-stu-id="64e91-169">In this case, you can allow both add-ins to coexist.</span></span>

</div>

<div>

## <a name="meetings-with-federated-organizations-that-use-previous-clients"></a><span data-ttu-id="64e91-170">Собрания с федеративными организациями, которые используют предыдущие клиенты</span><span class="sxs-lookup"><span data-stu-id="64e91-170">Meetings with Federated Organizations that Use Previous Clients</span></span>

<span data-ttu-id="64e91-171">Пользователи в федеративных организациях, использующих Microsoft Office Communicator 2007, не могут присоединиться к собраниям Lync Server 2013 в вашей организации, если эти собрания заблокированы организатором.</span><span class="sxs-lookup"><span data-stu-id="64e91-171">Users in federated organizations who are using Microsoft Office Communicator 2007 cannot join Lync Server 2013 meetings in your organization if those meetings are locked by the organizer.</span></span> <span data-ttu-id="64e91-172">Вы должны перепланировать эти собрания в Lync Server 2013, чтобы присоединиться к собранию с помощью нового URL-адреса собрания https://, в котором они могут использовать Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="64e91-172">You have to reschedule these meetings in Lync Server 2013 so when federated participants join the meeting by using the new https:// meeting URL, they can use Lync Web App.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

