---
title: 'Lync Server 2013: использование звонка на телефон с поддержкой Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Call Me At with a Lync-enabled phone
ms:assetid: 975a1df8-a159-4aa4-a991-5972a535998e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn383570(v=OCS.15)
ms:contentKeyID: 56470326
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d4b117970cec1e40b4d18928f82bc0cf2831eb8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744229"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-call-me-at-with-a-lync-enabled-phone-and-lync-server-2013"></a><span data-ttu-id="131d3-102">Использование звонка на телефон с поддержкой Lync и Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="131d3-102">Using Call Me At with a Lync-enabled phone and Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="131d3-103">_**Тема последнего изменения:** 2013-08-09_</span><span class="sxs-lookup"><span data-stu-id="131d3-103">_**Topic Last Modified:** 2013-08-09_</span></span>

<span data-ttu-id="131d3-104">Функция "позвонить мне в Lync" позволяет пользователям присоединиться к звуковой части конференции с помощью сотового телефона, "наземный линии" или другого устройства, подключенного к общественной коммутируемой телефонной сети (КТСОП).</span><span class="sxs-lookup"><span data-stu-id="131d3-104">The Call Me At feature in Lync provides a way for users to join the audio portion of a conference by using a cell phone, “land line,” or other device connected to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="131d3-105">При попытке присоединиться к собранию с помощью Lync вы обычно увидите диалоговое окно **присоединиться к звуковому каналу собрания** :</span><span class="sxs-lookup"><span data-stu-id="131d3-105">When you attempt to join a meeting by using Lync, you will typically be presented with the **Join Meeting Audio** dialog box:</span></span>

<span data-ttu-id="131d3-106">![Снимок экрана: окно "присоединение к звуковому каналу собрания" в Lync](images/Dn383570.e28f17f0-9f17-44ef-b893-f4ef132f47ac(OCS.15).png "Снимок экрана: окно "присоединение к звуковому каналу собрания" в Lync")</span><span class="sxs-lookup"><span data-stu-id="131d3-106">![Use Lync to join meeting audio window screenshot](images/Dn383570.e28f17f0-9f17-44ef-b893-f4ef132f47ac(OCS.15).png "Use Lync to join meeting audio window screenshot")</span></span>

<span data-ttu-id="131d3-107">Если вы выберете " **позвонить мне**", вы можете выбрать номер телефона из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="131d3-107">If you select **Call me at**, you can then pick a phone number from the dropdown list.</span></span> <span data-ttu-id="131d3-108">Lync Server 2013 помещает телефонный звонок на выбранный номер, и вы можете использовать этот телефон для участия в звуковой части Конференции.</span><span class="sxs-lookup"><span data-stu-id="131d3-108">Lync Server 2013 will place a phone call to the selected number, and you can then use that phone to participate in the audio portion of the conference.</span></span>

<span data-ttu-id="131d3-109">Раскрывающийся список заполняется номерами телефонов (для мобильного телефона, домашнего телефона или другого телефона), которые вы ввели на вкладке **телефоны** в диалоговом окне **Lync — параметры** .</span><span class="sxs-lookup"><span data-stu-id="131d3-109">The dropdown list is populated by the phone numbers (for mobile phone, home phone, or other phone) that you have entered on the **Phones** tab in the **Lync – Options** dialog box:</span></span>

<span data-ttu-id="131d3-110">![Снимок экрана: параметры настройки на телефоне с Lync](images/Dn383570.03d2f25d-49e2-47b4-b1e9-b1614fc0c11c(OCS.15).png "Снимок экрана: параметры настройки на телефоне с Lync")</span><span class="sxs-lookup"><span data-stu-id="131d3-110">![Lync Phones set up options screenshot](images/Dn383570.03d2f25d-49e2-47b4-b1e9-b1614fc0c11c(OCS.15).png "Lync Phones set up options screenshot")</span></span>

<span data-ttu-id="131d3-111">Если на вкладке **телефоны** не указаны номера телефонов, в раскрывающемся списке не будут доступны номера.</span><span class="sxs-lookup"><span data-stu-id="131d3-111">If you have not entered any phone numbers on the **Phones** tab then you will not have any numbers available in the dropdown box.</span></span> <span data-ttu-id="131d3-112">Тем не менее, вы всегда можете выбрать **новый номер** и установить для сервера Lync Server доступ к любому нужному номеру телефона.</span><span class="sxs-lookup"><span data-stu-id="131d3-112">However, you can always click **New Number** and have Lync Server dial out to any phone number you wish:</span></span>

<span data-ttu-id="131d3-113">![Снимок экрана: окно "присоединиться к звуковому каналу собрания Lync"](images/Dn383570.27f2ac7a-cc1c-465c-b145-202ad03af4f2(OCS.15).png "Снимок экрана: окно "присоединиться к звуковому каналу собрания Lync"")</span><span class="sxs-lookup"><span data-stu-id="131d3-113">![Lync join meeting audio call me window screenshot](images/Dn383570.27f2ac7a-cc1c-465c-b145-202ad03af4f2(OCS.15).png "Lync join meeting audio call me window screenshot")</span></span>

<span data-ttu-id="131d3-114">Функция "позвонить мне" очень хорошо подходит для использования в том виде, в котором она предназначена для того, чтобы Lync Server вызываю телефонный номер КТСОП.</span><span class="sxs-lookup"><span data-stu-id="131d3-114">The Call Me At feature works extremely well provided that you use it in the way it was intended: by having Lync Server call a PSTN phone number.</span></span> <span data-ttu-id="131d3-115">Тем не менее, если вы хотите, чтобы Lync Server мог позвонить вам на конечную точку с поддержкой Lync (например, на телефон в конференц-зале), вы можете работать в более удобной среде.</span><span class="sxs-lookup"><span data-stu-id="131d3-115">However, you can run into a less-than-optimal experience if you ask Lync Server to call you at a Lync-enabled endpoint (for example, a phone in a conference room).</span></span> <span data-ttu-id="131d3-116">Ниже приведена проблема, на которую вы можете столкнуться, а также два способа решения этой проблемы.</span><span class="sxs-lookup"><span data-stu-id="131d3-116">Following is the issue you might run into, as well as two ways to work around the problem.</span></span>

<span data-ttu-id="131d3-117">Ниже показано, что происходит, когда вы предоставляете звони мне по номеру телефона с телефонным подключением, поддерживающим Lync.</span><span class="sxs-lookup"><span data-stu-id="131d3-117">To begin, here’s what happens when you provide the Call Me At feature with the phone number of a Lync-enabled phone.</span></span> <span data-ttu-id="131d3-118">Предположим, что Кен мер пытается присоединиться к собранию, вызвав его в 1-206-555-1219, используя номер телефона, поддерживающий Lync Server.</span><span class="sxs-lookup"><span data-stu-id="131d3-118">Suppose Ken Myer tries to join a meeting by having Lync Server call him at 1-206-555-1219, a Lync Server-enabled phone number.</span></span> <span data-ttu-id="131d3-119">Кен сначала подключится к собранию, но после нескольких секунд, пока в Lync не будет **выполнен звонок, или он не был завершен**, а Кен будет удален из собрания:</span><span class="sxs-lookup"><span data-stu-id="131d3-119">Ken will initially be connected to the meeting, but after a few seconds Lync will display the message **Call was not completed or has ended**, and Ken will appear to have been dropped from the meeting:</span></span>

<span data-ttu-id="131d3-120">![Снимок экрана с окном конференц-связи Lync](images/Dn383570.c2a81727-8751-41b5-946a-03a1b75b9d95(OCS.15).png "Снимок экрана с окном конференц-связи Lync")</span><span class="sxs-lookup"><span data-stu-id="131d3-120">![Screen shot of Lync call conferencing window](images/Dn383570.c2a81727-8751-41b5-946a-03a1b75b9d95(OCS.15).png "Screen shot of Lync call conferencing window")</span></span>

<span data-ttu-id="131d3-121">Однако обратите внимание, что в окне беседы Lync есть несоответствие.</span><span class="sxs-lookup"><span data-stu-id="131d3-121">Notice, however, that there is a discrepancy within the Lync conversation window.</span></span> <span data-ttu-id="131d3-122">Кен мер — единственное имя, указанное в разделе " **Участники** ".</span><span class="sxs-lookup"><span data-stu-id="131d3-122">Ken Myer is the only name listed under the **Participants** heading.</span></span> <span data-ttu-id="131d3-123">Тем не менее, если посмотреть в строке заголовка окна, вы увидите, что Конференции содержали всего 4 участника.</span><span class="sxs-lookup"><span data-stu-id="131d3-123">However, if you look in the title bar of the window, you’ll see that the conference contains a total of 4 participants.</span></span>

<span data-ttu-id="131d3-124">Кроме того, если вы видите окно беседы любого из участников конференции, вы не увидите Кен мер в списке где угодно:</span><span class="sxs-lookup"><span data-stu-id="131d3-124">Likewise, if you look in the conversation window of any of the other conference participants you will not see Ken Myer listed anywhere:</span></span>

<span data-ttu-id="131d3-125">![Снимок экрана: окно списка участников Lync](images/Dn383570.fa5990cf-2694-402c-ac06-946aa66b6837(OCS.15).png "Снимок экрана: окно списка участников Lync")</span><span class="sxs-lookup"><span data-stu-id="131d3-125">![Lync participant list window screenshot](images/Dn383570.fa5990cf-2694-402c-ac06-946aa66b6837(OCS.15).png "Lync participant list window screenshot")</span></span>

<span data-ttu-id="131d3-126">Но в то же время, Кен мер сможет принимать участие в звуковой части звонка с помощью телефонного телефона, поддерживающего Lync.</span><span class="sxs-lookup"><span data-stu-id="131d3-126">And yet, at the same time, Ken Myer will be able to participate in the audio portion of the call by using his Lync-enabled phone.</span></span> <span data-ttu-id="131d3-127">Функция "позвонить мне" на самом деле работала, но взаимодействие с пользователем менее оптимально.</span><span class="sxs-lookup"><span data-stu-id="131d3-127">The Call Me At feature has actually worked, but the user experience is less than optimal.</span></span>

<span data-ttu-id="131d3-128">Существует по крайней мере два способа обойти эту проблему.</span><span class="sxs-lookup"><span data-stu-id="131d3-128">There are at least two ways to work around this problem.</span></span> <span data-ttu-id="131d3-129">Если вы уже присоединились к Конференции (например, Кен мер), вы обычно можете устранить проблему, вызвав другую модальность.</span><span class="sxs-lookup"><span data-stu-id="131d3-129">If you have already joined a conference in this fashion (like Ken Myer did), you can typically resolve the issue by engaging in a different modality.</span></span> <span data-ttu-id="131d3-130">Например, если вы отправляете мгновенное сообщение, в окне беседы отобразятся все участники Конференции, включая:</span><span class="sxs-lookup"><span data-stu-id="131d3-130">For example, if you send an instant message the conversation window will now show all the conference participants, including yourself:</span></span>

<span data-ttu-id="131d3-131">![Снимок экрана: окно беседы и список участников Lync](images/Dn383570.9b5ff6d6-9f73-467c-99a7-ef3aa8bd7e7a(OCS.15).png "Снимок экрана: окно беседы и список участников Lync")</span><span class="sxs-lookup"><span data-stu-id="131d3-131">![Lync conversation and participant list screenshot](images/Dn383570.9b5ff6d6-9f73-467c-99a7-ef3aa8bd7e7a(OCS.15).png "Lync conversation and participant list screenshot")</span></span>

<span data-ttu-id="131d3-132">На этом этапе вы должны сможете принимать участие в собрании в ожидаемом виде.</span><span class="sxs-lookup"><span data-stu-id="131d3-132">At this point you should be able to participate in the meeting in the expected fashion.</span></span>

<span data-ttu-id="131d3-133">Кроме того, вы можете вообще избежать этой проблемы, изменив способ присоединения к собранию.</span><span class="sxs-lookup"><span data-stu-id="131d3-133">Alternatively, you can avoid this issue altogether by changing the way you join the meeting.</span></span> <span data-ttu-id="131d3-134">Если вам нужно позвонить на сервер Lync Server, вы должны присоединиться к собранию, не используя голосовой телефонную связь.</span><span class="sxs-lookup"><span data-stu-id="131d3-134">If you need to have Lync Server call a Lync Server-enabled phone, you should begin by joining the meeting without an audio connection.</span></span> <span data-ttu-id="131d3-135">Для этого установите флажок не присоединять звук при отображении с помощью диалогового окна присоединиться к звуковому каналу собрания:</span><span class="sxs-lookup"><span data-stu-id="131d3-135">To do that, select Don’t join audio when presented with the Join Meeting Audio dialog box:</span></span>

<span data-ttu-id="131d3-136">![Снимок экрана: окно "не присоединиться к собранию звука"](images/Dn383570.280a148d-cce5-4b02-87f9-9f78f17a81c1(OCS.15).png "Снимок экрана: окно "не присоединиться к собранию звука"")</span><span class="sxs-lookup"><span data-stu-id="131d3-136">![Lync don't join meeting audio window screenshot](images/Dn383570.280a148d-cce5-4b02-87f9-9f78f17a81c1(OCS.15).png "Lync don't join meeting audio window screenshot")</span></span>

<span data-ttu-id="131d3-137">После того как вы успешно подключитесь к собранию, теперь вы можете "пригласить", чтобы присоединиться к собранию с помощью Lync Server.</span><span class="sxs-lookup"><span data-stu-id="131d3-137">After you have successfully connected to the meeting, you can now “invite” the Lync Server-enabled phone to join the meeting as well.</span></span> <span data-ttu-id="131d3-138">Для этого наведите указатель мыши на значок "люди", а затем выберите **пригласить других пользователей**:</span><span class="sxs-lookup"><span data-stu-id="131d3-138">To do that, place the mouse over the People icon and then click **Invite More People**:</span></span>

<span data-ttu-id="131d3-139">![Снимок экрана: окно "пригласить других участников" в Lync](images/Dn383570.69b81b29-d1d2-4ed3-acb6-e37dd18e3d86(OCS.15).png "Снимок экрана: окно "пригласить других участников" в Lync")</span><span class="sxs-lookup"><span data-stu-id="131d3-139">![Lync invite more participants window screenshot](images/Dn383570.69b81b29-d1d2-4ed3-acb6-e37dd18e3d86(OCS.15).png "Lync invite more participants window screenshot")</span></span>

<span data-ttu-id="131d3-140">Откроется диалоговое окно " **Отправить мгновенное** сообщение".</span><span class="sxs-lookup"><span data-stu-id="131d3-140">That will bring up the **Send an IM** dialog box.</span></span> <span data-ttu-id="131d3-141">Пропустите заголовок диалогового окна (вы не отправите мгновенное сообщение) и введите номер телефона, на котором разрешено Lync:</span><span class="sxs-lookup"><span data-stu-id="131d3-141">Ignore the dialog box title (you’re not actually sending an instant message) and type the phone number of the Lync-enabled phone:</span></span>

<span data-ttu-id="131d3-142">![Снимок экрана: диалоговое окно "Отправить мгновенное сообщение"](images/Dn383570.cd67a3f0-06d8-41ba-a808-c067f64bec9f(OCS.15).png "Снимок экрана: диалоговое окно "Отправить мгновенное сообщение"")</span><span class="sxs-lookup"><span data-stu-id="131d3-142">![Send an IM dialog box screenshot](images/Dn383570.cd67a3f0-06d8-41ba-a808-c067f64bec9f(OCS.15).png "Send an IM dialog box screenshot")</span></span>

<span data-ttu-id="131d3-143">После нажатия кнопки **ОК**сервер Lync будет вызывать номер, введенный в диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="131d3-143">After you click **OK**, Lync Server will call the number entered in the dialog box.</span></span> <span data-ttu-id="131d3-144">После установления подключения у вас будет возможность пользоваться всеми возможностями звука через телефон с поддержкой Lync, и вы сможете просматривать и взаимодействовать с полным фотособранием.</span><span class="sxs-lookup"><span data-stu-id="131d3-144">When the connection is made, you will have full audio capabilities through the Lync-enabled phone, and you will be able to see and interact with the full conference roster.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

