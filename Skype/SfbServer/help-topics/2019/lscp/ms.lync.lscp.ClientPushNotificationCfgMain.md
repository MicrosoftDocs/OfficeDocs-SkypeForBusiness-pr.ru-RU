---
title: Мобильный клиент конфигурации Push-уведомлений
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientPushNotificationCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7a85d75-9d36-4980-b669-2a009799d905
description: Чтобы настроить push-уведомления Майкрософт и push-уведомления Apple, необходимо создать политику, определяющую требуют типы push-уведомлений.
ms.openlocfilehash: 5570ab2f25359d847c6b594f36f865a1c37e170e
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/20/2018
ms.locfileid: "19971244"
---
# <a name="mobile-client-push-notification-configuration"></a><span data-ttu-id="c9187-103">Мобильный клиент: Конфигурация Push-уведомлений</span><span class="sxs-lookup"><span data-stu-id="c9187-103">Mobile Client: Push Notification Configuration</span></span>
 
<span data-ttu-id="c9187-104">Чтобы настроить **push-уведомления Майкрософт** и **push-уведомления Apple**, необходимо создать политику, определяющую типы требуемых push-уведомлений.</span><span class="sxs-lookup"><span data-stu-id="c9187-104">To configure the **Microsoft push notifications** and **Apple push notifications**, you must create a policy to define which types of push notification you require.</span></span>
  
<span data-ttu-id="c9187-105">На экране основной конфигурации нажмите кнопку **Обновить** , чтобы обновить и повторного заполнения списка политик.</span><span class="sxs-lookup"><span data-stu-id="c9187-105">On the main configuration screen, you can click **Refresh** to refresh and re-populate the list of policies.</span></span> <span data-ttu-id="c9187-106">Поле поиска обеспечивает сужение списка отображаемых политик.</span><span class="sxs-lookup"><span data-stu-id="c9187-106">A search box is provided for narrowing the list of displayed policies.</span></span> <span data-ttu-id="c9187-107">При вводе имя, которое выполняется поиск списка политик ограничивает автоматически.</span><span class="sxs-lookup"><span data-stu-id="c9187-107">As you type the name that you are searching for, the list of policies narrows automatically.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c9187-p102">Параметры политики, которые применяются на уровне одной политики, могут переопределять параметры, применяемые на уровне другой политики. Приоритет политик: политика пользователя (самое большое влияние) переопределяет политику сайта, а политика сайта — глобальную политику (минимальное влияние). То есть, чем ближе параметр политики к объекту, на который она влияет, тем больше влияния она оказывает на объект.</span><span class="sxs-lookup"><span data-stu-id="c9187-p102">Policy settings that are applied at one policy level can override settings that are applied at another policy level. Policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence). This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> 
  
<span data-ttu-id="c9187-111">Для создания и редактирования политик доступны две команды:</span><span class="sxs-lookup"><span data-stu-id="c9187-111">Two selections are available for policy creation and editing:</span></span>
  
1. <span data-ttu-id="c9187-112">**New**: щелкните, чтобы создать новую политику.</span><span class="sxs-lookup"><span data-stu-id="c9187-112">**New**: Click to create a new policy.</span></span> <span data-ttu-id="c9187-113">Необходимо предоставить сайта для политики для применения к.</span><span class="sxs-lookup"><span data-stu-id="c9187-113">You must provide a site for the policy to apply to.</span></span> <span data-ttu-id="c9187-114">Настройте параметры для push-уведомлений.</span><span class="sxs-lookup"><span data-stu-id="c9187-114">You then configure the settings for the push notification.</span></span> <span data-ttu-id="c9187-115">Для **Настройка Push-уведомлений**можно только создать политик для сайтов, которые уже созданы.</span><span class="sxs-lookup"><span data-stu-id="c9187-115">For **Push Notification Configuration**, you can only create policies for Sites that you have already created.</span></span>
    
2. <span data-ttu-id="c9187-116">**Изменение**: выберите политику и нажмите кнопку Изменить, чтобы выберите нужное действие из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="c9187-116">**Edit**: Select a policy and click Edit to select an action from a drop-down.</span></span> <span data-ttu-id="c9187-117">Можно изменять только создать или изменить глобальную политику сайтов:</span><span class="sxs-lookup"><span data-stu-id="c9187-117">You can only edit sites that you have already created or edit the Global policy:</span></span>
    
  - <span data-ttu-id="c9187-118">**Показать подробности**: отображаются сведения о политике выделенный в текущий момент.</span><span class="sxs-lookup"><span data-stu-id="c9187-118">**Show details…**: Displays information about the currently selected policy.</span></span> <span data-ttu-id="c9187-119">Вы сможете вносить изменения в существующую политику.</span><span class="sxs-lookup"><span data-stu-id="c9187-119">You will be able to make changes to the existing policy.</span></span>
    
  - <span data-ttu-id="c9187-120">**Выберите все**: Если количество политик и выберите все политики, нажмите кнопку Выбрать все</span><span class="sxs-lookup"><span data-stu-id="c9187-120">**Select all**: If you have a number of policies and need to select all policies, click Select all</span></span>
    
  - <span data-ttu-id="c9187-121">**Удаление**: приведет к удалению выбранной политики.</span><span class="sxs-lookup"><span data-stu-id="c9187-121">**Delete**: Will remove the selected policy.</span></span> <span data-ttu-id="c9187-122">С помощью **Выбрать все** и **удалите** будут удалены все политики</span><span class="sxs-lookup"><span data-stu-id="c9187-122">Using **Select all** and **Delete** will remove all policies</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c9187-123">Не удается удалить **глобальную** политику по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c9187-123">You cannot delete the default **Global** policy.</span></span> <span data-ttu-id="c9187-124">При попытке удалить ее, вы получите уведомление, что глобальную политику возвращенных значений по умолчанию (то есть, все параметры очищаются), но политика не может быть удалена.</span><span class="sxs-lookup"><span data-stu-id="c9187-124">If you attempt to delete it, you will be notified that the Global policy has been returned to the default values (that is, all settings are cleared), but the policy cannot be removed.</span></span>
  
<span data-ttu-id="c9187-125">Создание новой политики или редактирование существующей политики связано с двумя действиями:</span><span class="sxs-lookup"><span data-stu-id="c9187-125">Creating a new policy or editing an existing policy is associated with two actions:</span></span>
  
- <span data-ttu-id="c9187-126">**Фиксация** Зафиксировать действие фиксации создает или обновляет политику и сохраняет изменения</span><span class="sxs-lookup"><span data-stu-id="c9187-126">**Commit** The commit action creates or updates the policy and saves the changes</span></span>
    
- <span data-ttu-id="c9187-127">**Отмена** Действие "Отмена" отменяет все изменения, внесенные с момента последнего действия зафиксировать.</span><span class="sxs-lookup"><span data-stu-id="c9187-127">**Cancel** The cancel action discards any changes that have been made since the last commit action.</span></span> <span data-ttu-id="c9187-128">Если вы отменить все изменения, внесенные будут потеряны.</span><span class="sxs-lookup"><span data-stu-id="c9187-128">If you cancel, any changes made will be lost.</span></span>
    
<span data-ttu-id="c9187-129">Возможны два параметра для **Настройка Push-уведомлений**.</span><span class="sxs-lookup"><span data-stu-id="c9187-129">Two settings are possible for **Push Notification Configuration**.</span></span> <span data-ttu-id="c9187-130">Настройки, связанные с служб push-уведомлений для Microsoft и Apple.</span><span class="sxs-lookup"><span data-stu-id="c9187-130">The settings are associated with the push notification services for Microsoft and for Apple.</span></span> <span data-ttu-id="c9187-131">Включение push-уведомлений для любого из службы, установив флажок рядом с именем службы.</span><span class="sxs-lookup"><span data-stu-id="c9187-131">You enable push notification for either service by selecting the check box next to the name of the service.</span></span> <span data-ttu-id="c9187-132">Флажок снят, выбрав его снимите его.</span><span class="sxs-lookup"><span data-stu-id="c9187-132">You can clear the check box by selecting it to clear it.</span></span> <span data-ttu-id="c9187-133">После выбора вы завершении или Отмена.</span><span class="sxs-lookup"><span data-stu-id="c9187-133">Once you have made your selections, you either commit or cancel.</span></span> <span data-ttu-id="c9187-134">Нажмите кнопку зафиксировать будет сохранить изменения в политике.</span><span class="sxs-lookup"><span data-stu-id="c9187-134">Clicking commit will save the changes to the policy.</span></span>
  

