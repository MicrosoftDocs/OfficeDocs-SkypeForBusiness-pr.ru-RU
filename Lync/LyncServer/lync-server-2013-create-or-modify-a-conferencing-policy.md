---
title: 'Lync Server 2013: создание или изменение политики конференц-связи'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a conferencing policy
ms:assetid: e2974030-2c0a-4634-91e8-93f4e2d674d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721910(v=OCS.15)
ms:contentKeyID: 49733844
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f3dd712b94838382f6022de888383c0f47bee6e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758093"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-conferencing-policy-in-lync-server-2013"></a><span data-ttu-id="79853-102">Создание и изменение политики конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79853-102">Create or modify a conferencing policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79853-103">_**Тема последнего изменения:** 2013-02-07_</span><span class="sxs-lookup"><span data-stu-id="79853-103">_**Topic Last Modified:** 2013-02-07_</span></span>

<span data-ttu-id="79853-104">Выполните эти действия, чтобы создать политику конференц-связи на уровне пользователя или сайта.</span><span class="sxs-lookup"><span data-stu-id="79853-104">Follow these steps to create a user-level or a site-level conferencing policy.</span></span> <span data-ttu-id="79853-105">Сведения о назначении пользователю политики на уровне пользователей можно найти [в разделе Назначение политики конференций для пользователей в Lync Server 2013](lync-server-2013-assign-a-per-user-conferencing-policy.md).</span><span class="sxs-lookup"><span data-stu-id="79853-105">For details about how to assign a user-level policy to a user, see [Assign a per-user conferencing policy in Lync Server 2013](lync-server-2013-assign-a-per-user-conferencing-policy.md).</span></span> <span data-ttu-id="79853-106">Список всех доступных параметров политики конференций приведен в [справочнике параметры политики конференц-связи для Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span><span class="sxs-lookup"><span data-stu-id="79853-106">For a list of all available conferencing policy settings, see [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span></span>

<div>

## <a name="to-create-a-new-user-or-site-policy"></a><span data-ttu-id="79853-107">Создание политики для нового пользователя или сайта</span><span class="sxs-lookup"><span data-stu-id="79853-107">To create a new user or site policy</span></span>

1.  <span data-ttu-id="79853-108">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="79853-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="79853-109">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="79853-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="79853-110">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="79853-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="79853-111">На панели навигации слева выберите **Конференц** -связь, а затем — **Политика Конференц**-связи.</span><span class="sxs-lookup"><span data-stu-id="79853-111">In the left navigation bar, click **Conferencing** and then click **Conferencing Policy**.</span></span>

4.  <span data-ttu-id="79853-112">Нажмите кнопку **Создать**, а затем выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="79853-112">Click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="79853-p103">Для создания политики на уровне пользователя щелкните **Политика пользователя**. В окне **Создание политики пользователя** в поле **Имя** введите имя политики.</span><span class="sxs-lookup"><span data-stu-id="79853-p103">To create a user-level policy, click **User policy**. In **New Conferencing Policy**, in **Name**, type a descriptive name for the policy.</span></span>
    
      - <span data-ttu-id="79853-p104">Чтобы создать политику уровня сайта, выберите вариант **Политика сайта**. В поле поиска **Выбор сайта** введите часть или полное имя сайта, для которого требуется создать политику. В списке сайтов выберите нужный сайт и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="79853-p104">To create a site-level policy, click **Site policy**. In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy. In the list of sites, click the site that you want, and then click **OK**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="79853-118">Имя сайта становится именем политики конференций и не может быть изменено.</span><span class="sxs-lookup"><span data-stu-id="79853-118">The site name becomes the conferencing policy name, and it cannot be changed.</span></span>

        
        </div>

5.  <span data-ttu-id="79853-119">В поле **Описание** введите описание политики.</span><span class="sxs-lookup"><span data-stu-id="79853-119">In **Description**, type a description for the policy.</span></span>

6.  <span data-ttu-id="79853-p105">В разделе **Политика организатора** в поле **Максимальный размер собрания** введите максимальное допустимое число пользователей собрания. Значение по умолчанию — 250.</span><span class="sxs-lookup"><span data-stu-id="79853-p105">Under **Organizer policy**, in **Maximum meeting size**, type the maximum number of users that you want to allow at a meeting. By default, the maximum meeting size is 250.</span></span>

7.  <span data-ttu-id="79853-122">To prevent users from inviting anonymous users to meetings, clear the **Allow participants to invite anonymous users** check box.</span><span class="sxs-lookup"><span data-stu-id="79853-122">To prevent users from inviting anonymous users to meetings, clear the **Allow participants to invite anonymous users** check box.</span></span> <span data-ttu-id="79853-123">Анонимные пользователи — это пользователи, у которых нет учетных данных в доменных службах Active Directory вашей организации и которые, следовательно, не прошли проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="79853-123">Anonymous users are users who do not have credentials in your organization’s Active Directory Domain Services and who, therefore, are not authenticated.</span></span> <span data-ttu-id="79853-124">By default, users can invite anonymous users to meetings.</span><span class="sxs-lookup"><span data-stu-id="79853-124">By default, users can invite anonymous users to meetings.</span></span>

8.  <span data-ttu-id="79853-125">В окне **Запись** выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="79853-125">In **Recording**, do one of the following:</span></span>
    
      - <span data-ttu-id="79853-p107">Чтобы запретить участникам записывать собрания, щелкните **Нет**. Это параметр по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="79853-p107">To prevent participants from recording meetings, click **None**. This is the default setting.</span></span>
    
      - <span data-ttu-id="79853-128">Чтобы разрешить участникам записывать собрания, щелкните **Включить запись**.</span><span class="sxs-lookup"><span data-stu-id="79853-128">To allow participants to record meetings, click **Enable recording**.</span></span>

9.  <span data-ttu-id="79853-p108">Чтобы разрешить внешним участникам записывать собрания, установите флажок **Разрешить федеративным и анонимным участникам запись**. Значение по умолчанию — запретить внешним участникам записывать собрания.</span><span class="sxs-lookup"><span data-stu-id="79853-p108">To allow external participants to record meetings, select the **Allow federated and anonymous participants to record** check box. The default is to prevent external participants from recording meetings.</span></span>

10. <span data-ttu-id="79853-131">В окне **Аудио и видео** выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="79853-131">In **Audio/video**, do one of the following:</span></span>
    
      - <span data-ttu-id="79853-132">Чтобы запретить использование аудио и видео, щелкните **Нет**.</span><span class="sxs-lookup"><span data-stu-id="79853-132">To prevent the use of audio and video, click **None**.</span></span>
    
      - <span data-ttu-id="79853-133">Чтобы разрешить использование аудио, но не видео, щелкните **Включить IP-аудио**.</span><span class="sxs-lookup"><span data-stu-id="79853-133">To allow the use of audio but not video, click **Enable IP audio**.</span></span>
    
      - <span data-ttu-id="79853-p109">Чтобы разрешить использование аудио и видео, щелкните **Включить IP-аудио и видео**. Это параметр по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="79853-p109">To allow the use of audio and video, click **Enable IP audio/video**. This is the default setting.</span></span>

11. <span data-ttu-id="79853-136">Если вы разрешили использование аудио в окне **Аудио и видео**, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="79853-136">If you chose to allow the use of audio in **Audio/video**, do the following:</span></span>
    
      - <span data-ttu-id="79853-p110">Чтобы запретить пользователям присоединяться к собранию по телефонной связи, снимите флажок **Включить конференц-связь с телефонным подключением ТСОП**. По умолчанию пользователи могут подключиться к собраниям с ТСОП.</span><span class="sxs-lookup"><span data-stu-id="79853-p110">To prevent users from joining the meeting by dialing in, clear the **Enable PSTN dial-in conferencing** check box. By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>
    
      - <span data-ttu-id="79853-p111">Если вы разрешили пользователям подключаться к собраниям по телефонной связи и хотите анонимным пользователям присоединяться к собранию с помощью обратного звонка, установите флажок **Разрешить анонимным участникам обратный звонок**. При использовании обратных звонков сервер конференций вызывает пользователя, который отвечает на звонок, чтобы присоединиться к собранию. По умолчанию анонимные пользователи не могут присоединиться к собранию с помощью подключения обратным звонком.</span><span class="sxs-lookup"><span data-stu-id="79853-p111">If you allow users to dial in to meetings and you want to allow unauthenticated (anonymous) users to join a meeting by using dial out phoning, select the **Allow anonymous participants to dial out** check box. With dial-out phoning, the conference server calls the user, and the user answers the phone to join the meeting. By default, anonymous users cannot join a meeting by using dial-out phoning.</span></span>

12. <span data-ttu-id="79853-142">Если вы решили разрешить использование видео в **аудио-или видеоролике**, установите флажок **Разрешить несколько видеопотоков** .</span><span class="sxs-lookup"><span data-stu-id="79853-142">If you chose to allow the use of video in **Audio/video**, check **Allow multiple video streams** .</span></span>

13. <span data-ttu-id="79853-143">В окне **Совместная работа с данными** выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="79853-143">In **Data collaboration**, do one of the following:</span></span>
    
      - <span data-ttu-id="79853-144">Чтобы запретить совместную работу с данными, щелкните **Нет**.</span><span class="sxs-lookup"><span data-stu-id="79853-144">To prevent data collaboration, click **None**.</span></span>
    
      - <span data-ttu-id="79853-p112">Чтобы разрешить совместную работу с данными, щелкните **Включить совместную работу с данными**. Это параметр по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="79853-p112">To allow data collaboration, click **Enable data collaboration**. This is the default setting.</span></span>

14. <span data-ttu-id="79853-147">Если вы разрешили совместную работу с данными в окне **Совместная работа с данными**, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="79853-147">If you chose to allow data collaboration in **Data collaboration**, do the following:</span></span>
    
      - <span data-ttu-id="79853-p113">Чтобы запретить внешние загрузки, снимите флажок **Разрешить федеративным и анонимным участникам загружать контент**.</span><span class="sxs-lookup"><span data-stu-id="79853-p113">To prevent external downloads, clear the **Allow federated and anonymous participants to download content** check box. By default, external users can download content.</span></span>
    
      - <span data-ttu-id="79853-p114">Чтобы запретить передачу файлов, снимите флажок **Разрешить участникам передавать файлы**.</span><span class="sxs-lookup"><span data-stu-id="79853-p114">To prevent file transfers, clear the **Allow participants to transfer files** check box. By default, users can transfer files.</span></span>
    
      - <span data-ttu-id="79853-152">Чтобы запретить использование заметок, снимите флажок **Включить заметки**.</span><span class="sxs-lookup"><span data-stu-id="79853-152">To prevent the use of annotations, clear the **Enable annotations** check box.</span></span> <span data-ttu-id="79853-153">Для использования примечаний в презентациях для сегмента PowerPoint снимите флажок **включить примечания PowerPoint**.</span><span class="sxs-lookup"><span data-stu-id="79853-153">To the use of annotations in shard PowerPoint presentations, clear the **Enable PowerPoint annotations**.</span></span> <span data-ttu-id="79853-154">По умолчанию заметки разрешены.</span><span class="sxs-lookup"><span data-stu-id="79853-154">By default, annotations are allowed.</span></span>
    
      - <span data-ttu-id="79853-p116">Чтобы запретить использование опросов, снимите флажок **Включить опросы**. По умолчанию опросы включены.</span><span class="sxs-lookup"><span data-stu-id="79853-p116">To prevent the use of polls, clear the **Enable polls** check box. By default, polls are allowed.</span></span>

15. <span data-ttu-id="79853-157">В окне **Общий доступ к приложениям** выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="79853-157">In **Application sharing**, do one of the following:</span></span>
    
      - <span data-ttu-id="79853-158">Чтобы запретить использование общего доступа к приложениям, щелкните **Отключить общий доступ к приложениям**.</span><span class="sxs-lookup"><span data-stu-id="79853-158">To prevent the use of application sharing, click **Disable application sharing**.</span></span>
    
      - <span data-ttu-id="79853-p117">Чтобы разрешить использование общего доступа к приложениям, щелкните **Включить общий доступ к приложениям**. Это параметр по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="79853-p117">To allow the use of application sharing, click **Enable application sharing**. This is the default setting.</span></span>

16. <span data-ttu-id="79853-161">Если вы разрешили общий доступ к приложениям в окне **Общий доступ к приложениям**, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="79853-161">If you chose to allow application sharing in **Application sharing**, do the following:</span></span>
    
      - <span data-ttu-id="79853-p118">Чтобы запретить участникам собрания принимать управление общим доступом к приложениям, снимите флажок **Разрешить участникам принимать управление**. По умолчанию участники могут принимать управление общим доступом к приложениям.</span><span class="sxs-lookup"><span data-stu-id="79853-p118">To prevent meeting participants from taking control of application sharing, clear the **Allow participants to take control** check box. By default, participants can take control of application sharing.</span></span>
    
      - <span data-ttu-id="79853-p119">Если вы хотите разрешить участникам собрания принимать управление общим доступом к приложениям, установите флажок **Разрешить федеративным и анонимным участникам принимать управление**. По умолчанию внешние пользователи не могут принимать управление общим доступом к приложениям.</span><span class="sxs-lookup"><span data-stu-id="79853-p119">If you chose to allow meeting participants to take control of application sharing, select the **Allow federated and anonymous participants to take control** check box to allow external users to take control of application sharing. By default, external users cannot take control of application sharing.</span></span>

17. <span data-ttu-id="79853-166">В окне **Политика участника** выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="79853-166">Under **Participant policy**, do one of the following:</span></span>
    
      - <span data-ttu-id="79853-167">Чтобы запретить общий доступ к приложениям и общий доступ к рабочему столу, щелкните **Отключить общий доступ к приложениям и общий доступ к рабочему столу**.</span><span class="sxs-lookup"><span data-stu-id="79853-167">To prevent both application sharing and desktop sharing, click **Disable application and desktop sharing**.</span></span>
    
      - <span data-ttu-id="79853-168">Чтобы разрешить общий доступ к приложениям, но не общий доступ к рабочему столу, щелкните **Включить общий доступ к приложениям**.</span><span class="sxs-lookup"><span data-stu-id="79853-168">To allow application sharing but not desktop sharing, click **Enable application sharing**.</span></span>
    
      - <span data-ttu-id="79853-p120">Чтобы разрешить общий доступ к приложениям и общий доступ к рабочему столу, щелкните **Включить общий доступ к приложениям и общий доступ к рабочему столу**. Это параметр по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="79853-p120">To allow both application sharing and desktop sharing, click **Enable application and desktop sharing**. This is the default setting.</span></span>

18. <span data-ttu-id="79853-p121">Чтобы запретить одноранговую передачу файлов, снимите флажок **Включить одноранговую передачу файлов**. По умолчанию одноранговая передача файлов разрешена.</span><span class="sxs-lookup"><span data-stu-id="79853-p121">To prevent peer-to-peer file transfers, clear the **Enable peer-to-peer file transfer** check box. By default, peer-to-peer file transfers are allowed.</span></span>

19. <span data-ttu-id="79853-p122">Чтобы разрешить одноранговую запись, установите флажок **Включить одноранговую запись**. По умолчанию одноранговая запись запрещена.</span><span class="sxs-lookup"><span data-stu-id="79853-p122">To allow peer-to-peer recording, select the **Enable peer-to-peer recording** check box. By default, peer-to-peer recording is not allowed.</span></span>

20. <span data-ttu-id="79853-p123">Чтобы позволить участникам подключаться с несколькими видеопотоками, установите флажок **Позволить участникам подключаться с несколькими видеопотоками**. По умолчанию несколько видеопотоков разрешены.</span><span class="sxs-lookup"><span data-stu-id="79853-p123">To allow participants to join with multiple video streams, select the **Enable participants to join with multiple video streams** check box. By default, multiple video streams are allowed.</span></span>

21. <span data-ttu-id="79853-177">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="79853-177">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-an-existing-user-or-site-policy"></a><span data-ttu-id="79853-178">Изменение существующей политики пользователей или сайтов</span><span class="sxs-lookup"><span data-stu-id="79853-178">To modify an existing user or site policy</span></span>

1.  <span data-ttu-id="79853-179">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="79853-179">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="79853-180">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="79853-180">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="79853-181">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="79853-181">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="79853-182">На панели навигации слева выберите **Конференц** -связь, а затем — **Политика Конференц**-связи.</span><span class="sxs-lookup"><span data-stu-id="79853-182">In the left navigation bar, click **Conferencing** and then click **Conferencing Policy**.</span></span>

4.  <span data-ttu-id="79853-183">В списке политик конференций выберите политику, которую нужно изменить, нажмите кнопку **Изменить**, а затем **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="79853-183">In the list of conferencing policies, click the policy that you want to change, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="79853-184">В области **Изменение конфигурации собрания** измените любые параметры политики за исключением имени, которое нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="79853-184">In **Edit Conferencing Policy**, modify any of the policy settings, except for the policy name, which cannot be modified.</span></span>

6.  <span data-ttu-id="79853-185">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="79853-185">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

