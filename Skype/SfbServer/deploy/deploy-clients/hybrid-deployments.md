---
title: Гибридные развертывания системы комнат Skype
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: В этом разделе вы узнаете, как развернуть систему комнат Skype в гибридной среде.
ms.openlocfilehash: 47be9204155a1ff6cf6e8d9dfa67723a370fec26
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805899"
---
# <a name="skype-room-system-hybrid-deployments"></a><span data-ttu-id="81c71-103">Гибридные развертывания системы комнат Skype</span><span class="sxs-lookup"><span data-stu-id="81c71-103">Skype Room System hybrid deployments</span></span>

<span data-ttu-id="81c71-104">В этом разделе вы узнаете, как развернуть систему комнат Skype в гибридной среде.</span><span class="sxs-lookup"><span data-stu-id="81c71-104">Read this topic to learn how to deploy Skype Room System in a hybrid environment.</span></span>
  
## <a name="hybrid-deployments"></a><span data-ttu-id="81c71-105">Гибридные развертывания</span><span class="sxs-lookup"><span data-stu-id="81c71-105">Hybrid deployments</span></span>

<span data-ttu-id="81c71-106">Выполните следующие действия, если в вашей топологии есть Skype для бизнеса Server и Exchange Online, и вы хотите, чтобы почтовый ящик ресурса системы комнат Skype был в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="81c71-106">Follow these steps if your topology has Skype for Business Server and Exchange Online, and you want to host the Skype Room System resource mailbox on Exchange Online.</span></span> <span data-ttu-id="81c71-107">В этом разделе также описывается гибридный сценарий, в котором развернуты exchange Online Exchange Server exchange Online.</span><span class="sxs-lookup"><span data-stu-id="81c71-107">This section also covers a hybrid scenario where you have both Exchange Online and Exchange Server deployed.</span></span>
  
<span data-ttu-id="81c71-108">Для наглядности мы используем LyncSample.com для локального домена и LyncSample.ccstp.net для интернет-домена.</span><span class="sxs-lookup"><span data-stu-id="81c71-108">For illustrative purpose, we use LyncSample.com for the on-premises domain and LyncSample.ccstp.net for the online domain.</span></span>
  
1. <span data-ttu-id="81c71-109">Создайте почтовый ящик ресурса в Центре администрирования Exchange (LyncSample.ccsctp.net), подключившись к оболочке управления Exchange Online, как описано в exchange Online Provisioning.</span><span class="sxs-lookup"><span data-stu-id="81c71-109">Create a resource mailbox in Exchange admin center (LyncSample.ccsctp.net) by connecting to the Exchange Online Management shell as described in Exchange Online Provisioning.</span></span>
    
   ```powershell
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    <span data-ttu-id="81c71-110">Проверить подключение OWA можно с помощью lrstest5@LyncSample.ccsctp.net входа.</span><span class="sxs-lookup"><span data-stu-id="81c71-110">You can verify OWA connectivity using lrstest5@LyncSample.ccsctp.net to log in.</span></span>
    
2. <span data-ttu-id="81c71-111">В Центре администрирования Microsoft 365 или Office 365 Exchange добавьте адрес электронной почты lrstest5@LyncSample.com (наемный домен) и установите его в качестве адреса ответа.</span><span class="sxs-lookup"><span data-stu-id="81c71-111">In the Microsoft 365 or Office 365 Exchange admin center, add an e-mail address lrstest5@LyncSample.com (on-prem domain) and set it as the reply address.</span></span>
    
3. <span data-ttu-id="81c71-112">Создайте учетную lrstest5@LyncSample.com Active Directory, установите для адреса электронной почты lrstest5@LyncSample.com и за установите для целевого адреса lrstest5@LyncSample.com.</span><span class="sxs-lookup"><span data-stu-id="81c71-112">Create an on-prem Active Directory user lrstest5@LyncSample.com, set the e-mail address to lrstest5@LyncSample.com, and set the target address to lrstest5@LyncSample.com.</span></span>
    
4. <span data-ttu-id="81c71-113">Запуск синхронизации службы каталогов и проверка объединения пользователей в AAD и невозможности изменения свойств в ресурсах получателей в Центре администрирования Microsoft 365 или Office 365 Exchange.</span><span class="sxs-lookup"><span data-stu-id="81c71-113">Trigger directory synchronization, and, after synchronization is complete, verify that users merge in AAD and that you are not able to change properties in recipient's resources in the Microsoft 365 or Office 365 Exchange admin center.</span></span>
    
5. <span data-ttu-id="81c71-114">Проверьте подключение OWA с помощью lrstest5@LyncSample.com.</span><span class="sxs-lookup"><span data-stu-id="81c71-114">Verify OWA connectivity using lrstest5@LyncSample.com.</span></span> <span data-ttu-id="81c71-115">(Ранее вы проверили подключение OWA с помощью интернет-домена.)</span><span class="sxs-lookup"><span data-stu-id="81c71-115">(Earlier, you verified OWA connectivity using the online domain.)</span></span>
    
    <span data-ttu-id="81c71-116">После создания почтового ящика можно использовать Set-CalendarProcessing в exchange Online Management Shell для настройки почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="81c71-116">After creating the mailbox, you can use Set-CalendarProcessing on the Exchange Online Management Shell to configure the mailbox.</span></span> <span data-ttu-id="81c71-117">Дополнительные сведения можно найти в действиях с 3 по 6 в статье "Развертывание с одним лесом на предварительном этапе".</span><span class="sxs-lookup"><span data-stu-id="81c71-117">Refer to steps 3 through 6 under Single Forest On-prem Deployments for more details.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="81c71-118">Если у вас гибридная среда с Exchange Server и Exchange Online, перейдите в exchange Management Shell и Enable-RemoteMailbox lrstest5@LyncSample.com -RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net -Room.</span><span class="sxs-lookup"><span data-stu-id="81c71-118">If you have a hybrid environment with Exchange Server and Exchange Online, go to the Exchange Management Shell and Enable-RemoteMailbox lrstest5@LyncSample.com -RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net -Room.</span></span> <span data-ttu-id="81c71-119">Затем активирует синхронизацию каталогов.</span><span class="sxs-lookup"><span data-stu-id="81c71-119">Then trigger Directory Synchronization.</span></span> 
  
    <span data-ttu-id="81c71-120">Если вы хотите, чтобы почтовый ящик системы комнат Skype был в Exchange Online, эти действия в exchange Management Shell не требуются, и вы можете перейти к шагу 6.</span><span class="sxs-lookup"><span data-stu-id="81c71-120">If you want to host the Skype Room System mailbox in Exchange Online, these Exchange Management Shell steps are not required and you can proceed to step 6.</span></span>
    
6. <span data-ttu-id="81c71-121">Чтобы включить учетную запись системы комнат Skype для бизнеса, в оболочке управления Skype для бизнеса с помощью следующего:</span><span class="sxs-lookup"><span data-stu-id="81c71-121">Enable the Skype Room System account for Skype for Business by running the following cmdlet on Skype for Business Management Shell:</span></span>
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> <span data-ttu-id="81c71-122">Если в вышеуказанном сценарии вместо Skype для бизнеса Server имеется Skype для бизнеса Online, то после предоставления почтового ящика ресурса Exchange подучет учетной записи Skype для бизнеса, как описано в подучете Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="81c71-122">If you have Skype for Business Online instead of Skype for Business Server in the above scenario, then after provisioning the Exchange resource mailbox, provision a Skype for Business account as described in Skype for Business Online Provisioning.</span></span> 
  

