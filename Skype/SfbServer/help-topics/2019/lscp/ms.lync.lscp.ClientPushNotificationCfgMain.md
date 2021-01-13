---
title: Конфигурация push-уведомлений для мобильных клиентов
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientPushNotificationCfgMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: b7a85d75-9d36-4980-b669-2a009799d905
ROBOTS: NOINDEX, NOFOLLOW
description: Чтобы настроить push-уведомления Майкрософт и push-уведомления Apple, необходимо создать политику, определяющую тип требуемых push-уведомлений.
ms.openlocfilehash: 693b954fffbbce56a2d95ce29128482937b6fa05
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836679"
---
# <a name="mobile-client-push-notification-configuration"></a><span data-ttu-id="a70b3-103">Мобильный клиент: конфигурация push-уведомлений</span><span class="sxs-lookup"><span data-stu-id="a70b3-103">Mobile Client: Push Notification Configuration</span></span>
 
<span data-ttu-id="a70b3-104">Чтобы настроить **push-уведомления Майкрософт** и **push-уведомления Apple**, необходимо создать политику, определяющую тип требуемых push-уведомлений.</span><span class="sxs-lookup"><span data-stu-id="a70b3-104">To configure the **Microsoft push notifications** and **Apple push notifications**, you must create a policy to define which types of push notification you require.</span></span>
  
<span data-ttu-id="a70b3-p101">В главном окне конфигурации можно нажать кнопку **Обновить**, чтобы обновить и заново заполнить список политик. Поле поиска предоставляется для уточнения списка отображенных политик. По мере ввода искомого имени список политик автоматически сужается.</span><span class="sxs-lookup"><span data-stu-id="a70b3-p101">On the main configuration screen, you can click **Refresh** to refresh and re-populate the list of policies. A search box is provided for narrowing the list of displayed policies. As you type the name that you are searching for, the list of policies narrows automatically.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a70b3-108">Параметры политики, применяемые на уровне одной политики, могут переопределять параметры, применяемые на уровне другой политики.</span><span class="sxs-lookup"><span data-stu-id="a70b3-108">Policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="a70b3-109">Приоритет политики: политика пользователя (наиболее сильное влияние) переопределяет политику сайта, а политика сайта переопределяет глобальную политику (наименьшее влияние).</span><span class="sxs-lookup"><span data-stu-id="a70b3-109">Policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="a70b3-110">То есть, чем ближе параметр политики к объекту, на который она влияет, тем больше влияния она оказывает на объект.</span><span class="sxs-lookup"><span data-stu-id="a70b3-110">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> 
  
<span data-ttu-id="a70b3-111">Для создания и редактирования политик доступны две команды:</span><span class="sxs-lookup"><span data-stu-id="a70b3-111">Two selections are available for policy creation and editing:</span></span>
  
1. <span data-ttu-id="a70b3-p103">**Создать.** Щелкните, чтобы создать новую политику. Необходимо указать сайт для применения политики. Затем необходимо настроить параметры для push-уведомлений. Для **конфигурации push-уведомлений** политики можно создать только для тех сайтов, которые уже созданы.</span><span class="sxs-lookup"><span data-stu-id="a70b3-p103">**New**: Click to create a new policy. You must provide a site for the policy to apply to. You then configure the settings for the push notification. For **Push Notification Configuration**, you can only create policies for Sites that you have already created.</span></span>
    
2. <span data-ttu-id="a70b3-p104">**Правка.** Выберите политику и щелкните "Правка", чтобы выбрать действие из раскрывающегося списка. Редактировать можно только те сайты, которые уже созданы, или можно редактировать глобальную политику:</span><span class="sxs-lookup"><span data-stu-id="a70b3-p104">**Edit**: Select a policy and click Edit to select an action from a drop-down. You can only edit sites that you have already created or edit the Global policy:</span></span>
    
   - <span data-ttu-id="a70b3-p105">**Показать подробности…** Отображает сведения о текущей выбранной политике. Можно внести изменения в существующую политику.</span><span class="sxs-lookup"><span data-stu-id="a70b3-p105">**Show details…**: Displays information about the currently selected policy. You will be able to make changes to the existing policy.</span></span>
    
   - <span data-ttu-id="a70b3-120">**Выбрать все.** Если имеется несколько политик и требуется выбрать их все, щелкните "Выбрать все".</span><span class="sxs-lookup"><span data-stu-id="a70b3-120">**Select all**: If you have a number of policies and need to select all policies, click Select all</span></span>
    
   - <span data-ttu-id="a70b3-p106">**Удалить.** Удаляет выбранную политику. С помощью команд **Выбрать все** и **Удалить** можно удалить все политики.</span><span class="sxs-lookup"><span data-stu-id="a70b3-p106">**Delete**: Will remove the selected policy. Using **Select all** and **Delete** will remove all policies</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="a70b3-p107">Политику по умолчанию **Global** удалить невозможно. Если попытаться удалить ее, будет выдано уведомление о том, что параметрам в политике "Global" возвращены значения по умолчанию (то есть все параметры очищены), но политика не может быть удалена.</span><span class="sxs-lookup"><span data-stu-id="a70b3-p107">You cannot delete the default **Global** policy. If you attempt to delete it, you will be notified that the Global policy has been returned to the default values (that is, all settings are cleared), but the policy cannot be removed.</span></span>
  
<span data-ttu-id="a70b3-125">Создание новой политики или редактирование существующей политики связано с двумя действиями:</span><span class="sxs-lookup"><span data-stu-id="a70b3-125">Creating a new policy or editing an existing policy is associated with two actions:</span></span>
  
- <span data-ttu-id="a70b3-126">**Фиксация** Действие фиксации создает или обновляет политику и сохраняет изменения</span><span class="sxs-lookup"><span data-stu-id="a70b3-126">**Commit** The commit action creates or updates the policy and saves the changes</span></span>
    
- <span data-ttu-id="a70b3-127">**Отмена** Действие отмены отменяет все изменения, внесенные с момента последнего действия фиксации.</span><span class="sxs-lookup"><span data-stu-id="a70b3-127">**Cancel** The cancel action discards any changes that have been made since the last commit action.</span></span> <span data-ttu-id="a70b3-128">Если выполнить действие отмены, все изменения будут потеряны.</span><span class="sxs-lookup"><span data-stu-id="a70b3-128">If you cancel, any changes made will be lost.</span></span>
    
<span data-ttu-id="a70b3-p109">Для **конфигурации push-уведомлений** возможны два параметра. Эти параметры связаны со службами push-уведомлений для Майкрософт и для Apple. Push-уведомления для этих служб включаются посредством установки флажков рядом с именем службы. Флажок можно снять, выбрав его. После выбора необходимо либо зафиксировать изменения, либо отменить их. Если зафиксировать изменения, они будут сохранены в политику.</span><span class="sxs-lookup"><span data-stu-id="a70b3-p109">Two settings are possible for **Push Notification Configuration**. The settings are associated with the push notification services for Microsoft and for Apple. You enable push notification for either service by selecting the check box next to the name of the service. You can clear the check box by selecting it to clear it. Once you have made your selections, you either commit or cancel. Clicking commit will save the changes to the policy.</span></span>
  

