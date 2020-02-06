---
title: Настройка push-уведомлений для мобильных клиентов
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientPushNotificationCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7a85d75-9d36-4980-b669-2a009799d905
description: Чтобы настроить push-уведомления Майкрософт и Push-уведомления Apple, необходимо создать политику, чтобы определить, какие типы push-уведомлений вам нужны.
ms.openlocfilehash: 3fde99c3f026f87197492417cd10611d96f7e20e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822662"
---
# <a name="mobile-client-push-notification-configuration"></a><span data-ttu-id="d1c32-103">Мобильный клиент: конфигурация push-уведомлений</span><span class="sxs-lookup"><span data-stu-id="d1c32-103">Mobile Client: Push Notification Configuration</span></span>
 
<span data-ttu-id="d1c32-104">Чтобы настроить **Push-уведомления Майкрософт** и **Push-уведомления Apple**, необходимо создать политику, чтобы определить, какие типы push-уведомлений вам нужны.</span><span class="sxs-lookup"><span data-stu-id="d1c32-104">To configure the **Microsoft push notifications** and **Apple push notifications**, you must create a policy to define which types of push notification you require.</span></span>
  
<span data-ttu-id="d1c32-105">На главном экране настройки можно нажать кнопку **Обновить** , чтобы обновить список политик и повторно заполнить его.</span><span class="sxs-lookup"><span data-stu-id="d1c32-105">On the main configuration screen, you can click **Refresh** to refresh and re-populate the list of policies.</span></span> <span data-ttu-id="d1c32-106">Поле поиска предназначено для сужения списка политик, отображаемых в списке.</span><span class="sxs-lookup"><span data-stu-id="d1c32-106">A search box is provided for narrowing the list of displayed policies.</span></span> <span data-ttu-id="d1c32-107">По мере ввода имени, которое вы ищете, список политик сужается автоматически.</span><span class="sxs-lookup"><span data-stu-id="d1c32-107">As you type the name that you are searching for, the list of policies narrows automatically.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d1c32-p102">Параметры политики, которые применяются на уровне одной политики, могут переопределять параметры, применяемые на уровне другой политики. Приоритет политик: политика пользователя (самое большое влияние) переопределяет политику сайта, а политика сайта — глобальную политику (минимальное влияние). То есть, чем ближе параметр политики к объекту, на который она влияет, тем больше влияния она оказывает на объект.</span><span class="sxs-lookup"><span data-stu-id="d1c32-p102">Policy settings that are applied at one policy level can override settings that are applied at another policy level. Policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence). This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> 
  
<span data-ttu-id="d1c32-111">Для создания и редактирования политик доступны два выделения:</span><span class="sxs-lookup"><span data-stu-id="d1c32-111">Two selections are available for policy creation and editing:</span></span>
  
1. <span data-ttu-id="d1c32-112">**Создать**: щелкните, чтобы создать новую политику.</span><span class="sxs-lookup"><span data-stu-id="d1c32-112">**New**: Click to create a new policy.</span></span> <span data-ttu-id="d1c32-113">Необходимо указать сайт, к которому нужно применить политику.</span><span class="sxs-lookup"><span data-stu-id="d1c32-113">You must provide a site for the policy to apply to.</span></span> <span data-ttu-id="d1c32-114">Затем настройте параметры push-уведомлений.</span><span class="sxs-lookup"><span data-stu-id="d1c32-114">You then configure the settings for the push notification.</span></span> <span data-ttu-id="d1c32-115">Для **настройки push-уведомлений**вы можете создавать политики только для тех сайтов, которые вы уже создали.</span><span class="sxs-lookup"><span data-stu-id="d1c32-115">For **Push Notification Configuration**, you can only create policies for Sites that you have already created.</span></span>
    
2. <span data-ttu-id="d1c32-116">**Изменить**: выберите политику и нажмите кнопку изменить, чтобы выбрать действие из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="d1c32-116">**Edit**: Select a policy and click Edit to select an action from a drop-down.</span></span> <span data-ttu-id="d1c32-117">Вы можете редактировать только те сайты, которые вы уже создали или изменяют глобальную политику.</span><span class="sxs-lookup"><span data-stu-id="d1c32-117">You can only edit sites that you have already created or edit the Global policy:</span></span>
    
   - <span data-ttu-id="d1c32-118">**Показать подробности...**: выводит сведения о текущей выбранной политике.</span><span class="sxs-lookup"><span data-stu-id="d1c32-118">**Show details…**: Displays information about the currently selected policy.</span></span> <span data-ttu-id="d1c32-119">Вы сможете вносить изменения в существующую политику.</span><span class="sxs-lookup"><span data-stu-id="d1c32-119">You will be able to make changes to the existing policy.</span></span>
    
   - <span data-ttu-id="d1c32-120">**Выделить все**: если у вас несколько политик и вам нужно выбрать все политики, нажмите кнопку Выделить все.</span><span class="sxs-lookup"><span data-stu-id="d1c32-120">**Select all**: If you have a number of policies and need to select all policies, click Select all</span></span>
    
   - <span data-ttu-id="d1c32-121">**Delete (удалить**): удалит выбранную политику.</span><span class="sxs-lookup"><span data-stu-id="d1c32-121">**Delete**: Will remove the selected policy.</span></span> <span data-ttu-id="d1c32-122">Использование команды " **выделить все** " и " **Удалить** " приведет к удалению всех политик</span><span class="sxs-lookup"><span data-stu-id="d1c32-122">Using **Select all** and **Delete** will remove all policies</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="d1c32-123">Вы не можете удалить **глобальную** политику, используемую по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d1c32-123">You cannot delete the default **Global** policy.</span></span> <span data-ttu-id="d1c32-124">Если вы попытаетесь удалить его, вы будете уведомлены о том, что глобальная политика возвращена к значениям по умолчанию (то есть, все параметры очищены), но политика не может быть удалена.</span><span class="sxs-lookup"><span data-stu-id="d1c32-124">If you attempt to delete it, you will be notified that the Global policy has been returned to the default values (that is, all settings are cleared), but the policy cannot be removed.</span></span>
  
<span data-ttu-id="d1c32-125">Создание новой политики или изменение существующей политики связано с двумя действиями:</span><span class="sxs-lookup"><span data-stu-id="d1c32-125">Creating a new policy or editing an existing policy is associated with two actions:</span></span>
  
- <span data-ttu-id="d1c32-126">**Commit (фиксация** ) Действие Commit создает или обновляет политику и сохраняет изменения.</span><span class="sxs-lookup"><span data-stu-id="d1c32-126">**Commit** The commit action creates or updates the policy and saves the changes</span></span>
    
- <span data-ttu-id="d1c32-127">**Отмена** Действие отмены отменяет все изменения, внесенные с момента последнего действия фиксации.</span><span class="sxs-lookup"><span data-stu-id="d1c32-127">**Cancel** The cancel action discards any changes that have been made since the last commit action.</span></span> <span data-ttu-id="d1c32-128">При отмене все внесенные изменения будут потеряны.</span><span class="sxs-lookup"><span data-stu-id="d1c32-128">If you cancel, any changes made will be lost.</span></span>
    
<span data-ttu-id="d1c32-129">Для **настройки push-уведомлений можно настроить**два параметра.</span><span class="sxs-lookup"><span data-stu-id="d1c32-129">Two settings are possible for **Push Notification Configuration**.</span></span> <span data-ttu-id="d1c32-130">Эти параметры связаны со службами push-уведомлений для Microsoft и Apple.</span><span class="sxs-lookup"><span data-stu-id="d1c32-130">The settings are associated with the push notification services for Microsoft and for Apple.</span></span> <span data-ttu-id="d1c32-131">Вы включаете push-уведомления для каждой из служб, установив флажок рядом с ее названием.</span><span class="sxs-lookup"><span data-stu-id="d1c32-131">You enable push notification for either service by selecting the check box next to the name of the service.</span></span> <span data-ttu-id="d1c32-132">Вы можете снять флажок, щелкнув его, чтобы снять его.</span><span class="sxs-lookup"><span data-stu-id="d1c32-132">You can clear the check box by selecting it to clear it.</span></span> <span data-ttu-id="d1c32-133">После того как вы сделали выбор, вы зафиксируете или отмените их.</span><span class="sxs-lookup"><span data-stu-id="d1c32-133">Once you have made your selections, you either commit or cancel.</span></span> <span data-ttu-id="d1c32-134">Нажатие кнопки "завершить" сохранит изменения в политике.</span><span class="sxs-lookup"><span data-stu-id="d1c32-134">Clicking commit will save the changes to the policy.</span></span>
  

