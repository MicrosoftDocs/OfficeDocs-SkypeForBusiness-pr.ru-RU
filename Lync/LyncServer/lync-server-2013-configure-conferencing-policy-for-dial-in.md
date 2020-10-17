---
title: 'Lync Server 2013: Настройка политики конференц-связи с телефонным подключением'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure conferencing policy for dial-in
ms:assetid: 9bf926d6-0248-4352-98c3-9c5a333debbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398810(v=OCS.15)
ms:contentKeyID: 48184979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c42084f2e5ed8acceb73b4f417d8205b78b4b56
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515716"
---
# <a name="configure-conferencing-policy-for-dial-in-in-lync-server-2013"></a><span data-ttu-id="d46f9-102">Настройка политики конференц-связи с телефонным подключением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d46f9-102">Configure conferencing policy for dial-in in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d46f9-103">_**Последнее изменение темы:** 2014-03-21_</span><span class="sxs-lookup"><span data-stu-id="d46f9-103">_**Topic Last Modified:** 2014-03-21_</span></span>

<span data-ttu-id="d46f9-p101">Политика конференц-связи — это настройка учетной записи пользователя, задающая возможности взаимодействия участников в конференц-связи. Политики конференц-связи можно создавать на уровне сайта и на уровне пользователя. Параметры политики конференц-связи охватывают многие аспекты планирования конференций и участия в них. Некоторые параметры политики конференц-связи поддерживают конференц-связь с телефонным подключением участников. При настройке конференц-связи с телефонным подключением необходимо проверить, установлены ли эти поля соответственно вашей организации, и при необходимости изменить их.</span><span class="sxs-lookup"><span data-stu-id="d46f9-p101">Conferencing policy is a user account setting that specifies the conferencing experience for participants. You can create conferencing policies with a site scope or a user scope. Conferencing policy settings encompass many aspects of conference scheduling and participation. Several conferencing policy settings support dial-in conferencing for participants. When you configure dial-in conferencing, you should verify that these fields are set appropriately for your organization, and modify them as necessary.</span></span>

<span data-ttu-id="d46f9-109">Проверьте следующие поля в политике конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="d46f9-109">Verify the following fields in your conferencing policy:</span></span>

  - <span data-ttu-id="d46f9-110">**Разрешить участникам приглашать анонимных пользователей**     Этот параметр позволяет организаторов участникам собрания приглашать анонимных (то есть не прошедших проверку подлинности) участников для собраний.</span><span class="sxs-lookup"><span data-stu-id="d46f9-110">**Allow participants to invite anonymous users**   This setting allows meeting organizers to invite anonymous (that is, unauthenticated) participants to meetings.</span></span> <span data-ttu-id="d46f9-111">Этот параметр не является обязательным для конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="d46f9-111">This setting is optional for dial-in conferencing.</span></span> <span data-ttu-id="d46f9-112">Он установлен по умолчанию в глобальной политике конференц-связи по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d46f9-112">This setting is selected by default in the default global conferencing policy.</span></span>

  - <span data-ttu-id="d46f9-113">**Включение Конференц**     -связи с телефонным подключением PSTN Этот параметр позволяет пользователям присоединяться к звуковой части конференции с помощью телефонного подключения через сеть PSTN.</span><span class="sxs-lookup"><span data-stu-id="d46f9-113">**Enable PSTN dial-in conferencing**   This setting allows users to join the audio portion of a conference by dialing in from the PSTN.</span></span> <span data-ttu-id="d46f9-114">Этот параметр необходим для конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="d46f9-114">This setting is required for dial-in conferencing.</span></span> <span data-ttu-id="d46f9-115">Он установлен по умолчанию в глобальной политике конференц-связи по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d46f9-115">This setting is selected by default in the default global conferencing policy.</span></span>

  - <span data-ttu-id="d46f9-116">**Разрешить исходящие звонки**     анонимным участникам Этот параметр разрешает анонимным пользователям, которые уже присоединены к собранию, подключаться к телефонному номеру, чтобы присоединиться к звуковой части Конференции.</span><span class="sxs-lookup"><span data-stu-id="d46f9-116">**Allow anonymous participants to dial out**   This setting allows anonymous users who are already joined to the meeting to dial out to a phone number to join the audio portion of the conference.</span></span> <span data-ttu-id="d46f9-117">Этот параметр является необязательным для конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="d46f9-117">This setting is optional for dial-in conferencing.</span></span> <span data-ttu-id="d46f9-118">Он не установлен по умолчанию в глобальной политике конференц-связи по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d46f9-118">This setting is not selected by default in the default global conferencing policy.</span></span>

  - <span data-ttu-id="d46f9-119">**Разрешить участникам, не включенным в корпоративную голосовую связь, исходящие звонки**     Этот параметр позволяет участникам собрания и организаторов, не поддерживающих корпоративную голосовую связь, подключаться к телефонному номеру, чтобы присоединиться к звуковой части Конференции.</span><span class="sxs-lookup"><span data-stu-id="d46f9-119">**Allow participants not enabled for Enterprise Voice to dial out**   This setting allows meeting participants and organizers that are not enabled for Enterprise Voice to dial out to a phone number to join the audio portion of the conference.</span></span> <span data-ttu-id="d46f9-120">Авторизация телефонного подключения осуществляется на основе политики голосовой связи, назначенной организатору.</span><span class="sxs-lookup"><span data-stu-id="d46f9-120">The dial-out call is authorized based on the organizer’s assigned voice policy.</span></span> <span data-ttu-id="d46f9-121">Этот параметр не установлен по умолчанию в глобальной политике конференц-связи по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d46f9-121">This setting is not selected by default in the default global conferencing policy.</span></span> <span data-ttu-id="d46f9-122">По умолчанию этот параметр отключен.</span><span class="sxs-lookup"><span data-stu-id="d46f9-122">The setting default value is disabled.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d46f9-123">Чтобы включить эту возможность, организатору собрания, для которого не включена поддержка корпоративной голосовой связи, должно быть назначена соответствующая политика голосовой связи для авторизации всех исходящих звонков из конференции, организованной этим пользователем.</span><span class="sxs-lookup"><span data-stu-id="d46f9-123">To enable this capability, a meeting organizer that is not enabled for Enterprise Voice should have an appropriate voice policy assigned to them to authorize any dial-out from a conference organized by that user.</span></span> <span data-ttu-id="d46f9-124">Политика голосовой связи может быть назначена пользователю, для которого не включена поддержка корпоративной голосовой связи, из командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d46f9-124">A voice policy can be assigned to a user that is not enabled for Enterprise Voice from the Lync Server Management Shell.</span></span> <span data-ttu-id="d46f9-125">Если пользователь не имеет явно назначенной политики голосовой связи, для авторизации запроса на удаленную связь будет использоваться политика голосовой связи для сайта.</span><span class="sxs-lookup"><span data-stu-id="d46f9-125">If the user does not have a voice policy explicitly assigned to him, the site voice policy will be used to authorize the dial-out request.</span></span> <span data-ttu-id="d46f9-126">Если политика голосовой связи для сайта отсутствует, будет использоваться глобальная политика голосовой связи.&nbsp;</span><span class="sxs-lookup"><span data-stu-id="d46f9-126">If there is no site voice policy, the global voice policy will be used.&nbsp;</span></span>

    
    </div>

<span data-ttu-id="d46f9-127">В процедуре, приведенной в данном разделе, описывается изменение политики конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="d46f9-127">The procedure in this section explains how to modify conferencing policy.</span></span> <span data-ttu-id="d46f9-128">Сведения о том, как настроить все параметры, определяющие интерфейс участника в политике конференц-связи по умолчанию, можно найти в статье [Создание или изменение коллекции параметров конфигурации собраний в Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).</span><span class="sxs-lookup"><span data-stu-id="d46f9-128">For details about how to configure all of the settings that define the participant experience in the default conferencing policy, see [Create or modify a collection of meeting configuration settings in Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).</span></span> <span data-ttu-id="d46f9-129">Сведения о том, как создать политику конференц-связи для определенного пользователя или группы пользователей, можно найти [в статье Создание или изменение политики конференц-связи в Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span><span class="sxs-lookup"><span data-stu-id="d46f9-129">For details about how to create a conferencing policy for a specific user or group of users, see [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span></span> <span data-ttu-id="d46f9-130">Список всех доступных параметров политики конференц-связи представлен в статье [сведения о параметрах политики конференц-связи для Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span><span class="sxs-lookup"><span data-stu-id="d46f9-130">For a list of all available conferencing policy settings, see [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span></span>

<div>

## <a name="to-modify-the-conferencing-policy-for-dial-in"></a><span data-ttu-id="d46f9-131">Изменение политики конференц-связи для телефонного подключения</span><span class="sxs-lookup"><span data-stu-id="d46f9-131">To modify the conferencing policy for dial-in</span></span>

1.  <span data-ttu-id="d46f9-132">Войдите в компьютер как член группы RTCUniversalServerAdmins или как член роли **Cs-ServerAdministrator** или **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="d46f9-132">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="d46f9-133">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d46f9-133">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d46f9-134">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d46f9-134">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d46f9-135">В левой панели навигации выберите пункт **Конференц-связь**.</span><span class="sxs-lookup"><span data-stu-id="d46f9-135">In the left navigation bar, click **Conferencing**.</span></span>

4.  <span data-ttu-id="d46f9-136">На вкладке **Политика конференц-связи** дважды щелкните имя политики конференц-связи, чтобы открыть диалоговое окно **изменения политики конференц-связи**.</span><span class="sxs-lookup"><span data-stu-id="d46f9-136">On the **Conferencing Policy** tab, double-click a conferencing policy name to open the **Edit Conferencing Policy** dialog box.</span></span>

5.  <span data-ttu-id="d46f9-137">Проверьте, подходят ли вашей организации значения в полях для конференц-связи с телефонным подключением, и при необходимости измените их.</span><span class="sxs-lookup"><span data-stu-id="d46f9-137">Verify that the fields for dial-in conferencing are appropriate for your organization, and modify the settings if necessary.</span></span>

6.  <span data-ttu-id="d46f9-138">Нажмите кнопку **Зафиксировать**.</span><span class="sxs-lookup"><span data-stu-id="d46f9-138">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

