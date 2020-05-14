---
title: Гибридные развертывания системы комнат Skype
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: В этом разделе рассказывается, как развертывать систему комнат Skype в гибридной среде.
ms.openlocfilehash: 5773fac7aa87a6ee8c7c64c68124e48f4be67b66
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "44219679"
---
# <a name="skype-room-system-hybrid-deployments"></a><span data-ttu-id="e65fa-103">Гибридные развертывания системы комнат Skype</span><span class="sxs-lookup"><span data-stu-id="e65fa-103">Skype Room System hybrid deployments</span></span>

<span data-ttu-id="e65fa-104">В этом разделе рассказывается, как развертывать систему комнат Skype в гибридной среде.</span><span class="sxs-lookup"><span data-stu-id="e65fa-104">Read this topic to learn how to deploy Skype Room System in a hybrid environment.</span></span>
  
## <a name="hybrid-deployments"></a><span data-ttu-id="e65fa-105">Гибридные развертывания</span><span class="sxs-lookup"><span data-stu-id="e65fa-105">Hybrid deployments</span></span>

<span data-ttu-id="e65fa-106">Выполните указанные ниже действия, если ваша топология использует Skype для бизнеса Server и Exchange Online, и вы хотите разместить почтовый ящик ресурса системы комнат Skype в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e65fa-106">Follow these steps if your topology has Skype for Business Server and Exchange Online, and you want to host the Skype Room System resource mailbox on Exchange Online.</span></span> <span data-ttu-id="e65fa-107">В этом разделе также описывается гибридный сценарий, в котором вы развернули как Exchange Online, так и Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="e65fa-107">This section also covers a hybrid scenario where you have both Exchange Online and Exchange Server deployed.</span></span>
  
<span data-ttu-id="e65fa-108">Для иллюстрации целей мы используем LyncSample.com для локального домена и LyncSample.ccstp.net для домена в сети.</span><span class="sxs-lookup"><span data-stu-id="e65fa-108">For illustrative purpose, we use LyncSample.com for the on-premises domain and LyncSample.ccstp.net for the online domain.</span></span>
  
1. <span data-ttu-id="e65fa-109">Создайте почтовый ящик ресурса в центре администрирования Exchange (LyncSample.ccsctp.net), подключившись к командной консоли Exchange Online, как описано в статье Подготовка Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e65fa-109">Create a resource mailbox in Exchange admin center (LyncSample.ccsctp.net) by connecting to the Exchange Online Management shell as described in Exchange Online Provisioning.</span></span>
    
   ```powershell
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    <span data-ttu-id="e65fa-110">Вы можете проверить подключение OWA, используя lrstest5@LyncSample.ccsctp.net для входа в систему.</span><span class="sxs-lookup"><span data-stu-id="e65fa-110">You can verify OWA connectivity using lrstest5@LyncSample.ccsctp.net to log in.</span></span>
    
2. <span data-ttu-id="e65fa-111">В центре администрирования Exchange для Microsoft 365 или Office 365 добавьте адрес электронной почты lrstest5@LyncSample.com (локальный домен) и задайте его в качестве адреса для ответа.</span><span class="sxs-lookup"><span data-stu-id="e65fa-111">In the Microsoft 365 or Office 365 Exchange admin center, add an e-mail address lrstest5@LyncSample.com (on-prem domain) and set it as the reply address.</span></span>
    
3. <span data-ttu-id="e65fa-112">Создайте локальный пользователь lrstest5@LyncSample.com Active Directory, задайте для него адрес электронной почты lrstest5@LyncSample.com и задайте для целевого адреса значение lrstest5@LyncSample.com.</span><span class="sxs-lookup"><span data-stu-id="e65fa-112">Create an on-prem Active Directory user lrstest5@LyncSample.com, set the e-mail address to lrstest5@LyncSample.com, and set the target address to lrstest5@LyncSample.com.</span></span>
    
4. <span data-ttu-id="e65fa-113">Активируйте синхронизацию службы каталогов и после завершения синхронизации убедитесь, что пользователи объединяются в AAD и что не удается изменить свойства в ресурсах получателей в центре администрирования Microsoft 365 или Office 365 Exchange.</span><span class="sxs-lookup"><span data-stu-id="e65fa-113">Trigger directory synchronization, and, after synchronization is complete, verify that users merge in AAD and that you are not able to change properties in recipient's resources in the Microsoft 365 or Office 365 Exchange admin center.</span></span>
    
5. <span data-ttu-id="e65fa-114">Проверьте возможность подключения OWA с помощью lrstest5@LyncSample.com.</span><span class="sxs-lookup"><span data-stu-id="e65fa-114">Verify OWA connectivity using lrstest5@LyncSample.com.</span></span> <span data-ttu-id="e65fa-115">(Ранее вы проверили возможности подключения к OWA с помощью домена Online.)</span><span class="sxs-lookup"><span data-stu-id="e65fa-115">(Earlier, you verified OWA connectivity using the online domain.)</span></span>
    
    <span data-ttu-id="e65fa-116">После создания почтового ящика можно использовать командлет Set-CalendarProcessing в командной консоли Exchange Online для настройки почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="e65fa-116">After creating the mailbox, you can use Set-CalendarProcessing on the Exchange Online Management Shell to configure the mailbox.</span></span> <span data-ttu-id="e65fa-117">Для получения дополнительных сведений обратитесь к разделу 3 – 6 в разделе локальное развертывание в пределах одного леса.</span><span class="sxs-lookup"><span data-stu-id="e65fa-117">Refer to steps 3 through 6 under Single Forest On-prem Deployments for more details.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="e65fa-118">Если вы используете гибридную среду с Exchange Server и Exchange Online, перейдите в командную консоль Exchange и включите параметр-RemoteMailbox lrstest5@LyncSample.com-RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net-Room.</span><span class="sxs-lookup"><span data-stu-id="e65fa-118">If you have a hybrid environment with Exchange Server and Exchange Online, go to the Exchange Management Shell and Enable-RemoteMailbox lrstest5@LyncSample.com -RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net -Room.</span></span> <span data-ttu-id="e65fa-119">Затем активируйте синхронизацию службы каталогов.</span><span class="sxs-lookup"><span data-stu-id="e65fa-119">Then trigger Directory Synchronization.</span></span> 
  
    <span data-ttu-id="e65fa-120">Если вы хотите разместить почтовый ящик системы комнат Skype в Exchange Online, эти действия для командной консоли Exchange не требуются, и вы можете перейти к шагу 6.</span><span class="sxs-lookup"><span data-stu-id="e65fa-120">If you want to host the Skype Room System mailbox in Exchange Online, these Exchange Management Shell steps are not required and you can proceed to step 6.</span></span>
    
6. <span data-ttu-id="e65fa-121">Включите учетную запись системы комнат Skype для Skype для бизнеса, выполнив следующий командлет в командной консоли Skype для бизнеса:</span><span class="sxs-lookup"><span data-stu-id="e65fa-121">Enable the Skype Room System account for Skype for Business by running the following cmdlet on Skype for Business Management Shell:</span></span>
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> <span data-ttu-id="e65fa-122">Если вы используете Skype для бизнеса Online вместо Skype для бизнеса Server в указанном выше сценарии, то после подготовки почтового ящика ресурсов Exchange предоставьте учетную запись Skype для бизнеса, как описано в статье Подготовка Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="e65fa-122">If you have Skype for Business Online instead of Skype for Business Server in the above scenario, then after provisioning the Exchange resource mailbox, provision a Skype for Business account as described in Skype for Business Online Provisioning.</span></span> 
  

