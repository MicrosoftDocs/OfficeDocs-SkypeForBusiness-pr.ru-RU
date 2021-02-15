---
title: Публикация ожидающих изменений в конфигурации маршрутации голосовой почты в Skype для бизнеса
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
description: Сводка. Узнайте, как просмотреть, опубликовать или отменить изменения конфигурации маршрутации голосовой почты в Skype для бизнеса Server с помощью панели управления Skype для бизнеса Server.
ms.openlocfilehash: 6b75b6a1135cf9abde9551112fc9c29579862a8b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830399"
---
# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-skype-for-business"></a><span data-ttu-id="8ad92-103">Публикация ожидающих изменений в конфигурации маршрутации голосовой почты в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="8ad92-103">Publish pending changes to the voice routing configuration in Skype for Business</span></span>
 
<span data-ttu-id="8ad92-104">**Сводка:** Learn how to review, publish, or cancel voice routing configuration changes in Skype for Business Server by using the Skype for Business Server Control Panel.</span><span class="sxs-lookup"><span data-stu-id="8ad92-104">**Summary:** Learn how to review, publish, or cancel voice routing configuration changes in Skype for Business Server by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="8ad92-105">После внесения изменений в любые параметры конфигурации в группе **Маршрутизация голосовых вызовов** выполните эту процедуру, чтобы проверить, опубликовать или отменить ожидающие изменения.</span><span class="sxs-lookup"><span data-stu-id="8ad92-105">After you make changes to any of the configuration settings in pages in the **Voice Routing** group, perform this procedure to review, publish, or cancel the pending changes.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="8ad92-106">Необходимо следить за тем, чтобы одновременно параметры конфигурации маршрутизации голосовых вызовов изменял только один пользователь.</span><span class="sxs-lookup"><span data-stu-id="8ad92-106">Be sure that only one user at a time modifies the Voice Routing configuration settings.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="8ad92-p101">Все ожидающие изменения необходимо публиковать одновременно, выполнив команду **Фиксировать все**. Ожидающие изменения нельзя публиковать выборочно. Перед публикацией ожидающих изменений выполните команду **Review uncommitted changes** (Проверка несохраненных изменений) и отмените изменения конфигурации, которые не требуется публиковать.</span><span class="sxs-lookup"><span data-stu-id="8ad92-p101">All pending changes must be published at the same time by running the **Commit all** command. You cannot selectively publish pending changes. Before you publish pending changes, run the **Review uncommitted changes** command and cancel any configuration changes that you do not want to publish.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8ad92-110">Если перейти со страницы в группе **Маршрутизация голосовых вызовов** до фиксации ожидающих изменений, изменения будут утрачены.</span><span class="sxs-lookup"><span data-stu-id="8ad92-110">If you navigate away from the pages in the **Voice Routing** group before committing pending changes, all pending changes will be lost.</span></span> <span data-ttu-id="8ad92-111">Тем не менее, текущую конфигурацию (включая все ожидающие изменения) можно экспортировать в файл конфигурации голосовой связи, а затем импортировать и опубликовать обновленную конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="8ad92-111">However, you can export the current configuration (including any pending changes) to a voice configuration file, and then import and publish the updated configuration.</span></span> <span data-ttu-id="8ad92-112">For details, see [Export or import a voice route configuration file in Skype for Business](voice-route-configuration-import-export.md).</span><span class="sxs-lookup"><span data-stu-id="8ad92-112">For details, see [Export or import a voice route configuration file in Skype for Business](voice-route-configuration-import-export.md).</span></span> 
  
### <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a><span data-ttu-id="8ad92-113">Просмотр, публикация или отмена изменений конфигурации маршрутизации голосовых вызовов</span><span class="sxs-lookup"><span data-stu-id="8ad92-113">To review, publish, or cancel voice routing configuration changes</span></span>

1. <span data-ttu-id="8ad92-114">Войдите на компьютер в качестве члена группы RTCUniversalServerAdmins или роли администратора **CsVoiceAdministrator**, **CsServerAdministrator** или **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="8ad92-114">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="8ad92-115">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="8ad92-115">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="8ad92-116">В левой области навигации щелкните элемент **Voice Routing** (Маршрутизация голосовых вызовов).</span><span class="sxs-lookup"><span data-stu-id="8ad92-116">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="8ad92-117">Внесите необходимые изменения в параметры на каждой странице группы **Маршрутизация голосовых вызовов**.</span><span class="sxs-lookup"><span data-stu-id="8ad92-117">Make the configuration changes you want to the settings on each page of the **Voice Routing** group.</span></span>
    
5. <span data-ttu-id="8ad92-118">Чтобы просмотреть ожидающие изменения, не публикуя их, в меню **Зафиксировать** выберите пункт **Проверка несохраненных изменений**.</span><span class="sxs-lookup"><span data-stu-id="8ad92-118">To review pending changes without publishing them, select **Review uncommitted changes** from the **Commit** menu.</span></span>
    
6. <span data-ttu-id="8ad92-119">Чтобы отменить ожидающие изменения, выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="8ad92-119">If you want to cancel any of the pending changes, do one of the following:</span></span>
    
   - <span data-ttu-id="8ad92-120">В меню **Зафиксировать** выберите пункт **Cancel all uncommitted changes** (Отмена всех незафиксированных изменений).</span><span class="sxs-lookup"><span data-stu-id="8ad92-120">Select **Cancel all uncommitted changes** from the **Commit** menu.</span></span>
    
   - <span data-ttu-id="8ad92-121">Перейдите на вкладку страницы **Маршрутизация голосовых вызовов** с ожидающими изменениями, которые требуется отменить, выберите элемент с ожидающими изменениями, нажмите кнопку **Зафиксировать**, а затем **Cancel selected changes** (Отмена выбранных изменений).</span><span class="sxs-lookup"><span data-stu-id="8ad92-121">Navigate to the tab of the **Voice Routing** page that has pending changes you want to cancel, select the item with the pending changes, click **Commit**, and then click **Cancel selected changes**.</span></span>
    
7. <span data-ttu-id="8ad92-122">Просмотрев все ожидающие изменения и отменив те, которые не требуется публиковать, нажмите кнопку **Зафиксировать**, а затем **Фиксировать все**.</span><span class="sxs-lookup"><span data-stu-id="8ad92-122">After you have reviewed all pending changes and canceled any that you do not want to publish, click **Commit**, and then click **Commit all**.</span></span>
    
8. <span data-ttu-id="8ad92-123">В диалоговом окне **Uncommitted Voice Configuration Settings** (Незафиксированные параметры конфигурации голосовой связи), в котором отображается список всех ожидающих изменений, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8ad92-123">In the **Uncommitted Voice Configuration Settings** dialog box, which displays a list of all of the pending changes, click **OK**.</span></span> 
    
    <span data-ttu-id="8ad92-124">Когда панель управления Skype для бизнеса Server заверит изменения, появляется сообщение о конфигурации успешно опубликованной **маршрутиации голосовой** почты.</span><span class="sxs-lookup"><span data-stu-id="8ad92-124">When Skype for Business Server Control Panel has committed the changes, the **Successfully published voice routing configuration** message appears.</span></span>
    

