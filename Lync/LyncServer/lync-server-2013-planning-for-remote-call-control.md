---
title: 'Lync Server 2013: планирование удаленного управления звонком'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for remote call control
ms:assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558658(v=OCS.15)
ms:contentKeyID: 48184371
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ede2b5d63c57864f478cb8fd9bcd4689a91ab3d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824556"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="0e8a6-102">Планирование удаленного управления звонком в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0e8a6-102">Planning for remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e8a6-103">_**Тема последнего изменения:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="0e8a6-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="0e8a6-104">В Lync Server 2013 поддержка удаленными сценариями управления звонками позволяет пользователям управлять телефонами АТС с помощью Lync 2013 на настольных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-104">In Lync Server 2013, support for remote call control scenarios enables users to control their private branch exchange (PBX) phones by using Lync 2013 on their desktop computers.</span></span> <span data-ttu-id="0e8a6-105">В этом разделе описаны функции удаленного управления звонками и требования к развертыванию пульта дистанционного управления звонками.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-105">This section describes remote call control features and requirements for deploying remote call control.</span></span>

<span data-ttu-id="0e8a6-106">Интеграция между АТС и Lync Server 2013 делает возможным для пользователей, поддерживающих удаленное управление звонками, использование пользовательского интерфейса Lync 2013 для управления звонками на телефонах УАТС следующими способами.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-106">Integration between a PBX and Lync Server 2013 makes it possible for users enabled for remote call control to use the Lync 2013 user interface (UI) to control calls on their PBX phones in the following ways:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0e8a6-107">В конечном итоге возможности УАТС, в которой размещен телефон УАТС пользователя, определяют функции удаленного управления звонками, которые будут доступны для этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-107">Ultimately, the capabilities of the PBX that hosts a user’s PBX phone determine the remote call control features that will be available to that user.</span></span>



</div>

  - <span data-ttu-id="0e8a6-108">Совершение исходящих звонков</span><span class="sxs-lookup"><span data-stu-id="0e8a6-108">Make an outgoing call</span></span>

  - <span data-ttu-id="0e8a6-109">Ответ на входящий звонок</span><span class="sxs-lookup"><span data-stu-id="0e8a6-109">Answer an incoming call</span></span>

  - <span data-ttu-id="0e8a6-110">Ответ на входящий звонок с помощью мгновенного сообщения</span><span class="sxs-lookup"><span data-stu-id="0e8a6-110">Answer an incoming call with an instant message</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0e8a6-111">Это значит, что если телефонный номер вызывающего абонента может быть связан с адресом в глобальном списке адресов (GAL) своей организации, в списке контактов Lync вызываемого абонента или в Организации федеративного партнера.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-111">That is, when the caller’s phone number can be associated with an instant message address in your organization’s global address list (GAL), in the callee’s Lync Contacts list, or in a federated partner’s organization.</span></span>

    
    </div>

  - <span data-ttu-id="0e8a6-112">Перевод вызова</span><span class="sxs-lookup"><span data-stu-id="0e8a6-112">Transfer a call</span></span>

  - <span data-ttu-id="0e8a6-113">Переадресация входящего звонка</span><span class="sxs-lookup"><span data-stu-id="0e8a6-113">Forward an incoming call</span></span>

  - <span data-ttu-id="0e8a6-114">Разместите звонки на удержании</span><span class="sxs-lookup"><span data-stu-id="0e8a6-114">Place calls on hold</span></span>

  - <span data-ttu-id="0e8a6-115">Переключение между несколькими одновременными звонками</span><span class="sxs-lookup"><span data-stu-id="0e8a6-115">Alternate between multiple concurrent calls</span></span>

  - <span data-ttu-id="0e8a6-116">Ответ на второй звонок, пока он уже находится в звонке (то есть, в режиме ожидания звонка).</span><span class="sxs-lookup"><span data-stu-id="0e8a6-116">Answer a second call while already in a call (that is, call waiting)</span></span>

  - <span data-ttu-id="0e8a6-117">Набирать цифры с частотой двух тонов (DTMF)</span><span class="sxs-lookup"><span data-stu-id="0e8a6-117">Dial dual-tone multifrequency (DTMF) digits</span></span>

  - <span data-ttu-id="0e8a6-118">В окне беседы введите заметки в программе создания заметок в Microsoft Office OneNote.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-118">In the Conversation window, type notes in Microsoft Office OneNote note-taking program</span></span>

<span data-ttu-id="0e8a6-119">Кроме того, если пользователю разрешено удаленное управление звонками, Lync 2013 предоставляет пользователю следующие сведения о звонках:</span><span class="sxs-lookup"><span data-stu-id="0e8a6-119">Additionally, when a user is enabled for remote call control, Lync 2013 provides the user with the following call information:</span></span>

  - <span data-ttu-id="0e8a6-120">Идентификация вызывающего абонента по имени, если номер телефона вызывающего абонента указан в списке контактов клиента для обмена сообщениями и совместной работы в Microsoft Office Outlook, а также в списке контактов Lync или глобальном списке адресов организации.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-120">Identification of a caller by name when the caller’s phone number exists in the Contacts list of a remote call control-enabled user’s Microsoft Office Outlook messaging and collaboration client, Lync Contacts list, or your organization’s GAL.</span></span>

  - <span data-ttu-id="0e8a6-121">Входящие и исходящие звонки, сохраненные в папке "Журнал бесед" в Outlook.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-121">Past incoming and outgoing calls, which are saved in the Conversation History folder in Outlook.</span></span>

  - <span data-ttu-id="0e8a6-122">Уведомления о пропущенных звонках, которые отправляются в папку "Входящие" пользователя Outlook, но генерируются только в том случае, если приложение Lync запущено при получении входящего звонка.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-122">Missed call notifications, which are sent to the user’s Outlook Inbox folder, but are generated only if Lync is running when the incoming call is received.</span></span>

<div>

## <a name="remote-call-control-and-enterprise-voice"></a><span data-ttu-id="0e8a6-123">Удаленное управление звонками и Корпоративная голосовая связь</span><span class="sxs-lookup"><span data-stu-id="0e8a6-123">Remote Call Control and Enterprise Voice</span></span>

<span data-ttu-id="0e8a6-124">Несмотря на то, что функции удаленного управления звонками отделены от функций корпоративной голосовой связи и пользователи не могут быть включены одновременно для пользователей, корпоративный голос предоставляет подмножество функций, которые также доступны пользователям, поддерживающим удаленное управление звонками.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-124">Although remote call control features are separate from Enterprise Voice features and users cannot be enabled for both, Enterprise Voice provides a subset of features that are also available to users who are enabled for remote call control.</span></span> <span data-ttu-id="0e8a6-125">Если развернута Корпоративная голосовая связь, пользователи, которым разрешено удаленное управление звонками, смогут использовать Lync для доступа к следующим функциям корпоративного голосового ввода.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-125">If Enterprise Voice is deployed, users who are enabled for remote call control can use Lync to access the following Enterprise Voice features:</span></span>

  - <span data-ttu-id="0e8a6-126">Совершение и прием голосовых звонков для другого клиента Lync</span><span class="sxs-lookup"><span data-stu-id="0e8a6-126">Make and receive audio calls to another Lync client</span></span>

  - <span data-ttu-id="0e8a6-127">Присоединение к звуковой части Конференции, созданной пользователем, для которого включена Корпоративная голосовая связь</span><span class="sxs-lookup"><span data-stu-id="0e8a6-127">Join the audio portion of a conference created by a user who is enabled for Enterprise Voice</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0e8a6-128">Содержание</span><span class="sxs-lookup"><span data-stu-id="0e8a6-128">In This Section</span></span>

  - [<span data-ttu-id="0e8a6-129">Задачи развертывания для удаленного управления звонками в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0e8a6-129">Deployment tasks for remote call control in Lync Server 2013</span></span>](lync-server-2013-deployment-tasks-for-remote-call-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

