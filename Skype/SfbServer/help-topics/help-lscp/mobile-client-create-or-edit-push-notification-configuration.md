---
title: Настройка создания или изменения push-уведомлений мобильным клиентом
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Push-уведомления и PNCH являются двумя ключевыми компонентами функции мобильности. Push-уведомления — это процесс, в котором уведомления отправляются в систему PNCH. Сообщение удерживается в системе до тех пор, пока оно не сможет быть доставлено на мобильный клиент или не закончится срок его действия.
ms.openlocfilehash: 0cd2b17f764891dbb1ad89ada27f6be0b6246ba0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810889"
---
# <a name="mobile-client-create-or-edit-push-notification-configuration"></a><span data-ttu-id="caad2-105">Мобильный клиент: создание или редактирование конфигурации push-уведомлений</span><span class="sxs-lookup"><span data-stu-id="caad2-105">Mobile Client: Create or Edit Push Notification Configuration</span></span>
 
<span data-ttu-id="caad2-106">Push-уведомления и PNCH являются двумя ключевыми компонентами функции мобильности.</span><span class="sxs-lookup"><span data-stu-id="caad2-106">Push Notification and the Push Notification Clearing House (PNCH) are two key parts of the mobility feature.</span></span> <span data-ttu-id="caad2-107">Push-уведомления — это процесс, в котором уведомления отправляются в систему PNCH.</span><span class="sxs-lookup"><span data-stu-id="caad2-107">Push notification is the process where a message is sent to the PNCH.</span></span> <span data-ttu-id="caad2-108">Сообщение удерживается в системе до тех пор, пока оно не сможет быть доставлено на мобильный клиент или не закончится срок его действия.</span><span class="sxs-lookup"><span data-stu-id="caad2-108">The message is held here until it can be delivered to the mobile client, or the timeout period expires.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="caad2-109">Срок действия задается в системе PNCH и не настраивается пользователем или администратором развертывания.</span><span class="sxs-lookup"><span data-stu-id="caad2-109">The time period is set at the Push Notification Clearing House and is not configurable by the user or the administrator of your deployment.</span></span> 
  
<span data-ttu-id="caad2-110">Чтобы включить push-уведомления, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="caad2-110">To enable Push Notification, you do the following:</span></span>
  
1. <span data-ttu-id="caad2-111">**Область действия:** Обратите внимание на область применения этой политики.</span><span class="sxs-lookup"><span data-stu-id="caad2-111">**Scope:** Note the scope for this policy.</span></span> <span data-ttu-id="caad2-112">Это может **быть**"Глобальный", который применяется ко всем пользователям в данном развертывании, или "Сайт", который назначен только домашним серверам на указанном сайте.</span><span class="sxs-lookup"><span data-stu-id="caad2-112">It can either be **Global**, which applies to all users in this deployment, or **Site**, which is only users assigned to home servers in the specified site.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="caad2-113">Параметры политики, применяемые на уровне одной политики, могут переопределять параметры, применяемые на уровне другой политики.</span><span class="sxs-lookup"><span data-stu-id="caad2-113">Policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="caad2-114">Приоритет политики: политика пользователя (наиболее сильное влияние) переопределяет политику сайта, а политика сайта переопределяет глобальную политику (наименьшее влияние).</span><span class="sxs-lookup"><span data-stu-id="caad2-114">Policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="caad2-115">То есть, чем ближе параметр политики к объекту, на который она влияет, тем больше влияния она оказывает на объект.</span><span class="sxs-lookup"><span data-stu-id="caad2-115">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> 
  
2. <span data-ttu-id="caad2-116">Выберите, какую службу push-уведомлений следует включить, установив один из флажков:</span><span class="sxs-lookup"><span data-stu-id="caad2-116">Select which push notification services you want to enable by clicking the check box for:</span></span>
    
   - <span data-ttu-id="caad2-117">**Включить push-уведомления** Майкрософт включает push-уведомления для облачной PNCH для Windows Phone с помощью приложения Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="caad2-117">**Enable Microsoft push notification** will enable the push notification to the cloud-based PNCH for Windows Phone with the Skype for Business app</span></span>
    
   - <span data-ttu-id="caad2-118">**Включить push-уведомления** Apple включает push-уведомления в Apple PNCH для устройств под управлением Apple iOS (например, iPhone, iPad) и с помощью приложения Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="caad2-118">**Enable Apple push notification** will enable the push notification to the Apple PNCH for devices running Apple's iOS (for example, iPhone, iPad) and using the Skype for Business app</span></span>
    
3. <span data-ttu-id="caad2-p105">Когда редактирование политики завершено, нажмите кнопку **Зафиксировать**, чтобы сохранить изменения. Если требуется удалить выполненные изменения, нажмите кнопку **Отмена**. В этом случае изменения не будут сохранены в политику.</span><span class="sxs-lookup"><span data-stu-id="caad2-p105">When you have completed the edits of the policy, click **Commit** to save your changes. If you need to delete the changes you have made, select **Cancel**. No changes will be saved to the policy.</span></span>
    

