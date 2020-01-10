---
title: Гибридное развертывание системы комнат Skype
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: В этой статье рассказывается о том, как развертывать системы комнат Skype в гибридной среде.
ms.openlocfilehash: f6364f7bb96ddf2b25aaaef2a341fce5b71372f5
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003499"
---
# <a name="skype-room-system-hybrid-deployments"></a><span data-ttu-id="81e21-103">Гибридное развертывание системы комнат Skype</span><span class="sxs-lookup"><span data-stu-id="81e21-103">Skype Room System hybrid deployments</span></span>

<span data-ttu-id="81e21-104">В этой статье рассказывается о том, как развертывать системы комнат Skype в гибридной среде.</span><span class="sxs-lookup"><span data-stu-id="81e21-104">Read this topic to learn how to deploy Skype Room System in a hybrid environment.</span></span>
  
## <a name="hybrid-deployments"></a><span data-ttu-id="81e21-105">Гибридное развертывание</span><span class="sxs-lookup"><span data-stu-id="81e21-105">Hybrid deployments</span></span>

<span data-ttu-id="81e21-106">Если в вашей топологии есть Skype для бизнеса Server и Exchange Online, а вы хотите разместить почтовый ящик системы комнаты комнат Skype на Exchange Online, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="81e21-106">Follow these steps if your topology has Skype for Business Server and Exchange Online, and you want to host the Skype Room System resource mailbox on Exchange Online.</span></span> <span data-ttu-id="81e21-107">This section also covers a hybrid scenario where you have both Exchange Online and Exchange Server deployed.</span><span class="sxs-lookup"><span data-stu-id="81e21-107">This section also covers a hybrid scenario where you have both Exchange Online and Exchange Server deployed.</span></span>
  
<span data-ttu-id="81e21-108">Для наглядной цели мы используем LyncSample.com для локального домена и LyncSample.ccstp.net для домена в сети.</span><span class="sxs-lookup"><span data-stu-id="81e21-108">For illustrative purpose, we use LyncSample.com for the on-premises domain and LyncSample.ccstp.net for the online domain.</span></span>
  
1. <span data-ttu-id="81e21-109">Создайте почтовый ящик ресурсов в центре администрирования Exchange (LyncSample.ccsctp.net), подключившись к командной консоли Exchange Online, как описано в разделе Подготовка Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="81e21-109">Create a resource mailbox in Exchange admin center (LyncSample.ccsctp.net) by connecting to the Exchange Online Management shell as described in Exchange Online Provisioning.</span></span>
    
   ```powershell
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    <span data-ttu-id="81e21-110">Вы можете проверить подключение к OWA, используя lrstest5@LyncSample.ccsctp.net для входа в систему.</span><span class="sxs-lookup"><span data-stu-id="81e21-110">You can verify OWA connectivity using lrstest5@LyncSample.ccsctp.net to log in.</span></span>
    
2. <span data-ttu-id="81e21-111">В центре администрирования Office 365 добавьте адрес электронной почты lrstest5@LyncSample.com (локальный домен) и укажите адрес ответа.</span><span class="sxs-lookup"><span data-stu-id="81e21-111">In the Office 365 Exchange admin center, add an e-mail address lrstest5@LyncSample.com (on-prem domain) and set it as the reply address.</span></span>
    
3. <span data-ttu-id="81e21-112">Создайте локальную пользовательскую lrstest5@LyncSample.com Active Directory, установите для адреса электронной почты значение lrstest5@LyncSample.com и задайте для целевого адреса значение lrstest5@LyncSample.com.</span><span class="sxs-lookup"><span data-stu-id="81e21-112">Create an on-prem Active Directory user lrstest5@LyncSample.com, set the e-mail address to lrstest5@LyncSample.com, and set the target address to lrstest5@LyncSample.com.</span></span>
    
4. <span data-ttu-id="81e21-113">Активация службы синхронизации каталогов и после завершения синхронизации убедитесь в том, что пользователи объединяются в AAD и что вы не можете изменять свойства в ресурсах получателя в центре администрирования Office365 Exchange.</span><span class="sxs-lookup"><span data-stu-id="81e21-113">Trigger directory synchronization, and, after synchronization is complete, verify that users merge in AAD and that you are not able to change properties in recipient's resources in the Office365 Exchange admin center.</span></span>
    
5. <span data-ttu-id="81e21-114">Проверьте подключение к OWA с помощью lrstest5@LyncSample.com.</span><span class="sxs-lookup"><span data-stu-id="81e21-114">Verify OWA connectivity using lrstest5@LyncSample.com.</span></span> <span data-ttu-id="81e21-115">(Ранее вы проверили возможности подключения к OWA с помощью домена в сети.)</span><span class="sxs-lookup"><span data-stu-id="81e21-115">(Earlier, you verified OWA connectivity using the online domain.)</span></span>
    
    <span data-ttu-id="81e21-p103">После создания почтового ящика для его настройки можно использовать Set-CalendarProcessing в командной консоли Exchange Online. Для получения дополнительных сведений см. шаги 3-6 в разделе "Локальные развертывания с одиночным лесом".</span><span class="sxs-lookup"><span data-stu-id="81e21-p103">After creating the mailbox, you can use Set-CalendarProcessing on the Exchange Online Management Shell to configure the mailbox. Refer to steps 3 through 6 under Single Forest On-prem Deployments for more details.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="81e21-118">Если у вас есть гибридная среда с Exchange Server и Exchange Online, перейдите в командную консоль Exchange и включите-Ремотемаилбокс lrstest5@LyncSample.com-Ремотераутингаддресс lrstest5@LyncSample.mail.ccsctp.net-Room.</span><span class="sxs-lookup"><span data-stu-id="81e21-118">If you have a hybrid environment with Exchange Server and Exchange Online, go to the Exchange Management Shell and Enable-RemoteMailbox lrstest5@LyncSample.com -RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net -Room.</span></span> <span data-ttu-id="81e21-119">Запустите синхронизацию с каталогом.</span><span class="sxs-lookup"><span data-stu-id="81e21-119">Then trigger Directory Synchronization.</span></span> 
  
    <span data-ttu-id="81e21-120">Если вы хотите разместить почтовый ящик системы комнаты Skype в Exchange Online, эти инструкции командной консоли Exchange не требуются, и вы можете перейти к действию 6.</span><span class="sxs-lookup"><span data-stu-id="81e21-120">If you want to host the Skype Room System mailbox in Exchange Online, these Exchange Management Shell steps are not required and you can proceed to step 6.</span></span>
    
6. <span data-ttu-id="81e21-121">Включите учетную запись системы комнаты Skype для Skype для бизнеса, выполнив в командной консоли Skype для бизнеса следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="81e21-121">Enable the Skype Room System account for Skype for Business by running the following cmdlet on Skype for Business Management Shell:</span></span>
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> <span data-ttu-id="81e21-122">Если у вас есть Skype для бизнеса Online вместо Skype для бизнеса Server в описанной выше ситуации, после подготовки почтового ящика Exchange для подготовки к работе необходимо подготовить учетную запись Skype для бизнеса, как описано в разделе Подготовка Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="81e21-122">If you have Skype for Business Online instead of Skype for Business Server in the above scenario, then after provisioning the Exchange resource mailbox, provision a Skype for Business account as described in Skype for Business Online Provisioning.</span></span> 
  

