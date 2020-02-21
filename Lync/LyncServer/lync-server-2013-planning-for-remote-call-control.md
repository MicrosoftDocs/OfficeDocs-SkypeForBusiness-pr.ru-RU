---
title: 'Lync Server 2013: планирование удаленного управления звонками'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for remote call control
ms:assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558658(v=OCS.15)
ms:contentKeyID: 48184371
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35b8586df49eb1dd7a10e94d3231cc2fdc082353
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184112"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="6de96-102">Планирование удаленного управления звонками в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6de96-102">Planning for remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6de96-103">_**Последнее изменение темы:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="6de96-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="6de96-104">В Lync Server 2013 поддержка удаленных сценариев управления звонками позволяет пользователям управлять телефонами УАТС с помощью Lync 2013 на настольных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="6de96-104">In Lync Server 2013, support for remote call control scenarios enables users to control their private branch exchange (PBX) phones by using Lync 2013 on their desktop computers.</span></span> <span data-ttu-id="6de96-105">В этом разделе описываются функции удаленного контроля звонков.</span><span class="sxs-lookup"><span data-stu-id="6de96-105">This section describes remote call control features and requirements for deploying remote call control.</span></span>

<span data-ttu-id="6de96-106">Интеграция между УАТС и Lync Server 2013 позволяет пользователям с поддержкой удаленного управления вызовами использовать пользовательский интерфейс Lync 2013 для управления вызовами на телефонах УАТС следующими способами:</span><span class="sxs-lookup"><span data-stu-id="6de96-106">Integration between a PBX and Lync Server 2013 makes it possible for users enabled for remote call control to use the Lync 2013 user interface (UI) to control calls on their PBX phones in the following ways:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6de96-107">В конечном счете, возможности УАТС, где размещается телефон УАТС пользователя, определяют функции удаленного контроля звонков, доступные данному пользователю.</span><span class="sxs-lookup"><span data-stu-id="6de96-107">Ultimately, the capabilities of the PBX that hosts a user’s PBX phone determine the remote call control features that will be available to that user.</span></span>



</div>

  - <span data-ttu-id="6de96-108">Совершение исходящих вызовов</span><span class="sxs-lookup"><span data-stu-id="6de96-108">Make an outgoing call</span></span>

  - <span data-ttu-id="6de96-109">Ответ на входящие вызовы</span><span class="sxs-lookup"><span data-stu-id="6de96-109">Answer an incoming call</span></span>

  - <span data-ttu-id="6de96-110">Ответ на входящий вызов мгновенным сообщением</span><span class="sxs-lookup"><span data-stu-id="6de96-110">Answer an incoming call with an instant message</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6de96-111">То есть, когда телефонный номер абонента может быть связан с адресом для обмена мгновенными сообщениями в глобальном списке адресов вашей организации (GAL), в списке контактов Lync вызываемого абонента или в Организации федеративного партнера.</span><span class="sxs-lookup"><span data-stu-id="6de96-111">That is, when the caller’s phone number can be associated with an instant message address in your organization’s global address list (GAL), in the callee’s Lync Contacts list, or in a federated partner’s organization.</span></span>

    
    </div>

  - <span data-ttu-id="6de96-112">Перевод вызова</span><span class="sxs-lookup"><span data-stu-id="6de96-112">Transfer a call</span></span>

  - <span data-ttu-id="6de96-113">Переадресация входящего вызова</span><span class="sxs-lookup"><span data-stu-id="6de96-113">Forward an incoming call</span></span>

  - <span data-ttu-id="6de96-114">Перевод вызовов в режим удержания</span><span class="sxs-lookup"><span data-stu-id="6de96-114">Place calls on hold</span></span>

  - <span data-ttu-id="6de96-115">Переключение между несколькими одновременными вызовами</span><span class="sxs-lookup"><span data-stu-id="6de96-115">Alternate between multiple concurrent calls</span></span>

  - <span data-ttu-id="6de96-116">Ответ на второй вызов, в то время как вы уже отвечаете на другой вызов (то есть, ожидание вызова)</span><span class="sxs-lookup"><span data-stu-id="6de96-116">Answer a second call while already in a call (that is, call waiting)</span></span>

  - <span data-ttu-id="6de96-117">Набор цифр DTMF</span><span class="sxs-lookup"><span data-stu-id="6de96-117">Dial dual-tone multifrequency (DTMF) digits</span></span>

  - <span data-ttu-id="6de96-118">Вводите заметки в окне программы в Microsoft Office OneNote</span><span class="sxs-lookup"><span data-stu-id="6de96-118">In the Conversation window, type notes in Microsoft Office OneNote note-taking program</span></span>

<span data-ttu-id="6de96-119">Кроме того, если пользователю разрешено удаленное управление звонками, Lync 2013 предоставляет пользователю следующие сведения о вызовах:</span><span class="sxs-lookup"><span data-stu-id="6de96-119">Additionally, when a user is enabled for remote call control, Lync 2013 provides the user with the following call information:</span></span>

  - <span data-ttu-id="6de96-120">Идентификация вызывающего абонента по имени, если номер телефона вызывающего абонента существует в списке контактов клиента для обмена сообщениями и совместной работы пользователей Microsoft Office Outlook, списка контактов Lync или глобального списка адресов в Организации.</span><span class="sxs-lookup"><span data-stu-id="6de96-120">Identification of a caller by name when the caller’s phone number exists in the Contacts list of a remote call control-enabled user’s Microsoft Office Outlook messaging and collaboration client, Lync Contacts list, or your organization’s GAL.</span></span>

  - <span data-ttu-id="6de96-121">Прошедшие входящие и исходящие вызовы, которые сохранены в папке "Журнал бесед" в Outlook.</span><span class="sxs-lookup"><span data-stu-id="6de96-121">Past incoming and outgoing calls, which are saved in the Conversation History folder in Outlook.</span></span>

  - <span data-ttu-id="6de96-122">Уведомления о пропущенных звонках, которые отправляются в папку "Входящие" Outlook пользователя, но создаются только в том случае, если Lync выполняется при получении входящего вызова.</span><span class="sxs-lookup"><span data-stu-id="6de96-122">Missed call notifications, which are sent to the user’s Outlook Inbox folder, but are generated only if Lync is running when the incoming call is received.</span></span>

<div>

## <a name="remote-call-control-and-enterprise-voice"></a><span data-ttu-id="6de96-123">Удаленный контроль звонков и Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="6de96-123">Remote Call Control and Enterprise Voice</span></span>

<span data-ttu-id="6de96-124">Несмотря на то, что функции удаленного управления звонками отделены от функций корпоративной голосовой связи и пользователи не могут быть включены для пользователей, Корпоративная голосовая связь предоставляет подмножество функций, которые также доступны пользователям, для которых разрешено удаленное управление звонками.</span><span class="sxs-lookup"><span data-stu-id="6de96-124">Although remote call control features are separate from Enterprise Voice features and users cannot be enabled for both, Enterprise Voice provides a subset of features that are also available to users who are enabled for remote call control.</span></span> <span data-ttu-id="6de96-125">Если развернута Корпоративная голосовая связь, пользователи, которым разрешено удаленное управление звонками, могут использовать Lync для доступа к следующим функциям корпоративной голосовой связи:</span><span class="sxs-lookup"><span data-stu-id="6de96-125">If Enterprise Voice is deployed, users who are enabled for remote call control can use Lync to access the following Enterprise Voice features:</span></span>

  - <span data-ttu-id="6de96-126">Создание и получение голосовых вызовов другому клиенту Lync</span><span class="sxs-lookup"><span data-stu-id="6de96-126">Make and receive audio calls to another Lync client</span></span>

  - <span data-ttu-id="6de96-127">Присоединение к звуковой части Конференции, созданной пользователем, для которого включена поддержка корпоративной голосовой связи</span><span class="sxs-lookup"><span data-stu-id="6de96-127">Join the audio portion of a conference created by a user who is enabled for Enterprise Voice</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6de96-128">Содержание</span><span class="sxs-lookup"><span data-stu-id="6de96-128">In This Section</span></span>

  - [<span data-ttu-id="6de96-129">Задачи развертывания для удаленного управления звонками в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6de96-129">Deployment tasks for remote call control in Lync Server 2013</span></span>](lync-server-2013-deployment-tasks-for-remote-call-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

