---
title: 'Lync Server 2013: использование функции "позвонить мне" с телефонным телефоном с поддержкой Lync'
description: 'Lync Server 2013: использование телефонного звонка с поддержкой Lync.'
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
ms.openlocfilehash: 7fd7855e45132b133c78230e7f8769bdab897140
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580425"
---
# <a name="using-call-me-at-with-a-lync-enabled-phone-and-lync-server-2013"></a><span data-ttu-id="d2377-103">Использование функции "позвонить мне" с телефонами с поддержкой Lync и Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2377-103">Using Call Me At with a Lync-enabled phone and Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2377-104">_**Последнее изменение темы:** 2013-08-09_</span><span class="sxs-lookup"><span data-stu-id="d2377-104">_**Topic Last Modified:** 2013-08-09_</span></span>

<span data-ttu-id="d2377-105">Функция "позвонить мне с помощью Lync" позволяет пользователям присоединяться к звуковой части конференции с помощью сотового телефона, "Land Line" или другого устройства, подключенного к телефонной сети общего пользования (PSTN).</span><span class="sxs-lookup"><span data-stu-id="d2377-105">The Call Me At feature in Lync provides a way for users to join the audio portion of a conference by using a cell phone, “land line,” or other device connected to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="d2377-106">При попытке присоединения к собранию с помощью Lync в диалоговом окне "присоединение к собранию" обычно отображается диалоговое окно " **Присоединение к собранию** ":</span><span class="sxs-lookup"><span data-stu-id="d2377-106">When you attempt to join a meeting by using Lync, you will typically be presented with the **Join Meeting Audio** dialog box:</span></span>

<span data-ttu-id="d2377-107">![Использование Lync для присоединения к снимку экрана с окном "звук собрания"](images/Dn383570.e28f17f0-9f17-44ef-b893-f4ef132f47ac(OCS.15).png "Использование Lync для присоединения к снимку экрана с окном "звук собрания"")</span><span class="sxs-lookup"><span data-stu-id="d2377-107">![Use Lync to join meeting audio window screenshot](images/Dn383570.e28f17f0-9f17-44ef-b893-f4ef132f47ac(OCS.15).png "Use Lync to join meeting audio window screenshot")</span></span>

<span data-ttu-id="d2377-108">Если вы выберете параметр **позвонить мне**, вы можете выбрать номер телефона из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="d2377-108">If you select **Call me at**, you can then pick a phone number from the dropdown list.</span></span> <span data-ttu-id="d2377-109">Lync Server 2013 поместит телефонный звонок на выбранный номер, а затем вы можете использовать этот телефон для участия в звуковой части Конференции.</span><span class="sxs-lookup"><span data-stu-id="d2377-109">Lync Server 2013 will place a phone call to the selected number, and you can then use that phone to participate in the audio portion of the conference.</span></span>

<span data-ttu-id="d2377-110">Раскрывающийся список заполняется номерами телефонов, которые вы ввели на вкладке Телефоны в диалоговом окне **Lync — Options** (мобильный телефон, домашний телефон или другой телефон), который вы ввели на вкладке **телефоны** :</span><span class="sxs-lookup"><span data-stu-id="d2377-110">The dropdown list is populated by the phone numbers (for mobile phone, home phone, or other phone) that you have entered on the **Phones** tab in the **Lync – Options** dialog box:</span></span>

<span data-ttu-id="d2377-111">![Снимок экрана настройки телефонов Lync](images/Dn383570.03d2f25d-49e2-47b4-b1e9-b1614fc0c11c(OCS.15).png "Снимок экрана настройки телефонов Lync")</span><span class="sxs-lookup"><span data-stu-id="d2377-111">![Lync Phones set up options screenshot](images/Dn383570.03d2f25d-49e2-47b4-b1e9-b1614fc0c11c(OCS.15).png "Lync Phones set up options screenshot")</span></span>

<span data-ttu-id="d2377-112">Если вы не ввели номера телефонов на вкладке **телефоны** , в раскрывающемся списке нет доступных номеров.</span><span class="sxs-lookup"><span data-stu-id="d2377-112">If you have not entered any phone numbers on the **Phones** tab then you will not have any numbers available in the dropdown box.</span></span> <span data-ttu-id="d2377-113">Тем не менее, всегда можно выбрать **новый номер** и исходящие звонки Lync Server на любой номер телефона, который вы хотите:</span><span class="sxs-lookup"><span data-stu-id="d2377-113">However, you can always click **New Number** and have Lync Server dial out to any phone number you wish:</span></span>

<span data-ttu-id="d2377-114">![Снимок экрана: присоединение к собранию голосового звонка в Lync](images/Dn383570.27f2ac7a-cc1c-465c-b145-202ad03af4f2(OCS.15).png "Снимок экрана: присоединение к собранию голосового звонка в Lync")</span><span class="sxs-lookup"><span data-stu-id="d2377-114">![Lync join meeting audio call me window screenshot](images/Dn383570.27f2ac7a-cc1c-465c-b145-202ad03af4f2(OCS.15).png "Lync join meeting audio call me window screenshot")</span></span>

<span data-ttu-id="d2377-115">Функция "позвонить мне" очень хорошо подходит для использования в том виде, в котором она предназначена для того, чтобы Lync Server вызывал телефонный номер PSTN.</span><span class="sxs-lookup"><span data-stu-id="d2377-115">The Call Me At feature works extremely well provided that you use it in the way it was intended: by having Lync Server call a PSTN phone number.</span></span> <span data-ttu-id="d2377-116">Тем не менее, если вы запрашиваете у Lync Server вызов на конечной точке с поддержкой Lync (например, на телефоне в конференц-зале), вы можете работать с неоптимальным интерфейсом.</span><span class="sxs-lookup"><span data-stu-id="d2377-116">However, you can run into a less-than-optimal experience if you ask Lync Server to call you at a Lync-enabled endpoint (for example, a phone in a conference room).</span></span> <span data-ttu-id="d2377-117">Ниже приведена проблема, с которой вы можете столкнуться, а также два способа обхода этой проблемы.</span><span class="sxs-lookup"><span data-stu-id="d2377-117">Following is the issue you might run into, as well as two ways to work around the problem.</span></span>

<span data-ttu-id="d2377-118">Для начала, что происходит, когда вы предоставляете функцию "позвонить мне" с номером телефона телефона с поддержкой Lync.</span><span class="sxs-lookup"><span data-stu-id="d2377-118">To begin, here’s what happens when you provide the Call Me At feature with the phone number of a Lync-enabled phone.</span></span> <span data-ttu-id="d2377-119">Предположим, что Кен Myer пытается присоединиться к собранию, выполнив вызов Lync Server для пользователя по телефону 1-206-555-1219, с поддержкой Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d2377-119">Suppose Ken Myer tries to join a meeting by having Lync Server call him at 1-206-555-1219, a Lync Server-enabled phone number.</span></span> <span data-ttu-id="d2377-120">Ken сначала подключается к собранию, но после нескольких секунд, когда Lync отображает сообщение **не было завершено или закончилось**, а Кен будет удален из собрания:</span><span class="sxs-lookup"><span data-stu-id="d2377-120">Ken will initially be connected to the meeting, but after a few seconds Lync will display the message **Call was not completed or has ended**, and Ken will appear to have been dropped from the meeting:</span></span>

<span data-ttu-id="d2377-121">![Снимок экрана с окном конференц-связи Lync](images/Dn383570.c2a81727-8751-41b5-946a-03a1b75b9d95(OCS.15).png "Снимок экрана с окном конференц-связи Lync")</span><span class="sxs-lookup"><span data-stu-id="d2377-121">![Screen shot of Lync call conferencing window](images/Dn383570.c2a81727-8751-41b5-946a-03a1b75b9d95(OCS.15).png "Screen shot of Lync call conferencing window")</span></span>

<span data-ttu-id="d2377-122">Однако обратите внимание, что в окне беседы Lync есть несоответствие.</span><span class="sxs-lookup"><span data-stu-id="d2377-122">Notice, however, that there is a discrepancy within the Lync conversation window.</span></span> <span data-ttu-id="d2377-123">Кен Myer это единственное имя, указанное в разделе **Участники** .</span><span class="sxs-lookup"><span data-stu-id="d2377-123">Ken Myer is the only name listed under the **Participants** heading.</span></span> <span data-ttu-id="d2377-124">Тем не менее, если взглянуть на строку заголовка окна, вы увидите, что Конференция содержит всего четыре участника.</span><span class="sxs-lookup"><span data-stu-id="d2377-124">However, if you look in the title bar of the window, you’ll see that the conference contains a total of 4 participants.</span></span>

<span data-ttu-id="d2377-125">Аналогично, при просмотре беседы в окне беседы любого из других участников конференции Ken Myer не будет отображаться в любом месте:</span><span class="sxs-lookup"><span data-stu-id="d2377-125">Likewise, if you look in the conversation window of any of the other conference participants you will not see Ken Myer listed anywhere:</span></span>

<span data-ttu-id="d2377-126">![Снимок экрана с окном списка участников Lync](images/Dn383570.fa5990cf-2694-402c-ac06-946aa66b6837(OCS.15).png "Снимок экрана с окном списка участников Lync")</span><span class="sxs-lookup"><span data-stu-id="d2377-126">![Lync participant list window screenshot](images/Dn383570.fa5990cf-2694-402c-ac06-946aa66b6837(OCS.15).png "Lync participant list window screenshot")</span></span>

<span data-ttu-id="d2377-127">Но в то же время, Ken Myer будет иметь возможность участвовать в звуковой части звонка с помощью телефона с поддержкой Lync.</span><span class="sxs-lookup"><span data-stu-id="d2377-127">And yet, at the same time, Ken Myer will be able to participate in the audio portion of the call by using his Lync-enabled phone.</span></span> <span data-ttu-id="d2377-128">Функция "позвонить мне" на самом деле работала, но взаимодействие с пользователем не является оптимальным.</span><span class="sxs-lookup"><span data-stu-id="d2377-128">The Call Me At feature has actually worked, but the user experience is less than optimal.</span></span>

<span data-ttu-id="d2377-129">Существует по крайней мере два способа обойти эту проблему.</span><span class="sxs-lookup"><span data-stu-id="d2377-129">There are at least two ways to work around this problem.</span></span> <span data-ttu-id="d2377-130">Если вы уже присоединились к Конференции (например, Ken Myer), вы обычно можете решить эту проблему, выполнив различные модальности.</span><span class="sxs-lookup"><span data-stu-id="d2377-130">If you have already joined a conference in this fashion (like Ken Myer did), you can typically resolve the issue by engaging in a different modality.</span></span> <span data-ttu-id="d2377-131">Например, если вы отправляете мгновенное сообщение, в окне беседы будут отображаться все участники Конференции, включая себя:</span><span class="sxs-lookup"><span data-stu-id="d2377-131">For example, if you send an instant message the conversation window will now show all the conference participants, including yourself:</span></span>

<span data-ttu-id="d2377-132">![Снимок экрана: Беседа и список участников Lync](images/Dn383570.9b5ff6d6-9f73-467c-99a7-ef3aa8bd7e7a(OCS.15).png "Снимок экрана: Беседа и список участников Lync")</span><span class="sxs-lookup"><span data-stu-id="d2377-132">![Lync conversation and participant list screenshot](images/Dn383570.9b5ff6d6-9f73-467c-99a7-ef3aa8bd7e7a(OCS.15).png "Lync conversation and participant list screenshot")</span></span>

<span data-ttu-id="d2377-133">На этом шаге вы должны иметь возможность участвовать в собрании в ожидаемом порядке.</span><span class="sxs-lookup"><span data-stu-id="d2377-133">At this point you should be able to participate in the meeting in the expected fashion.</span></span>

<span data-ttu-id="d2377-134">Кроме того, можно полностью устранить эту ошибку, изменив способ присоединения к собранию.</span><span class="sxs-lookup"><span data-stu-id="d2377-134">Alternatively, you can avoid this issue altogether by changing the way you join the meeting.</span></span> <span data-ttu-id="d2377-135">Если вам необходим вызов Lync Server для телефонного телефона с поддержкой Lync Server, начните с присоединения к собранию без подключения к звуковому каналу.</span><span class="sxs-lookup"><span data-stu-id="d2377-135">If you need to have Lync Server call a Lync Server-enabled phone, you should begin by joining the meeting without an audio connection.</span></span> <span data-ttu-id="d2377-136">Чтобы сделать это, установите флажок не присоединять звук при работе с диалоговым окном присоединения к аудио:</span><span class="sxs-lookup"><span data-stu-id="d2377-136">To do that, select Don’t join audio when presented with the Join Meeting Audio dialog box:</span></span>

<span data-ttu-id="d2377-137">![Lync не присоединиться к снимку окна "звук собрания"](images/Dn383570.280a148d-cce5-4b02-87f9-9f78f17a81c1(OCS.15).png "Lync не присоединиться к снимку окна "звук собрания"")</span><span class="sxs-lookup"><span data-stu-id="d2377-137">![Lync don't join meeting audio window screenshot](images/Dn383570.280a148d-cce5-4b02-87f9-9f78f17a81c1(OCS.15).png "Lync don't join meeting audio window screenshot")</span></span>

<span data-ttu-id="d2377-138">После успешного подключения к собранию вы можете присоединиться к собранию с помощью телефонного телефона с поддержкой Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d2377-138">After you have successfully connected to the meeting, you can now “invite” the Lync Server-enabled phone to join the meeting as well.</span></span> <span data-ttu-id="d2377-139">Для этого наведите указатель мыши на значок люди, а затем щелкните **пригласить других людей**:</span><span class="sxs-lookup"><span data-stu-id="d2377-139">To do that, place the mouse over the People icon and then click **Invite More People**:</span></span>

<span data-ttu-id="d2377-140">![Снимок экрана с окном приглашенных участников Lync](images/Dn383570.69b81b29-d1d2-4ed3-acb6-e37dd18e3d86(OCS.15).png "Снимок экрана с окном приглашенных участников Lync")</span><span class="sxs-lookup"><span data-stu-id="d2377-140">![Lync invite more participants window screenshot](images/Dn383570.69b81b29-d1d2-4ed3-acb6-e37dd18e3d86(OCS.15).png "Lync invite more participants window screenshot")</span></span>

<span data-ttu-id="d2377-141">Откроется диалоговое окно **Отправка мгновенных сообщений** .</span><span class="sxs-lookup"><span data-stu-id="d2377-141">That will bring up the **Send an IM** dialog box.</span></span> <span data-ttu-id="d2377-142">Проигнорируйте заголовок диалогового окна (вы не отправляете мгновенное сообщение) и вводите номер телефона для телефонного телефона с поддержкой Lync:</span><span class="sxs-lookup"><span data-stu-id="d2377-142">Ignore the dialog box title (you’re not actually sending an instant message) and type the phone number of the Lync-enabled phone:</span></span>

<span data-ttu-id="d2377-143">![Снимок экрана диалогового окна "Отправка мгновенных сообщений"](images/Dn383570.cd67a3f0-06d8-41ba-a808-c067f64bec9f(OCS.15).png "Снимок экрана диалогового окна "Отправка мгновенных сообщений"")</span><span class="sxs-lookup"><span data-stu-id="d2377-143">![Send an IM dialog box screenshot](images/Dn383570.cd67a3f0-06d8-41ba-a808-c067f64bec9f(OCS.15).png "Send an IM dialog box screenshot")</span></span>

<span data-ttu-id="d2377-144">После нажатия кнопки **ОК**сервер Lync Server вызовет номер, введенный в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="d2377-144">After you click **OK**, Lync Server will call the number entered in the dialog box.</span></span> <span data-ttu-id="d2377-145">Когда подключение будет установлено, вы сможете использовать все возможности работы со звуком с помощью телефона с поддержкой Lync, и вы сможете просмотреть полный список конференций и взаимодействовать с ним.</span><span class="sxs-lookup"><span data-stu-id="d2377-145">When the connection is made, you will have full audio capabilities through the Lync-enabled phone, and you will be able to see and interact with the full conference roster.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

