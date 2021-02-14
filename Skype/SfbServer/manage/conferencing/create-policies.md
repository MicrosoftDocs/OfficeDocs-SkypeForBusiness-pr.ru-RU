---
title: Создание политик в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8c685326-8356-4075-bf95-32324b16ef81
description: Сводка. Узнайте, как создавать политики в Skype для бизнеса Server.
ms.openlocfilehash: 8e707e6da1a56fa1818d436714327936369b06fe
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828239"
---
# <a name="create-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="6933f-103">Создание политик в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="6933f-103">Create conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="6933f-104">**Сводка:** Узнайте, как создавать политики в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="6933f-104">**Summary:** Learn how to create conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="6933f-105">You can create conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="6933f-105">You can create conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="create-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="6933f-106">Create conferencing policies by using Skype for Business Server Control Panel</span><span class="sxs-lookup"><span data-stu-id="6933f-106">Create conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="6933f-107">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="6933f-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="6933f-108">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="6933f-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="6933f-109">В левой панели навигации щелкните **"Conferencing" (Conferencing),** а затем выберите **"Conferencing Policy" (Политика).**</span><span class="sxs-lookup"><span data-stu-id="6933f-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="6933f-110">Нажмите кнопку **Создать**, а затем выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="6933f-110">Click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="6933f-p101">Для создания политики на уровне пользователя щелкните **Политика пользователя**. В окне **Создание политики пользователя** в поле **Имя** введите имя политики.</span><span class="sxs-lookup"><span data-stu-id="6933f-p101">To create a user-level policy, click **User policy**. In **New Conferencing Policy**, in **Name**, type a descriptive name for the policy.</span></span>
    
   - <span data-ttu-id="6933f-p102">Чтобы создать политику уровня сайта, выберите вариант **Политика сайта**. В поле поиска **Выбор сайта** введите часть или полное имя сайта, для которого требуется создать политику. В списке сайтов выберите нужный сайт и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="6933f-p102">To create a site-level policy, click **Site policy**. In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy. In the list of sites, click the site that you want, and then click **OK**.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="6933f-116">Имя сайта становится именем политики conferencing; его нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="6933f-116">The site name becomes the conferencing policy name; it cannot be changed.</span></span> 
  
5. <span data-ttu-id="6933f-117">В поле **Описание** введите описание политики.</span><span class="sxs-lookup"><span data-stu-id="6933f-117">In **Description**, type a description for the policy.</span></span>
    
6. <span data-ttu-id="6933f-p103">В разделе **Политика организатора** в поле **Максимальный размер собрания** введите максимальное допустимое число пользователей собрания. Значение по умолчанию — 250.</span><span class="sxs-lookup"><span data-stu-id="6933f-p103">Under **Organizer policy**, in **Maximum meeting size**, type the maximum number of users that you want to allow at a meeting. By default, the maximum meeting size is 250.</span></span>
    
7. <span data-ttu-id="6933f-120">Чтобы запретить пользователям приглашать на собрания анонимных пользователей, снимите флажок **Allow participants to invite anonymous users (Разрешить участникам приглашать анонимных пользователей)**.</span><span class="sxs-lookup"><span data-stu-id="6933f-120">To prevent users from inviting anonymous users to meetings, clear the **Allow participants to invite anonymous users** check box.</span></span> <span data-ttu-id="6933f-121">Анонимные пользователи — это пользователи, которые не имеют учетных данных в доменных службах Active Directory вашей организации, и поэтому не имеют проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="6933f-121">Anonymous users are users who do not have credentials in your organization's Active Directory Domain Services and who, therefore, are not authenticated.</span></span> <span data-ttu-id="6933f-122">По умолчанию пользователи могут приглашать анонимных пользователей на собрания.</span><span class="sxs-lookup"><span data-stu-id="6933f-122">By default, users can invite anonymous users to meetings.</span></span>
    
8. <span data-ttu-id="6933f-123">В разделе **Recording (Запись)** выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="6933f-123">In **Recording**, do one of the following:</span></span>
    
   - <span data-ttu-id="6933f-p105">Чтобы запретить участникам записывать собрания, выберите **None (Нет)**. Это установка по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6933f-p105">To prevent participants from recording meetings, click **None**. This is the default setting.</span></span>
    
   - <span data-ttu-id="6933f-126">Чтобы разрешить участникам записывать собрания, выберите **Enable recording (Разрешить запись)**.</span><span class="sxs-lookup"><span data-stu-id="6933f-126">To allow participants to record meetings, click **Enable recording**.</span></span>
    
9. <span data-ttu-id="6933f-p106">Чтобы разрешить внешним участникам записывать собрания, установите флажок **Allow federated and anonymous participants to record (Разрешить запись федеративным и анонимным участникам)**. По умолчанию внешним участникам запрещено записывать собрания.</span><span class="sxs-lookup"><span data-stu-id="6933f-p106">To allow external participants to record meetings, select the **Allow federated and anonymous participants to record** check box. The default is to prevent external participants from recording meetings.</span></span>
    
10. <span data-ttu-id="6933f-129">В разделе **Audio/video (Звук и видео)** выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="6933f-129">In **Audio/video**, do one of the following:</span></span>
    
    - <span data-ttu-id="6933f-130">Чтобы запретить использование звука и видео, выберите **None (Нет)**.</span><span class="sxs-lookup"><span data-stu-id="6933f-130">To prevent the use of audio and video, click **None**.</span></span>
    
    - <span data-ttu-id="6933f-131">Чтобы разрешить использование звука, но не видео, выберите **Enable IP audio (Включить IP-звук)**.</span><span class="sxs-lookup"><span data-stu-id="6933f-131">To allow the use of audio but not video, click **Enable IP audio**.</span></span>
    
    - <span data-ttu-id="6933f-p107">Чтобы разрешить использование звука и видео, выберите **Enable IP audio/video (Включить IP-звук и видео)**. Это установка по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6933f-p107">To allow the use of audio and video, click **Enable IP audio/video**. This is the default setting.</span></span>
    
11. <span data-ttu-id="6933f-134">Если вы разрешили видео в разделе **Audio/video (Звук и видео)**, выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="6933f-134">If you chose to allow the use of audio in **Audio/video**, do the following:</span></span>
    
    - <span data-ttu-id="6933f-p108">Чтобы запретить пользователям присоединяться к собранию по телефону, снимите флажок **Enable PSTN dial-in conferencing (Разрешить конференц-связь с телефонным подключением ТСОП)**. По умолчанию пользователи могут подключаться к собраниям с помощью телефонной сети общего пользования (ТСОП).</span><span class="sxs-lookup"><span data-stu-id="6933f-p108">To prevent users from joining the meeting by dialing in, clear the **Enable PSTN dial-in conferencing** check box. By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>
    
    - <span data-ttu-id="6933f-p109">Если вы разрешили пользователям присоединяться к собраниям по телефону и хотите разрешить неавторизованным (анонимным) пользователям присоединяться к собраниям обратным звонком, установите флажок **Allow anonymous participants to dial out (Разрешить анонимным участникам присоединяться обратным звонком)**. При обратном звонке сервер конференций вызывает пользователя, и пользователь отвечает по телефону, чтобы присоединиться к собранию. По умолчанию анонимные пользователи не могут присоединяться к собраниям обратным звонком.</span><span class="sxs-lookup"><span data-stu-id="6933f-p109">If you allow users to dial in to meetings and you want to allow unauthenticated (anonymous) users to join a meeting by using dial out phoning, select the **Allow anonymous participants to dial out** check box. With dial-out phoning, the conference server calls the user, and the user answers the phone to join the meeting. By default, anonymous users cannot join a meeting by using dial-out phoning.</span></span>
    
12. <span data-ttu-id="6933f-140">Если вы разрешили использование видео в аудио- **и** видеопотоках, проверьте разрешение **нескольких видеопотоков.**</span><span class="sxs-lookup"><span data-stu-id="6933f-140">If you chose to allow the use of video in **Audio/video**, check **Allow multiple video streams**.</span></span>
    
13. <span data-ttu-id="6933f-141">В разделе **Data collaboration (Совместная работа с данными)** выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="6933f-141">In **Data collaboration**, do one of the following:</span></span>
    
    - <span data-ttu-id="6933f-142">Чтобы запретить совместную работу с данными, выберите **None (Нет)**.</span><span class="sxs-lookup"><span data-stu-id="6933f-142">To prevent data collaboration, click **None**.</span></span>
    
    - <span data-ttu-id="6933f-p110">Чтобы разрешить совместную работу с данными, выберите **Enable data collaboration (Разрешить совместную работу с данными)**. Это установка по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6933f-p110">To allow data collaboration, click **Enable data collaboration**. This is the default setting.</span></span>
    
14. <span data-ttu-id="6933f-145">Если вы разрешили совместную работу с данными в разделе **Data collaboration (Совместная работа с данными)**, выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="6933f-145">If you chose to allow data collaboration in **Data collaboration**, do the following:</span></span>
    
    - <span data-ttu-id="6933f-p111">Чтобы запретить внешние загрузки, снимите флажок **Allow federated and anonymous participants to download content (Разрешить загрузку контента федеративным и анонимным участникам)**. По умолчанию внешние пользователи могут загружать контент.</span><span class="sxs-lookup"><span data-stu-id="6933f-p111">To prevent external downloads, clear the **Allow federated and anonymous participants to download content** check box. By default, external users can download content.</span></span>
    
    - <span data-ttu-id="6933f-p112">Чтобы запретить передачу файлов, снимите флажок **Allow participants to transfer files (Разрешить передачу файлов участникам)**. По умолчанию пользователи могут передавать файлы.</span><span class="sxs-lookup"><span data-stu-id="6933f-p112">To prevent file transfers, clear the **Allow participants to transfer files** check box. By default, users can transfer files.</span></span>
    
    - <span data-ttu-id="6933f-150">Чтобы запретить использование заметок, снимите флажок **Enable annotations (Разрешить заметки)**.</span><span class="sxs-lookup"><span data-stu-id="6933f-150">To prevent the use of annotations, clear the **Enable annotations** check box.</span></span> <span data-ttu-id="6933f-151">Чтобы использовать аннотации в общих презентациях PowerPoint, очищает **аннотации PowerPoint.**</span><span class="sxs-lookup"><span data-stu-id="6933f-151">To the use of annotations in shared PowerPoint presentations, clear the **Enable PowerPoint annotations**.</span></span> <span data-ttu-id="6933f-152">По умолчанию заметки разрешены.</span><span class="sxs-lookup"><span data-stu-id="6933f-152">By default, annotations are allowed.</span></span>
    
    - <span data-ttu-id="6933f-p114">Чтобы запретить использование опросов, снимите флажок **Enable polls (Разрешить опросы)**. По умолчанию опросы разрешены.</span><span class="sxs-lookup"><span data-stu-id="6933f-p114">To prevent the use of polls, clear the **Enable polls** check box. By default, polls are allowed.</span></span>
    
15. <span data-ttu-id="6933f-155">В разделе **Application sharing (Общий доступ к приложениям)** выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="6933f-155">In **Application sharing**, do one of the following:</span></span>
    
    - <span data-ttu-id="6933f-156">Чтобы запретить использование общего доступа к приложениям, выберите **Disable application sharing (Отключить общий доступ к приложениям)**.</span><span class="sxs-lookup"><span data-stu-id="6933f-156">To prevent the use of application sharing, click **Disable application sharing**.</span></span>
    
    - <span data-ttu-id="6933f-p115">Чтобы разрешить использование общего доступа к приложениям, выберите  **Enable application sharing (Включить общий доступ к приложениям)**. Это установка по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6933f-p115">To allow the use of application sharing, click **Enable application sharing**. This is the default setting.</span></span>
    
16. <span data-ttu-id="6933f-159">Если вы разрешили общий доступ к приложениям в разделе **Application sharing (Общий доступ к приложениям)**, выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="6933f-159">If you chose to allow application sharing in **Application sharing**, do the following:</span></span>
    
    - <span data-ttu-id="6933f-p116">Чтобы запретить участникам собрания управлять общим доступом к приложениям, снимите флажок **Allow participants to take control (Разрешить участникам управлять)**. По умолчанию участники могут управлять общим доступом к приложениям.</span><span class="sxs-lookup"><span data-stu-id="6933f-p116">To prevent meeting participants from taking control of application sharing, clear the **Allow participants to take control** check box. By default, participants can take control of application sharing.</span></span>
    
    - <span data-ttu-id="6933f-p117">Если вы разрешили участникам собрания управлять общим доступом к приложениям, установите флажок **Allow federated and anonymous participants to take control (Разрешить федеративным и анонимным участникам управлять)**, чтобы разрешить внешним пользователям управлять общим доступом к приложениям. По умолчанию внешние пользователи не могут управлять общим доступом к приложениям.</span><span class="sxs-lookup"><span data-stu-id="6933f-p117">If you chose to allow meeting participants to take control of application sharing, select the **Allow federated and anonymous participants to take control** check box to allow external users to take control of application sharing. By default, external users cannot take control of application sharing.</span></span>
    
17. <span data-ttu-id="6933f-164">В разделе **Participant policy (Политика участников)** выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="6933f-164">Under **Participant policy**, do one of the following:</span></span>
    
    - <span data-ttu-id="6933f-165">Чтобы запретить общий доступ к приложениям и общий доступ к рабочим столам, выберите **Disable application and desktop sharing (Отключить общий доступ к приложениям и рабочим столам)**.</span><span class="sxs-lookup"><span data-stu-id="6933f-165">To prevent both application sharing and desktop sharing, click **Disable application and desktop sharing**.</span></span>
    
    - <span data-ttu-id="6933f-166">Чтобы разрешить общий доступ к приложениям, но не к рабочим столам, выберите **Enable application sharing (Включить общий доступ к приложениям)**.</span><span class="sxs-lookup"><span data-stu-id="6933f-166">To allow application sharing but not desktop sharing, click **Enable application sharing**.</span></span>
    
    - <span data-ttu-id="6933f-p118">Чтобы разрешить общий доступ и к приложениям, и к рабочим столам, выберите **Enable application and desktop sharing (Включить общий доступ к приложениям и рабочим столам)**. Это установка по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6933f-p118">To allow both application sharing and desktop sharing, click **Enable application and desktop sharing**. This is the default setting.</span></span>
    
18. <span data-ttu-id="6933f-p119">Чтобы запретить одноранговую передачу файлов, снимите флажок **Enable peer-to-peer file transfer (Включить одноранговую передачу файлов)**. По умолчанию одноранговые передачи файлов разрешены.</span><span class="sxs-lookup"><span data-stu-id="6933f-p119">To prevent peer-to-peer file transfers, clear the **Enable peer-to-peer file transfer** check box. By default, peer-to-peer file transfers are allowed.</span></span>
    
19. <span data-ttu-id="6933f-p120">Чтобы разрешить одноранговую запись, установите флажок **Включить одноранговую запись**. По умолчанию одноранговая запись запрещена.</span><span class="sxs-lookup"><span data-stu-id="6933f-p120">To allow peer-to-peer recording, select the **Enable peer-to-peer recording** check box. By default, peer-to-peer recording is not allowed.</span></span>
    
20. <span data-ttu-id="6933f-p121">Чтобы позволить участникам подключаться с несколькими видеопотоками, установите флажок **Позволить участникам подключаться с несколькими видеопотоками**. По умолчанию несколько видеопотоков разрешены.</span><span class="sxs-lookup"><span data-stu-id="6933f-p121">To allow participants to join with multiple video streams, select the **Enable participants to join with multiple video streams** check box. By default, multiple video streams are allowed.</span></span>
    
21. <span data-ttu-id="6933f-175">Нажмите кнопку **Зафиксировать**.</span><span class="sxs-lookup"><span data-stu-id="6933f-175">Click **Commit**.</span></span>
    
## <a name="create-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="6933f-176">Create conferencing policies by using Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="6933f-176">Create conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="6933f-177">Чтобы создать политики для conferencing, используйте **cmdlet New-CsConferencingPolicy.**</span><span class="sxs-lookup"><span data-stu-id="6933f-177">To create conferencing policies, use the **New-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="6933f-178">В следующем примере создается новая политика с идентификатором SalesConferencingPolicy.</span><span class="sxs-lookup"><span data-stu-id="6933f-178">The following example creates a new conferencing policy with the Identity SalesConferencingPolicy.</span></span> <span data-ttu-id="6933f-179">Эта политика будет использовать все значения по умолчанию для политики conferencing, кроме одного: MaxMeetingSize.</span><span class="sxs-lookup"><span data-stu-id="6933f-179">This policy will use all the default values for a conferencing policy except one: MaxMeetingSize.</span></span> <span data-ttu-id="6933f-180">В этом примере максимальный размер собрания будет иметь значение 50 вместо значения по умолчанию 250:</span><span class="sxs-lookup"><span data-stu-id="6933f-180">In this example, the maximum size for a meeting will be set to 50 instead of the default value of 250:</span></span>
  
```PowerShell
New-CsConferencingPolicy -Identity SalesConferencingPolicy -MaxMeetingSize 50
```

<span data-ttu-id="6933f-181">Дополнительные сведения, включая полное описание синтаксиса и список параметров, см. в описании [New-CsConferencingPolicy.](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="6933f-181">For more information, including a complete syntax description and list of parameters, see [New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps).</span></span>
  

