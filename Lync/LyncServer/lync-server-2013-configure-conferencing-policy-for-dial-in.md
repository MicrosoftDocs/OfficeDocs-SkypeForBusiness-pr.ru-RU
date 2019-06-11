---
title: 'Lync Server 2013: настройка политики конференц-связи с телефонным подключением'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure conferencing policy for dial-in
ms:assetid: 9bf926d6-0248-4352-98c3-9c5a333debbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398810(v=OCS.15)
ms:contentKeyID: 48184979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74621fee97a1e6721f8772b265761b62b1b9f266
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841406"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-conferencing-policy-for-dial-in-in-lync-server-2013"></a><span data-ttu-id="eca86-102">Настройка политики конференц-связи с телефонным подключением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eca86-102">Configure conferencing policy for dial-in in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eca86-103">_**Тема последнего изменения:** 2014-03-21_</span><span class="sxs-lookup"><span data-stu-id="eca86-103">_**Topic Last Modified:** 2014-03-21_</span></span>

<span data-ttu-id="eca86-p101">Политика конференц-связи – это настройка учетной записи пользователя, задающая возможности взаимодействия участников в конференц-связи. Политики конференц-связи можно создавать на уровне сайта и на уровне пользователя. Параметры политики конференц-связи охватывают многие аспекты планирования конференций и участия в них. Некоторые параметры политики конференц-связи поддерживают конференц-связь с телефонным подключением участников. При настройке конференц-связи с телефонным подключением необходимо проверить, установлены ли эти поля соответственно вашей организации, и при необходимости изменить их.</span><span class="sxs-lookup"><span data-stu-id="eca86-p101">Conferencing policy is a user account setting that specifies the conferencing experience for participants. You can create conferencing policies with a site scope or a user scope. Conferencing policy settings encompass many aspects of conference scheduling and participation. Several conferencing policy settings support dial-in conferencing for participants. When you configure dial-in conferencing, you should verify that these fields are set appropriately for your organization, and modify them as necessary.</span></span>

<span data-ttu-id="eca86-109">Убедитесь в том, что в политике конференц-связи указаны следующие поля:</span><span class="sxs-lookup"><span data-stu-id="eca86-109">Verify the following fields in your conferencing policy:</span></span>

  - <span data-ttu-id="eca86-110">**Разрешить участникам приглашать анонимных пользователей**   . Этот параметр позволяет организаторов собраний получать анонимные участники (то есть участников, не прошедших проверку подлинности) на собрания.</span><span class="sxs-lookup"><span data-stu-id="eca86-110">**Allow participants to invite anonymous users**   This setting allows meeting organizers to invite anonymous (that is, unauthenticated) participants to meetings.</span></span> <span data-ttu-id="eca86-111">Этот параметр необязателен для конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="eca86-111">This setting is optional for dial-in conferencing.</span></span> <span data-ttu-id="eca86-112">Этот параметр выбран по умолчанию в глобальной политике конференц-связи по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="eca86-112">This setting is selected by default in the default global conferencing policy.</span></span>

  - <span data-ttu-id="eca86-113">**Включить Конференц**   -связь с телефонным подключением по PSTN этот параметр позволяет пользователям присоединиться к звуковой части конференции с помощью телефонного подключения через сеть PSTN.</span><span class="sxs-lookup"><span data-stu-id="eca86-113">**Enable PSTN dial-in conferencing**   This setting allows users to join the audio portion of a conference by dialing in from the PSTN.</span></span> <span data-ttu-id="eca86-114">Этот параметр требуется для конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="eca86-114">This setting is required for dial-in conferencing.</span></span> <span data-ttu-id="eca86-115">Этот параметр выбран по умолчанию в глобальной политике конференц-связи по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="eca86-115">This setting is selected by default in the default global conferencing policy.</span></span>

  - <span data-ttu-id="eca86-116">**Разрешить анонимным участникам Звонок**   . Этот параметр позволяет анонимным пользователям, которые уже присоединены к собранию, звонить на телефонные номера для присоединения к звуковому разделу Конференции.</span><span class="sxs-lookup"><span data-stu-id="eca86-116">**Allow anonymous participants to dial out**   This setting allows anonymous users who are already joined to the meeting to dial out to a phone number to join the audio portion of the conference.</span></span> <span data-ttu-id="eca86-117">Этот параметр необязателен для конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="eca86-117">This setting is optional for dial-in conferencing.</span></span> <span data-ttu-id="eca86-118">Этот параметр не выбран по умолчанию в глобальной политике конференц-связи по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="eca86-118">This setting is not selected by default in the default global conferencing policy.</span></span>

  - <span data-ttu-id="eca86-119">**Разрешить участникам, не поддерживающим корпоративную голосовую**   связь. Этот параметр позволяет участникам собрания и организаторов, не поддерживающим корпоративную голосовую почту, звонить на телефонные номера, чтобы присоединиться к звуковой части Конференции.</span><span class="sxs-lookup"><span data-stu-id="eca86-119">**Allow participants not enabled for Enterprise Voice to dial out**   This setting allows meeting participants and organizers that are not enabled for Enterprise Voice to dial out to a phone number to join the audio portion of the conference.</span></span> <span data-ttu-id="eca86-120">Вызов по исходящим звонкам разрешен на основе назначенной политики голосовой связи организатора.</span><span class="sxs-lookup"><span data-stu-id="eca86-120">The dial-out call is authorized based on the organizer’s assigned voice policy.</span></span> <span data-ttu-id="eca86-121">Этот параметр не выбран по умолчанию в глобальной политике конференц-связи по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="eca86-121">This setting is not selected by default in the default global conferencing policy.</span></span> <span data-ttu-id="eca86-122">Значение параметра по умолчанию — Disabled (отключить).</span><span class="sxs-lookup"><span data-stu-id="eca86-122">The setting default value is disabled.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="eca86-123">Чтобы включить эту возможность, организатору собрания, недоступному для корпоративной голосовой почты, должна быть назначена соответствующая политика голосовой связи для авторизации подключения с конференции, организованной этим пользователем.</span><span class="sxs-lookup"><span data-stu-id="eca86-123">To enable this capability, a meeting organizer that is not enabled for Enterprise Voice should have an appropriate voice policy assigned to them to authorize any dial-out from a conference organized by that user.</span></span> <span data-ttu-id="eca86-124">Политике голосовой связи может быть назначен пользователь, не поддерживающий корпоративный голосовой интерфейс из командной консоли Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="eca86-124">A voice policy can be assigned to a user that is not enabled for Enterprise Voice from the Lync Server Management Shell.</span></span> <span data-ttu-id="eca86-125">Если пользователю не назначена политика голосовой связи, она будет использоваться для авторизации запроса на исходящие звонки.</span><span class="sxs-lookup"><span data-stu-id="eca86-125">If the user does not have a voice policy explicitly assigned to him, the site voice policy will be used to authorize the dial-out request.</span></span> <span data-ttu-id="eca86-126">Если у вас нет политики голосовой связи сайта, будет использоваться глобальная политика голосовой связи.&nbsp;</span><span class="sxs-lookup"><span data-stu-id="eca86-126">If there is no site voice policy, the global voice policy will be used.&nbsp;</span></span>

    
    </div>

<span data-ttu-id="eca86-127">В этом разделе описана процедура изменения политики конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="eca86-127">The procedure in this section explains how to modify conferencing policy.</span></span> <span data-ttu-id="eca86-128">Дополнительные сведения о том, как настроить все параметры участника в политике конференц-связи по умолчанию, можно найти [в разделе Создание или изменение коллекции параметров конфигурации собраний в Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).</span><span class="sxs-lookup"><span data-stu-id="eca86-128">For details about how to configure all of the settings that define the participant experience in the default conferencing policy, see [Create or modify a collection of meeting configuration settings in Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).</span></span> <span data-ttu-id="eca86-129">Сведения о том, как создать политику конференций для определенного пользователя или группы пользователей, можно найти в разделе [Создание и изменение политики конференц-связи в Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span><span class="sxs-lookup"><span data-stu-id="eca86-129">For details about how to create a conferencing policy for a specific user or group of users, see [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span></span> <span data-ttu-id="eca86-130">Список всех доступных параметров политики конференций приведен в [справочнике параметры политики конференц-связи для Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span><span class="sxs-lookup"><span data-stu-id="eca86-130">For a list of all available conferencing policy settings, see [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span></span>

<div>

## <a name="to-modify-the-conferencing-policy-for-dial-in"></a><span data-ttu-id="eca86-131">Изменение политики конференц-связи с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="eca86-131">To modify the conferencing policy for dial-in</span></span>

1.  <span data-ttu-id="eca86-132">Войдите в систему под учетной записью члена группы Рткуниверсалсерверадминс или члена роли **CS-серверадминистратор** или **ксадминистратор** .</span><span class="sxs-lookup"><span data-stu-id="eca86-132">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="eca86-133">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="eca86-133">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="eca86-134">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="eca86-134">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="eca86-135">На левой панели навигации щелкните элемент **Конференция**.</span><span class="sxs-lookup"><span data-stu-id="eca86-135">In the left navigation bar, click **Conferencing**.</span></span>

4.  <span data-ttu-id="eca86-136">На вкладке **Политика конференций** дважды щелкните имя политики конференц-связи, чтобы открыть диалоговое окно **изменение политики Конференц** -связи.</span><span class="sxs-lookup"><span data-stu-id="eca86-136">On the **Conferencing Policy** tab, double-click a conferencing policy name to open the **Edit Conferencing Policy** dialog box.</span></span>

5.  <span data-ttu-id="eca86-137">Убедитесь в том, что поля для конференц-связи с телефонным подключением подходят для вашей организации, и при необходимости измените параметры.</span><span class="sxs-lookup"><span data-stu-id="eca86-137">Verify that the fields for dial-in conferencing are appropriate for your organization, and modify the settings if necessary.</span></span>

6.  <span data-ttu-id="eca86-138">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="eca86-138">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

