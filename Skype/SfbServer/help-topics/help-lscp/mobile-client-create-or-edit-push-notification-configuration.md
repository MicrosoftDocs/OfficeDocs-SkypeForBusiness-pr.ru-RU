---
title: Создание или изменение конфигурации push-уведомлений на мобильном клиенте
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientPushNotificationCfgEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb39af60-c999-42fb-9538-0bd87098f508
description: Push-уведомления и система PNCH — это два компонента для работы с мобильными устройствами. Push-уведомления — это процесс, в котором уведомления отправляются в систему PNCH. Сообщение удерживается в системе до тех пор, пока оно не сможет быть доставлено на мобильный клиент или не закончится срок его действия.
ms.openlocfilehash: ca302e0dbdde2c1628abc6c0257ee807f6f152a8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822672"
---
# <a name="mobile-client-create-or-edit-push-notification-configuration"></a><span data-ttu-id="6293b-105">Мобильный клиент: создание или редактирование конфигурации push-уведомлений</span><span class="sxs-lookup"><span data-stu-id="6293b-105">Mobile Client: Create or Edit Push Notification Configuration</span></span>
 
<span data-ttu-id="6293b-p102">Push-уведомления и система PNCH — это два компонента для работы с мобильными устройствами. Push-уведомления — это процесс, в котором уведомления отправляются в систему PNCH. Сообщение удерживается в системе до тех пор, пока оно не сможет быть доставлено на мобильный клиент или не закончится срок его действия.</span><span class="sxs-lookup"><span data-stu-id="6293b-p102">Push Notification and the Push Notification Clearing House (PNCH) are two key parts of the mobility feature. Push notification is the process where a message is sent to the PNCH. The message is held here until it can be delivered to the mobile client, or the timeout period expires.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="6293b-109">Срок действия задается в системе PNCH и не настраивается пользователем или администратором развертывания.</span><span class="sxs-lookup"><span data-stu-id="6293b-109">The time period is set at the Push Notification Clearing House and is not configurable by the user or the administrator of your deployment.</span></span> 
  
<span data-ttu-id="6293b-110">Чтобы включить push-уведомления, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="6293b-110">To enable Push Notification, you do the following:</span></span>
  
1. <span data-ttu-id="6293b-p103">**Область.** Обратите внимание на область действия для этой политики. Она может быть **глобальной**, тогда она применяется ко всем пользователям в развертывании, или иметь значение **Сайт**, тогда она включает только пользователей, назначенных домашним серверам в заданном сайте.</span><span class="sxs-lookup"><span data-stu-id="6293b-p103">**Scope:** Note the scope for this policy. It can either be **Global**, which applies to all users in this deployment, or **Site**, which is only users assigned to home servers in the specified site.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="6293b-p104">Параметры политики, которые применяются на уровне одной политики, могут переопределять параметры, применяемые на уровне другой политики. Приоритет политик: политика пользователя (самое большое влияние) переопределяет политику сайта, а политика сайта — глобальную политику (минимальное влияние). То есть, чем ближе параметр политики к объекту, на который она влияет, тем больше влияния она оказывает на объект.</span><span class="sxs-lookup"><span data-stu-id="6293b-p104">Policy settings that are applied at one policy level can override settings that are applied at another policy level. Policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence). This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> 
  
2. <span data-ttu-id="6293b-116">Выберите, какую службу push-уведомлений следует включить, установив один из флажков:</span><span class="sxs-lookup"><span data-stu-id="6293b-116">Select which push notification services you want to enable by clicking the check box for:</span></span>
    
   - <span data-ttu-id="6293b-117">**Включить push-уведомление Майкрософт** включит на облачном ПНЧ для Windows Phone с помощью приложения Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="6293b-117">**Enable Microsoft push notification** will enable the push notification to the cloud-based PNCH for Windows Phone with the Skype for Business app</span></span>
    
   - <span data-ttu-id="6293b-118">**Включение push-уведомлений Apple** для устройств под управлением iOS (например, iPhone, iPad) и использования приложения Skype для бизнеса: Push-уведомление в Apple ПНЧ.</span><span class="sxs-lookup"><span data-stu-id="6293b-118">**Enable Apple push notification** will enable the push notification to the Apple PNCH for devices running Apple's iOS (for example, iPhone, iPad) and using the Skype for Business app</span></span>
    
3. <span data-ttu-id="6293b-p105">Завершив редактирование политики, нажмите кнопку **Исполнить**, чтобы сохранить изменения. Если требуется удалить выполненные изменения, нажмите кнопку **Отмена**. В этом случае изменения не будут сохранены в политику.</span><span class="sxs-lookup"><span data-stu-id="6293b-p105">When you have completed the edits of the policy, click **Commit** to save your changes. If you need to delete the changes you have made, select **Cancel**. No changes will be saved to the policy.</span></span>
    

