---
title: Создание или редактирование конфигурации Push-уведомления мобильного клиента
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientPushNotificationCfgEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb39af60-c999-42fb-9538-0bd87098f508
description: Push-уведомления и система PNCH — это два компонента для работы с мобильными устройствами. Push-уведомления — это процесс, в котором уведомления отправляются в систему PNCH. Сообщение удерживается в системе до тех пор, пока оно не сможет быть доставлено на мобильный клиент или не закончится срок его действия.
ms.openlocfilehash: 53583e59261e369aa11c8bac12f5f5b5eaf4a8dc
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/24/2018
---
# <a name="mobile-client-create-or-edit-push-notification-configuration"></a><span data-ttu-id="7bdb5-105">Мобильный клиент: создание или редактирование конфигурации push-уведомлений</span><span class="sxs-lookup"><span data-stu-id="7bdb5-105">Mobile Client: Create or Edit Push Notification Configuration</span></span>
 
<span data-ttu-id="7bdb5-p102">Push-уведомления и система PNCH — это два компонента для работы с мобильными устройствами. Push-уведомления — это процесс, в котором уведомления отправляются в систему PNCH. Сообщение удерживается в системе до тех пор, пока оно не сможет быть доставлено на мобильный клиент или не закончится срок его действия.</span><span class="sxs-lookup"><span data-stu-id="7bdb5-p102">Push Notification and the Push Notification Clearing House (PNCH) are two key parts of the mobility feature. Push notification is the process where a message is sent to the PNCH. The message is held here until it can be delivered to the mobile client, or the timeout period expires.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="7bdb5-109">Срок действия задается в системе PNCH и не настраивается пользователем или администратором развертывания.</span><span class="sxs-lookup"><span data-stu-id="7bdb5-109">The time period is set at the Push Notification Clearing House and is not configurable by the user or the administrator of your deployment.</span></span> 
  
<span data-ttu-id="7bdb5-110">Чтобы включить push-уведомления, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="7bdb5-110">To enable Push Notification, you do the following:</span></span>
  
1. <span data-ttu-id="7bdb5-p103">**Область.** Обратите внимание на область действия для этой политики. Она может быть **глобальной**, тогда она применяется ко всем пользователям в развертывании, или иметь значение **Сайт**, тогда она включает только пользователей, назначенных домашним серверам в заданном сайте.</span><span class="sxs-lookup"><span data-stu-id="7bdb5-p103">**Scope:** Note the scope for this policy. It can either be **Global**, which applies to all users in this deployment, or **Site**, which is only users assigned to home servers in the specified site.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="7bdb5-p104">Параметры политики, которые применяются на уровне одной политики, могут переопределять параметры, применяемые на уровне другой политики. Приоритет политик: политика пользователя (самое большое влияние) переопределяет политику сайта, а политика сайта — глобальную политику (минимальное влияние). То есть, чем ближе параметр политики к объекту, на который она влияет, тем больше влияния она оказывает на объект.</span><span class="sxs-lookup"><span data-stu-id="7bdb5-p104">Policy settings that are applied at one policy level can override settings that are applied at another policy level. Policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence). This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> 
  
2. <span data-ttu-id="7bdb5-116">Выберите, какую службу push-уведомлений следует включить, установив один из флажков:</span><span class="sxs-lookup"><span data-stu-id="7bdb5-116">Select which push notification services you want to enable by clicking the check box for:</span></span>
    
  - <span data-ttu-id="7bdb5-117">Включает **push-уведомления Майкрософт включить** push-уведомления для облачных PNCH для Windows Phone с Скайп для бизнес-приложения</span><span class="sxs-lookup"><span data-stu-id="7bdb5-117">**Enable Microsoft push notification** will enable the push notification to the cloud-based PNCH for Windows Phone with the Skype for Business app</span></span>
    
  - <span data-ttu-id="7bdb5-118">**Включение push-уведомления** будет включить push-уведомления для PNCH Apple для устройств под управлением Apple iOS (например, iPhone, iPad) и с помощью Скайп для бизнес-приложения</span><span class="sxs-lookup"><span data-stu-id="7bdb5-118">**Enable Apple push notification** will enable the push notification to the Apple PNCH for devices running Apple's iOS (for example, iPhone, iPad) and using the Skype for Business app</span></span>
    
3. <span data-ttu-id="7bdb5-p105">Завершив редактирование политики, нажмите кнопку **Исполнить**, чтобы сохранить изменения. Если требуется удалить выполненные изменения, нажмите кнопку **Отмена**. В этом случае изменения не будут сохранены в политику.</span><span class="sxs-lookup"><span data-stu-id="7bdb5-p105">When you have completed the edits of the policy, click **Commit** to save your changes. If you need to delete the changes you have made, select **Cancel**. No changes will be saved to the policy.</span></span>
    

