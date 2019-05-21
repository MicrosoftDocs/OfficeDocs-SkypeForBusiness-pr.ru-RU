---
title: Создание политик конференц-связи в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8c685326-8356-4075-bf95-32324b16ef81
description: 'Сводка: сведения о создании политик конференц-связи в Skype для бизнеса Server.'
ms.openlocfilehash: 323a50ab779e772ca6149dc4c151f9d42d55df66
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34304014"
---
# <a name="create-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="0418e-103">Создание политик конференц-связи в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="0418e-103">Create conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="0418e-104">**Сводка:** Сведения о том, как создавать политики конференций в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="0418e-104">**Summary:** Learn how to create conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="0418e-105">Вы можете создавать политики конференций с помощью панели управления Skype для бизнеса Server или с помощью командной консоли Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="0418e-105">You can create conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="create-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="0418e-106">Создание политик конференц-связи с помощью панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="0418e-106">Create conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="0418e-107">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="0418e-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="0418e-108">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="0418e-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="0418e-109">На левой панели навигации щелкните **Конференция**, а затем — **Политика конференц-связи**.</span><span class="sxs-lookup"><span data-stu-id="0418e-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="0418e-110">Нажмите кнопку **Создать**, а затем выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="0418e-110">Click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="0418e-p101">Для создания политики на уровне пользователя щелкните **Политика пользователя**. В окне **Создание политики пользователя** в поле **Имя** введите имя политики.</span><span class="sxs-lookup"><span data-stu-id="0418e-p101">To create a user-level policy, click **User policy**. In **New Conferencing Policy**, in **Name**, type a descriptive name for the policy.</span></span>
    
   - <span data-ttu-id="0418e-p102">Чтобы создать политику уровня сайта, выберите вариант **Политика сайта**. В поле поиска **Выбор сайта** введите часть или полное имя сайта, для которого требуется создать политику. В списке сайтов выберите нужный сайт и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0418e-p102">To create a site-level policy, click **Site policy**. In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy. In the list of sites, click the site that you want, and then click **OK**.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="0418e-116">Имя сайта становится именем политики конференций, его нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="0418e-116">The site name becomes the conferencing policy name; it cannot be changed.</span></span> 
  
5. <span data-ttu-id="0418e-117">В поле **Описание** введите описание политики.</span><span class="sxs-lookup"><span data-stu-id="0418e-117">In **Description**, type a description for the policy.</span></span>
    
6. <span data-ttu-id="0418e-p103">В разделе **Политика организатора** в поле **Максимальный размер собрания** введите максимальное допустимое число пользователей собрания. Значение по умолчанию — 250.</span><span class="sxs-lookup"><span data-stu-id="0418e-p103">Under **Organizer policy**, in **Maximum meeting size**, type the maximum number of users that you want to allow at a meeting. By default, the maximum meeting size is 250.</span></span>
    
7. <span data-ttu-id="0418e-120">To prevent users from inviting anonymous users to meetings, clear the **Allow participants to invite anonymous users** check box.</span><span class="sxs-lookup"><span data-stu-id="0418e-120">To prevent users from inviting anonymous users to meetings, clear the **Allow participants to invite anonymous users** check box.</span></span> <span data-ttu-id="0418e-121">Анонимные пользователи — это пользователи, у которых нет учетных данных в доменных службах Active Directory вашей организации и которые, следовательно, не прошли проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="0418e-121">Anonymous users are users who do not have credentials in your organization's Active Directory Domain Services and who, therefore, are not authenticated.</span></span> <span data-ttu-id="0418e-122">By default, users can invite anonymous users to meetings.</span><span class="sxs-lookup"><span data-stu-id="0418e-122">By default, users can invite anonymous users to meetings.</span></span>
    
8. <span data-ttu-id="0418e-123">В окне **Запись** выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="0418e-123">In **Recording**, do one of the following:</span></span>
    
   - <span data-ttu-id="0418e-p105">Чтобы запретить участникам записывать собрания, щелкните **Нет**. Это параметр по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0418e-p105">To prevent participants from recording meetings, click **None**. This is the default setting.</span></span>
    
   - <span data-ttu-id="0418e-126">Чтобы разрешить участникам записывать собрания, щелкните **Включить запись**.</span><span class="sxs-lookup"><span data-stu-id="0418e-126">To allow participants to record meetings, click **Enable recording**.</span></span>
    
9. <span data-ttu-id="0418e-p106">Чтобы разрешить внешним участникам записывать собрания, установите флажок **Разрешить федеративным и анонимным участникам запись**. Значение по умолчанию — запретить внешним участникам записывать собрания.</span><span class="sxs-lookup"><span data-stu-id="0418e-p106">To allow external participants to record meetings, select the **Allow federated and anonymous participants to record** check box. The default is to prevent external participants from recording meetings.</span></span>
    
10. <span data-ttu-id="0418e-129">В окне **Аудио и видео** выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="0418e-129">In **Audio/video**, do one of the following:</span></span>
    
    - <span data-ttu-id="0418e-130">Чтобы запретить использование аудио и видео, щелкните **Нет**.</span><span class="sxs-lookup"><span data-stu-id="0418e-130">To prevent the use of audio and video, click **None**.</span></span>
    
    - <span data-ttu-id="0418e-131">Чтобы разрешить использование аудио, но не видео, щелкните **Включить IP-аудио**.</span><span class="sxs-lookup"><span data-stu-id="0418e-131">To allow the use of audio but not video, click **Enable IP audio**.</span></span>
    
    - <span data-ttu-id="0418e-p107">Чтобы разрешить использование аудио и видео, щелкните **Включить IP-аудио и видео**. Это параметр по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0418e-p107">To allow the use of audio and video, click **Enable IP audio/video**. This is the default setting.</span></span>
    
11. <span data-ttu-id="0418e-134">Если вы разрешили использование аудио в окне **Аудио и видео**, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="0418e-134">If you chose to allow the use of audio in **Audio/video**, do the following:</span></span>
    
    - <span data-ttu-id="0418e-p108">Чтобы запретить пользователям присоединяться к собранию по телефонной связи, снимите флажок **Включить конференц-связь с телефонным подключением ТСОП**. По умолчанию пользователи могут подключиться к собраниям с ТСОП.</span><span class="sxs-lookup"><span data-stu-id="0418e-p108">To prevent users from joining the meeting by dialing in, clear the **Enable PSTN dial-in conferencing** check box. By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>
    
    - <span data-ttu-id="0418e-p109">Если вы разрешили пользователям подключаться к собраниям по телефонной связи и хотите анонимным пользователям присоединяться к собранию с помощью обратного звонка, установите флажок **Разрешить анонимным участникам обратный звонок**. При использовании обратных звонков сервер конференций вызывает пользователя, который отвечает на звонок, чтобы присоединиться к собранию. По умолчанию анонимные пользователи не могут присоединиться к собранию с помощью подключения обратным звонком.</span><span class="sxs-lookup"><span data-stu-id="0418e-p109">If you allow users to dial in to meetings and you want to allow unauthenticated (anonymous) users to join a meeting by using dial out phoning, select the **Allow anonymous participants to dial out** check box. With dial-out phoning, the conference server calls the user, and the user answers the phone to join the meeting. By default, anonymous users cannot join a meeting by using dial-out phoning.</span></span>
    
12. <span data-ttu-id="0418e-140">Если вы разрешили использование видео в окне **Аудио и видео**, установите флажок **Разрешить несколько видеопотоков**.</span><span class="sxs-lookup"><span data-stu-id="0418e-140">If you chose to allow the use of video in **Audio/video**, check **Allow multiple video streams**.</span></span>
    
13. <span data-ttu-id="0418e-141">В окне **Совместная работа с данными** выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="0418e-141">In **Data collaboration**, do one of the following:</span></span>
    
    - <span data-ttu-id="0418e-142">Чтобы запретить совместную работу с данными, щелкните **Нет**.</span><span class="sxs-lookup"><span data-stu-id="0418e-142">To prevent data collaboration, click **None**.</span></span>
    
    - <span data-ttu-id="0418e-p110">Чтобы разрешить совместную работу с данными, щелкните **Включить совместную работу с данными**. Это параметр по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0418e-p110">To allow data collaboration, click **Enable data collaboration**. This is the default setting.</span></span>
    
14. <span data-ttu-id="0418e-145">Если вы разрешили совместную работу с данными в окне **Совместная работа с данными**, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="0418e-145">If you chose to allow data collaboration in **Data collaboration**, do the following:</span></span>
    
    - <span data-ttu-id="0418e-p111">Чтобы запретить внешние загрузки, снимите флажок **Разрешить федеративным и анонимным участникам загружать контент**.</span><span class="sxs-lookup"><span data-stu-id="0418e-p111">To prevent external downloads, clear the **Allow federated and anonymous participants to download content** check box. By default, external users can download content.</span></span>
    
    - <span data-ttu-id="0418e-p112">Чтобы запретить передачу файлов, снимите флажок **Разрешить участникам передавать файлы**.</span><span class="sxs-lookup"><span data-stu-id="0418e-p112">To prevent file transfers, clear the **Allow participants to transfer files** check box. By default, users can transfer files.</span></span>
    
    - <span data-ttu-id="0418e-p113">Чтобы запретить использование заметок, снимите флажок **Включить заметки**. Чтобы использовать заметки в общих презентациях PowerPoint, снимите флажок **Включить заметки PowerPoint**. По умолчанию заметки разрешены.</span><span class="sxs-lookup"><span data-stu-id="0418e-p113">To prevent the use of annotations, clear the **Enable annotations** check box. To the use of annotations in shared PowerPoint presentations, clear the **Enable PowerPoint annotations**. By default, annotations are allowed.</span></span>
    
    - <span data-ttu-id="0418e-p114">Чтобы запретить использование опросов, снимите флажок **Включить опросы**. По умолчанию опросы включены.</span><span class="sxs-lookup"><span data-stu-id="0418e-p114">To prevent the use of polls, clear the **Enable polls** check box. By default, polls are allowed.</span></span>
    
15. <span data-ttu-id="0418e-155">В окне **Общий доступ к приложениям** выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="0418e-155">In **Application sharing**, do one of the following:</span></span>
    
    - <span data-ttu-id="0418e-156">Чтобы запретить использование общего доступа к приложениям, щелкните **Отключить общий доступ к приложениям**.</span><span class="sxs-lookup"><span data-stu-id="0418e-156">To prevent the use of application sharing, click **Disable application sharing**.</span></span>
    
    - <span data-ttu-id="0418e-p115">Чтобы разрешить использование общего доступа к приложениям, щелкните **Включить общий доступ к приложениям**. Это параметр по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0418e-p115">To allow the use of application sharing, click **Enable application sharing**. This is the default setting.</span></span>
    
16. <span data-ttu-id="0418e-159">Если вы разрешили общий доступ к приложениям в окне **Общий доступ к приложениям**, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="0418e-159">If you chose to allow application sharing in **Application sharing**, do the following:</span></span>
    
    - <span data-ttu-id="0418e-p116">Чтобы запретить участникам собрания принимать управление общим доступом к приложениям, снимите флажок **Разрешить участникам принимать управление**. По умолчанию участники могут принимать управление общим доступом к приложениям.</span><span class="sxs-lookup"><span data-stu-id="0418e-p116">To prevent meeting participants from taking control of application sharing, clear the **Allow participants to take control** check box. By default, participants can take control of application sharing.</span></span>
    
    - <span data-ttu-id="0418e-p117">Если вы хотите разрешить участникам собрания принимать управление общим доступом к приложениям, установите флажок **Разрешить федеративным и анонимным участникам принимать управление**. По умолчанию внешние пользователи не могут принимать управление общим доступом к приложениям.</span><span class="sxs-lookup"><span data-stu-id="0418e-p117">If you chose to allow meeting participants to take control of application sharing, select the **Allow federated and anonymous participants to take control** check box to allow external users to take control of application sharing. By default, external users cannot take control of application sharing.</span></span>
    
17. <span data-ttu-id="0418e-164">В окне **Политика участника** выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="0418e-164">Under **Participant policy**, do one of the following:</span></span>
    
    - <span data-ttu-id="0418e-165">Чтобы запретить общий доступ к приложениям и общий доступ к рабочему столу, щелкните **Отключить общий доступ к приложениям и общий доступ к рабочему столу**.</span><span class="sxs-lookup"><span data-stu-id="0418e-165">To prevent both application sharing and desktop sharing, click **Disable application and desktop sharing**.</span></span>
    
    - <span data-ttu-id="0418e-166">Чтобы разрешить общий доступ к приложениям, но не общий доступ к рабочему столу, щелкните **Включить общий доступ к приложениям**.</span><span class="sxs-lookup"><span data-stu-id="0418e-166">To allow application sharing but not desktop sharing, click **Enable application sharing**.</span></span>
    
    - <span data-ttu-id="0418e-p118">Чтобы разрешить общий доступ к приложениям и общий доступ к рабочему столу, щелкните **Включить общий доступ к приложениям и общий доступ к рабочему столу**. Это параметр по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0418e-p118">To allow both application sharing and desktop sharing, click **Enable application and desktop sharing**. This is the default setting.</span></span>
    
18. <span data-ttu-id="0418e-p119">Чтобы запретить одноранговую передачу файлов, снимите флажок **Включить одноранговую передачу файлов**. По умолчанию одноранговая передача файлов разрешена.</span><span class="sxs-lookup"><span data-stu-id="0418e-p119">To prevent peer-to-peer file transfers, clear the **Enable peer-to-peer file transfer** check box. By default, peer-to-peer file transfers are allowed.</span></span>
    
19. <span data-ttu-id="0418e-p120">Чтобы разрешить одноранговую запись, установите флажок **Включить одноранговую запись**. По умолчанию одноранговая запись запрещена.</span><span class="sxs-lookup"><span data-stu-id="0418e-p120">To allow peer-to-peer recording, select the **Enable peer-to-peer recording** check box. By default, peer-to-peer recording is not allowed.</span></span>
    
20. <span data-ttu-id="0418e-p121">Чтобы позволить участникам подключаться с несколькими видеопотоками, установите флажок **Позволить участникам подключаться с несколькими видеопотоками**. По умолчанию несколько видеопотоков разрешены.</span><span class="sxs-lookup"><span data-stu-id="0418e-p121">To allow participants to join with multiple video streams, select the **Enable participants to join with multiple video streams** check box. By default, multiple video streams are allowed.</span></span>
    
21. <span data-ttu-id="0418e-175">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="0418e-175">Click **Commit**.</span></span>
    
## <a name="create-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="0418e-176">Создание политик конференц-связи с помощью командной консоли Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="0418e-176">Create conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="0418e-177">Чтобы создать политики конференц-связи, используйте командлет **New-CsConferencingPolicy**.</span><span class="sxs-lookup"><span data-stu-id="0418e-177">To create conferencing policies, use the **New-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="0418e-178">В следующем примере создается новая политика конференц-связи с удостоверением СалесконференЦингполици.</span><span class="sxs-lookup"><span data-stu-id="0418e-178">The following example creates a new conferencing policy with the Identity SalesConferencingPolicy.</span></span> <span data-ttu-id="0418e-179">В этой политике будут использованы все значения по умолчанию, кроме одного: MaxMeetingSize.</span><span class="sxs-lookup"><span data-stu-id="0418e-179">This policy will use all the default values for a conferencing policy except one: MaxMeetingSize.</span></span> <span data-ttu-id="0418e-180">В этом примере максимальное количество участников будет 50 вместо значения по умолчанию — 250.</span><span class="sxs-lookup"><span data-stu-id="0418e-180">In this example, the maximum size for a meeting will be set to 50 instead of the default value of 250:</span></span>
  
```
New-CsConferencingPolicy -Identity SalesConferencingPolicy -MaxMeetingSize 50
```

<span data-ttu-id="0418e-181">Дополнительные сведения, в том числе полные описания синтаксиса и список параметров, можно найти в разделе [New-ксконференЦингполици](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="0418e-181">For more information, including a complete syntax description and list of parameters, see [New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps).</span></span>
  

