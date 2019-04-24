---
title: Гибридное развертывание системы комнат Skype
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: Прочтите этот раздел, чтобы узнать, как развертывание системы Скайп помещения в гибридной среде.
ms.openlocfilehash: 40cbcd7cd95b6a5dc7542f913fe7599bedc7eb85
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32219453"
---
# <a name="skype-room-system-hybrid-deployments"></a><span data-ttu-id="9c50f-103">Гибридное развертывание системы комнат Skype</span><span class="sxs-lookup"><span data-stu-id="9c50f-103">Skype Room System hybrid deployments</span></span>

<span data-ttu-id="9c50f-104">Прочтите этот раздел, чтобы узнать, как развертывание системы Скайп помещения в гибридной среде.</span><span class="sxs-lookup"><span data-stu-id="9c50f-104">Read this topic to learn how to deploy Skype Room System in a hybrid environment.</span></span>
  
## <a name="hybrid-deployments"></a><span data-ttu-id="9c50f-105">Гибридное развертывание</span><span class="sxs-lookup"><span data-stu-id="9c50f-105">Hybrid deployments</span></span>

<span data-ttu-id="9c50f-106">Если топология имеет Скайп для Business Server и Exchange Online и разместить ресурсов Скайп комнаты системных почтовых ящиков на Exchange Online, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="9c50f-106">Follow these steps if your topology has Skype for Business Server and Exchange Online, and you want to host the Skype Room System resource mailbox on Exchange Online.</span></span> <span data-ttu-id="9c50f-107">This section also covers a hybrid scenario where you have both Exchange Online and Exchange Server deployed.</span><span class="sxs-lookup"><span data-stu-id="9c50f-107">This section also covers a hybrid scenario where you have both Exchange Online and Exchange Server deployed.</span></span>
  
<span data-ttu-id="9c50f-108">Для демонстрационных целей мы используем LyncSample.com для локального домена и LyncSample.ccstp.net для Интернет-домена.</span><span class="sxs-lookup"><span data-stu-id="9c50f-108">For illustrative purpose, we use LyncSample.com for the on-premises domain and LyncSample.ccstp.net for the online domain.</span></span>
  
1. <span data-ttu-id="9c50f-109">Создание почтового ящика ресурсов в центре администрирования Exchange (LyncSample.ccsctp.net) с помощью подключения к консоли управления Exchange Online, как описано в Exchange Online подготовки.</span><span class="sxs-lookup"><span data-stu-id="9c50f-109">Create a resource mailbox in Exchange admin center (LyncSample.ccsctp.net) by connecting to the Exchange Online Management shell as described in Exchange Online Provisioning.</span></span>
    
   ```
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    <span data-ttu-id="9c50f-110">Вы можете проверить подключения OWA, с использованием lrstest5@LyncSample.ccsctp.net для входа.</span><span class="sxs-lookup"><span data-stu-id="9c50f-110">You can verify OWA connectivity using lrstest5@LyncSample.ccsctp.net to log in.</span></span>
    
2. <span data-ttu-id="9c50f-111">В центре администрирования Office 365 Exchange добавьте lrstest5@LyncSample.com адрес электронной почты (на prem домена) и его настройка в качестве обратный адрес.</span><span class="sxs-lookup"><span data-stu-id="9c50f-111">In the Office 365 Exchange admin center, add an e-mail address lrstest5@LyncSample.com (on-prem domain) and set it as the reply address.</span></span>
    
3. <span data-ttu-id="9c50f-112">Создание lrstest5@LyncSample.com пользователя Active Directory на prem, равным lrstest5@LyncSample.com адрес электронной почты и задать целевой адрес lrstest5@LyncSample.com.</span><span class="sxs-lookup"><span data-stu-id="9c50f-112">Create an on-prem Active Directory user lrstest5@LyncSample.com, set the e-mail address to lrstest5@LyncSample.com, and set the target address to lrstest5@LyncSample.com.</span></span>
    
4. <span data-ttu-id="9c50f-113">Запуск синхронизации службы каталогов и после завершения синхронизации убедитесь, что пользователи объединить в AAD и, что не могут изменить свойства на ресурсах получателя в центре администрирования Exchange Office 365.</span><span class="sxs-lookup"><span data-stu-id="9c50f-113">Trigger directory synchronization, and, after synchronization is complete, verify that users merge in AAD and that you are not able to change properties in recipient's resources in the Office365 Exchange admin center.</span></span>
    
5. <span data-ttu-id="9c50f-114">Проверка возможности подключения к OWA с помощью lrstest5@LyncSample.com.</span><span class="sxs-lookup"><span data-stu-id="9c50f-114">Verify OWA connectivity using lrstest5@LyncSample.com.</span></span> <span data-ttu-id="9c50f-115">(Ранее, проверено ли OWA подключения с использованием online домена.)</span><span class="sxs-lookup"><span data-stu-id="9c50f-115">(Earlier, you verified OWA connectivity using the online domain.)</span></span>
    
    <span data-ttu-id="9c50f-p103">После создания почтового ящика для его настройки можно использовать Set-CalendarProcessing в командной консоли Exchange Online. Для получения дополнительных сведений см. шаги 3-6 в разделе "Локальные развертывания с одиночным лесом".</span><span class="sxs-lookup"><span data-stu-id="9c50f-p103">After creating the mailbox, you can use Set-CalendarProcessing on the Exchange Online Management Shell to configure the mailbox. Refer to steps 3 through 6 under Single Forest On-prem Deployments for more details.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="9c50f-118">Если у вас есть гибридной среде с Exchange Server и Exchange Online, перейдите к командной консоли Exchange и Enable-RemoteMailbox lrstest5@LyncSample.mail.ccsctp.net - RemoteRoutingAddress lrstest5@LyncSample.com-комнаты.</span><span class="sxs-lookup"><span data-stu-id="9c50f-118">If you have a hybrid environment with Exchange Server and Exchange Online, go to the Exchange Management Shell and Enable-RemoteMailbox lrstest5@LyncSample.com -RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net -Room.</span></span> <span data-ttu-id="9c50f-119">Запустите синхронизацию с каталогом.</span><span class="sxs-lookup"><span data-stu-id="9c50f-119">Then trigger Directory Synchronization.</span></span> 
  
    <span data-ttu-id="9c50f-120">Если требуется разместить Скайп комнаты системных почтовых ящиков в Exchange Online, эти действия Командная консоль Exchange не являются обязательными и можно перейти к шагу 6.</span><span class="sxs-lookup"><span data-stu-id="9c50f-120">If you want to host the Skype Room System mailbox in Exchange Online, these Exchange Management Shell steps are not required and you can proceed to step 6.</span></span>
    
6. <span data-ttu-id="9c50f-121">Включение Скайп комнаты системную учетную запись для Скайп для бизнеса, выполнив следующий командлет на Скайп оболочки управления бизнеса:</span><span class="sxs-lookup"><span data-stu-id="9c50f-121">Enable the Skype Room System account for Skype for Business by running the following cmdlet on Skype for Business Management Shell:</span></span>
    
   ```
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> <span data-ttu-id="9c50f-122">При наличии Скайп для бизнеса в Интернет вместо Скайп для Business Server в вышеприведенном сценарии, затем после заполнения почтовому ящику Exchange временного Скайп для бизнеса учетной записи, как описано в Скайп для бизнеса Online подготовки.</span><span class="sxs-lookup"><span data-stu-id="9c50f-122">If you have Skype for Business Online instead of Skype for Business Server in the above scenario, then after provisioning the Exchange resource mailbox, provision a Skype for Business account as described in Skype for Business Online Provisioning.</span></span> 
  

