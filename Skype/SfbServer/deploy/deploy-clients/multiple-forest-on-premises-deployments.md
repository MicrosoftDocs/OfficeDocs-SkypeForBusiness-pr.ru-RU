---
title: Развертывание нескольких локальных лесов для системы комнат Skype
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6793fca0-3970-44e4-8703-1925428c1967
description: В этом разделе описывается развертывание системы комнат Skype в локальной среде с несколькими лесами.
ms.openlocfilehash: eb5aa2cbe3bef26602279ffa9d4a5dc38a7e7bc2
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "36775044"
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a><span data-ttu-id="624fd-103">Развертывание нескольких локальных лесов для системы комнат Skype</span><span class="sxs-lookup"><span data-stu-id="624fd-103">Skype Room System multiple forest on-premises deployments</span></span>
 
<span data-ttu-id="624fd-104">В этом разделе описывается развертывание системы комнат Skype в локальной среде с несколькими лесами.</span><span class="sxs-lookup"><span data-stu-id="624fd-104">Read this topic to learn how to deploy Skype Room System in a multiple forest on-premises environment.</span></span>
  
> [!NOTE]
> <span data-ttu-id="624fd-105">Для развертывания в нескольких лесах для системы комнат Skype требуется Exchange Server 2013 CU6 выпущены 26 августа 2014 г.</span><span class="sxs-lookup"><span data-stu-id="624fd-105">In order to deploy in multiple forests, Skype Room System requires Exchange Server 2013 CU6 released on August 26, 2014.</span></span> <span data-ttu-id="624fd-106">Старайтесь не использовать существующий почтовый ящик для системы комнат Skype.</span><span class="sxs-lookup"><span data-stu-id="624fd-106">Avoid re-using an existing mailbox for Skype Room System.</span></span> <span data-ttu-id="624fd-107">Использование нового почтового ящика ресурсов (удаление старого почтового ящика и повторного создания) для системы комнат Skype.</span><span class="sxs-lookup"><span data-stu-id="624fd-107">Use a new (delete old mailbox and re-create) resource mailbox for Skype Room System.</span></span> <span data-ttu-id="624fd-108">Чтобы восстановить собрания из-за удаления почтового ящика, обратитесь к разделу [подключение или восстановление удаленного почтового ящика](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="624fd-108">To restore the meetings lost by deleting the mailbox, see [Connect or restore a deleted mailbox](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx).</span></span> 
  
<span data-ttu-id="624fd-109">After creating the mailbox, you can use Set-CalendarProcessing to configure the mailbox.</span><span class="sxs-lookup"><span data-stu-id="624fd-109">After creating the mailbox, you can use Set-CalendarProcessing to configure the mailbox.</span></span> <span data-ttu-id="624fd-110">Refer to steps 3 through 6 under Single forest on-premises deployments for more details.</span><span class="sxs-lookup"><span data-stu-id="624fd-110">Refer to steps 3 through 6 under Single forest on-premises deployments for more details.</span></span> <span data-ttu-id="624fd-111">После создания почтового ящика ресурсов Exchange для системы комнат Skype включите учетную запись Skype для бизнеса, выполнив действия, описанные в статье Включение системных учетных записей Skype для бизнеса в рамках локальных развертываний с одним лесом.</span><span class="sxs-lookup"><span data-stu-id="624fd-111">After creating an Exchange Resource mailbox for Skype Room System, enable the account for Skype for Business by following the steps in Enabling Skype Room System Accounts for Skype for Business under Single forest on-premises deployments.</span></span>
  
## <a name="option-1-create-a-new-resource-mailbox"></a><span data-ttu-id="624fd-112">Вариант 1. Создание нового почтового ящика ресурсов</span><span class="sxs-lookup"><span data-stu-id="624fd-112">Option 1: Create a new resource mailbox</span></span>

<span data-ttu-id="624fd-113">Чтобы развернуть систему комнат Skype в среде с несколькими лесами:</span><span class="sxs-lookup"><span data-stu-id="624fd-113">To deploy Skype Room System in a multi-forest environment:</span></span>
  
1. <span data-ttu-id="624fd-114">Создайте связанного пользователя (LinkedRoomTest) в Active Directory (Authentication Forest).</span><span class="sxs-lookup"><span data-stu-id="624fd-114">Create a Linked User (LinkedRoomTest) in Active Directory (Authentication Forest).</span></span>
    
2. <span data-ttu-id="624fd-115">Выполните следующие команды в командной консоли Exchange Server:</span><span class="sxs-lookup"><span data-stu-id="624fd-115">Run the following commands in the Exchange Server Management Shell:</span></span>
    
   ```
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a><span data-ttu-id="624fd-116">Вариант 2: изменение почтового ящика помещения на почтовый ящик системы комнаты Skype (связанный)</span><span class="sxs-lookup"><span data-stu-id="624fd-116">Option 2: Change an existing room mailbox to Skype Room System (linked) resource mailbox</span></span>

```
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```


