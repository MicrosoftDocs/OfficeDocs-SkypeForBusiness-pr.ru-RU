---
title: Локальное развертывание системы комнат Skype с несколькими лесами
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
ms.assetid: 6793fca0-3970-44e4-8703-1925428c1967
description: В этом разделе вы узнаете, как развернуть систему комнат Skype в локальной среде с несколькими лесами.
ms.openlocfilehash: 168244033a681b9aa9dc6e4c9697b7e3c7e89127
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805749"
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a><span data-ttu-id="e359c-103">Локальное развертывание системы комнат Skype с несколькими лесами</span><span class="sxs-lookup"><span data-stu-id="e359c-103">Skype Room System multiple forest on-premises deployments</span></span>
 
<span data-ttu-id="e359c-104">В этом разделе вы узнаете, как развернуть систему комнат Skype в локальной среде с несколькими лесами.</span><span class="sxs-lookup"><span data-stu-id="e359c-104">Read this topic to learn how to deploy Skype Room System in a multiple forest on-premises environment.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e359c-105">Для развертывания в нескольких лесах системе комнат Skype требуется Exchange Server 2013 CU6, выпущенный 26 августа 2014 г.</span><span class="sxs-lookup"><span data-stu-id="e359c-105">In order to deploy in multiple forests, Skype Room System requires Exchange Server 2013 CU6 released on August 26, 2014.</span></span> <span data-ttu-id="e359c-106">Избегайте повторного использования существующего почтового ящика для системы комнат Skype.</span><span class="sxs-lookup"><span data-stu-id="e359c-106">Avoid re-using an existing mailbox for Skype Room System.</span></span> <span data-ttu-id="e359c-107">Используйте новый (удалить старый почтовый ящик и повторно создать) почтовый ящик ресурса для системы комнат Skype.</span><span class="sxs-lookup"><span data-stu-id="e359c-107">Use a new (delete old mailbox and re-create) resource mailbox for Skype Room System.</span></span> <span data-ttu-id="e359c-108">Чтобы восстановить собрания, потерянные при удалении почтового ящика, см. в подключении или [восстановлении удаленного почтового ящика.](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e359c-108">To restore the meetings lost by deleting the mailbox, see [Connect or restore a deleted mailbox](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx).</span></span> 
  
<span data-ttu-id="e359c-109">После создания почтового ящика можно использовать Set-CalendarProcessing для настройки почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="e359c-109">After creating the mailbox, you can use Set-CalendarProcessing to configure the mailbox.</span></span> <span data-ttu-id="e359c-110">Дополнительные сведения можно найти в шагах с 3 по 6 в рамках локального развертывания с одним лесом.</span><span class="sxs-lookup"><span data-stu-id="e359c-110">Refer to steps 3 through 6 under Single forest on-premises deployments for more details.</span></span> <span data-ttu-id="e359c-111">After creating an Exchange Resource mailbox for Skype Room System, enable the account for Skype for Business by following the steps in Enabling Skype Room System Accounts for Skype for Business under Single forest on-premises deployments.</span><span class="sxs-lookup"><span data-stu-id="e359c-111">After creating an Exchange Resource mailbox for Skype Room System, enable the account for Skype for Business by following the steps in Enabling Skype Room System Accounts for Skype for Business under Single forest on-premises deployments.</span></span>
  
## <a name="option-1-create-a-new-resource-mailbox"></a><span data-ttu-id="e359c-112">Вариант 1. Создание нового почтового ящика ресурса</span><span class="sxs-lookup"><span data-stu-id="e359c-112">Option 1: Create a new resource mailbox</span></span>

<span data-ttu-id="e359c-113">Развертывание системы комнат Skype в среде с несколькими лесами</span><span class="sxs-lookup"><span data-stu-id="e359c-113">To deploy Skype Room System in a multi-forest environment:</span></span>
  
1. <span data-ttu-id="e359c-114">Создание связанного пользователя (LinkedRoomTest) в Active Directory (лес проверки подлинности).</span><span class="sxs-lookup"><span data-stu-id="e359c-114">Create a Linked User (LinkedRoomTest) in Active Directory (Authentication Forest).</span></span>
    
2. <span data-ttu-id="e359c-115">В командной Exchange Server командной Exchange Server следующие команды:</span><span class="sxs-lookup"><span data-stu-id="e359c-115">Run the following commands in the Exchange Server Management Shell:</span></span>
    
   ```powershell
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a><span data-ttu-id="e359c-116">Вариант 2. Изменение существующего почтового ящика помещения на почтовый ящик системы комнат Skype (связанный)</span><span class="sxs-lookup"><span data-stu-id="e359c-116">Option 2: Change an existing room mailbox to Skype Room System (linked) resource mailbox</span></span>

```powershell
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```


