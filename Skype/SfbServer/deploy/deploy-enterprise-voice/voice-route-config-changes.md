---
title: Публикация ожидающих изменений конфигурации маршрутизации голосовой связи в Скайп для бизнеса
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
description: 'Сводка: Узнайте, как для просмотра, публикация или Отмена изменений конфигурации маршрутизации голосовых в Скайп для Business Server с помощью Скайп для панели управления Business Server.'
ms.openlocfilehash: 9878e719234a5d7eff2e7321fa71e30c094d489a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32222459"
---
# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-skype-for-business"></a><span data-ttu-id="bc69f-103">Публикация ожидающих изменений конфигурации маршрутизации голосовой связи в Скайп для бизнеса</span><span class="sxs-lookup"><span data-stu-id="bc69f-103">Publish pending changes to the voice routing configuration in Skype for Business</span></span>
 
<span data-ttu-id="bc69f-104">**Сводка:** Узнайте, как для просмотра, публикация или Отмена изменений конфигурации маршрутизации голосовых в Скайп для Business Server с помощью Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="bc69f-104">**Summary:** Learn how to review, publish, or cancel voice routing configuration changes in Skype for Business Server by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="bc69f-105">После внесения изменений в любые параметры конфигурации в группе **Маршрутизация голосовой связи** выполните эту процедуру, чтобы проверить, опубликовать или отменить ожидающие изменения.</span><span class="sxs-lookup"><span data-stu-id="bc69f-105">After you make changes to any of the configuration settings in pages in the **Voice Routing** group, perform this procedure to review, publish, or cancel the pending changes.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="bc69f-106">Необходимо следить за тем, чтобы одновременно параметры конфигурации маршрутизации голосовых вызовов изменял только один пользователь.</span><span class="sxs-lookup"><span data-stu-id="bc69f-106">Be sure that only one user at a time modifies the Voice Routing configuration settings.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="bc69f-p101">Все ожидающие изменения необходимо публиковать одновременно, выполнив команду **Сохранить все**. Ожидающие изменения нельзя публиковать выборочно. Перед публикацией ожидающих изменений выполните команду **Проверка несохраненных изменений** и отмените изменения конфигурации, которые не требуется публиковать.</span><span class="sxs-lookup"><span data-stu-id="bc69f-p101">All pending changes must be published at the same time by running the **Commit all** command. You cannot selectively publish pending changes. Before you publish pending changes, run the **Review uncommitted changes** command and cancel any configuration changes that you do not want to publish.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bc69f-110">Если перейти со страницы в группе **Маршрутизация голосовой связи** до сохранения ожидающих изменений, изменения будут утрачены.</span><span class="sxs-lookup"><span data-stu-id="bc69f-110">If you navigate away from the pages in the **Voice Routing** group before committing pending changes, all pending changes will be lost.</span></span> <span data-ttu-id="bc69f-111">Тем не менее, текущую конфигурацию (включая все ожидающие изменения) можно экспортировать в файл конфигурации голосовой связи, а затем импортировать и опубликовать обновленную конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="bc69f-111">However, you can export the current configuration (including any pending changes) to a voice configuration file, and then import and publish the updated configuration.</span></span> <span data-ttu-id="bc69f-112">Дополнительные сведения см [Экспорт и импорт конфигурации маршрутизации голосовых данных файлов в Скайп для бизнеса](voice-route-configuration-import-export.md).</span><span class="sxs-lookup"><span data-stu-id="bc69f-112">For details, see [Export or import a voice route configuration file in Skype for Business](voice-route-configuration-import-export.md).</span></span> 
  
### <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a><span data-ttu-id="bc69f-113">Просмотр, публикация или отмена изменений конфигурации маршрутизации голосовых вызовов</span><span class="sxs-lookup"><span data-stu-id="bc69f-113">To review, publish, or cancel voice routing configuration changes</span></span>

1. <span data-ttu-id="bc69f-114">Войдите на компьютер в качестве члена группы RTCUniversalServerAdmins или роли администратора **CsVoiceAdministrator**, **CsServerAdministrator** или **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="bc69f-114">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="bc69f-115">Откройте Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="bc69f-115">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="bc69f-116">В левой области навигации щелкните элемент **Маршрутизация голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="bc69f-116">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="bc69f-117">Внесите необходимые изменения в параметры на каждой странице группы **Маршрутизация голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="bc69f-117">Make the configuration changes you want to the settings on each page of the **Voice Routing** group.</span></span>
    
5. <span data-ttu-id="bc69f-118">Чтобы просмотреть ожидающие изменения, не публикуя их, в меню **Сохранить** выберите пункт **Проверка несохраненных изменений**.</span><span class="sxs-lookup"><span data-stu-id="bc69f-118">To review pending changes without publishing them, select **Review uncommitted changes** from the **Commit** menu.</span></span>
    
6. <span data-ttu-id="bc69f-119">Чтобы отменить ожидающие изменения, выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="bc69f-119">If you want to cancel any of the pending changes, do one of the following:</span></span>
    
   - <span data-ttu-id="bc69f-120">В меню **Сохранить** выберите пункт **Отмена всех несохраненных изменений**.</span><span class="sxs-lookup"><span data-stu-id="bc69f-120">Select **Cancel all uncommitted changes** from the **Commit** menu.</span></span>
    
   - <span data-ttu-id="bc69f-121">Перейдите на вкладку страницы **Маршрутизация голосовой связи** с ожидающими изменениями, которые требуется отменить, выберите элемент с ожидающими изменениями, нажмите кнопку **Сохранить**, а затем **Отмена выбранных изменений**.</span><span class="sxs-lookup"><span data-stu-id="bc69f-121">Navigate to the tab of the **Voice Routing** page that has pending changes you want to cancel, select the item with the pending changes, click **Commit**, and then click **Cancel selected changes**.</span></span>
    
7. <span data-ttu-id="bc69f-122">Просмотрев все ожидающие изменения и отменив те, которые не требуется публиковать, нажмите кнопку **Сохранить**, а затем **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="bc69f-122">After you have reviewed all pending changes and canceled any that you do not want to publish, click **Commit**, and then click **Commit all**.</span></span>
    
8. <span data-ttu-id="bc69f-123">В диалоговом окне **Несохраненные параметры конфигурации голосовой связи**, в котором отображается список всех ожидающих изменений, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="bc69f-123">In the **Uncommitted Voice Configuration Settings** dialog box, which displays a list of all of the pending changes, click **OK**.</span></span> 
    
    <span data-ttu-id="bc69f-124">После сохранения изменений Скайп для панели управления сервера Business появится сообщение **успешно опубликована конфигурации маршрутизации голосовых данных** .</span><span class="sxs-lookup"><span data-stu-id="bc69f-124">When Skype for Business Server Control Panel has committed the changes, the **Successfully published voice routing configuration** message appears.</span></span>
    

