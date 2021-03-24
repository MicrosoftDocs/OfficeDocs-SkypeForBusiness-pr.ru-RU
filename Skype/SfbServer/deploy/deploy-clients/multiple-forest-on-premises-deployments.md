---
title: Несколько локального развертывания системы номеров Skype
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
description: Ознакомьтесь с этой темой, чтобы узнать, как развернуть систему skype Room System в нескольких лесных локальной среде.
ms.openlocfilehash: d215ce13059c414d6c6142d7cd1e93ea9011c97b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093533"
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a><span data-ttu-id="4e1a8-103">Несколько локального развертывания системы номеров Skype</span><span class="sxs-lookup"><span data-stu-id="4e1a8-103">Skype Room System multiple forest on-premises deployments</span></span>
 
<span data-ttu-id="4e1a8-104">Ознакомьтесь с этой темой, чтобы узнать, как развернуть систему skype Room System в нескольких лесных локальной среде.</span><span class="sxs-lookup"><span data-stu-id="4e1a8-104">Read this topic to learn how to deploy Skype Room System in a multiple forest on-premises environment.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4e1a8-105">Чтобы развернуться в нескольких лесах, skype Room System требует Exchange Server 2013 cu6, выпущенный 26 августа 2014 г.</span><span class="sxs-lookup"><span data-stu-id="4e1a8-105">In order to deploy in multiple forests, Skype Room System requires Exchange Server 2013 CU6 released on August 26, 2014.</span></span> <span data-ttu-id="4e1a8-106">Избегайте повторного использования существующего почтового ящика для системы номеров Skype.</span><span class="sxs-lookup"><span data-stu-id="4e1a8-106">Avoid re-using an existing mailbox for Skype Room System.</span></span> <span data-ttu-id="4e1a8-107">Используйте новый (удаление старого почтового ящика и повторное создание) почтовый ящик ресурса для системы номеров Skype.</span><span class="sxs-lookup"><span data-stu-id="4e1a8-107">Use a new (delete old mailbox and re-create) resource mailbox for Skype Room System.</span></span> <span data-ttu-id="4e1a8-108">Чтобы восстановить собрания, потерянные путем удаления почтового ящика, см. в руб. Подключение или восстановление [удаленного почтового ящика.](/exchange/connect-or-restore-a-deleted-mailbox-exchange-2013-help)</span><span class="sxs-lookup"><span data-stu-id="4e1a8-108">To restore the meetings lost by deleting the mailbox, see [Connect or restore a deleted mailbox](/exchange/connect-or-restore-a-deleted-mailbox-exchange-2013-help).</span></span> 
  
<span data-ttu-id="4e1a8-109">После создания почтового ящика можно использовать Set-CalendarProcessing для настройки почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="4e1a8-109">After creating the mailbox, you can use Set-CalendarProcessing to configure the mailbox.</span></span> <span data-ttu-id="4e1a8-110">Дополнительные сведения можно найти в статье шаги 3-6 в рамках локального развертывания "Единый лес".</span><span class="sxs-lookup"><span data-stu-id="4e1a8-110">Refer to steps 3 through 6 under Single forest on-premises deployments for more details.</span></span> <span data-ttu-id="4e1a8-111">Создав почтовый ящик Exchange Resource для системы номеров Skype, включим учетную запись Skype для бизнеса, следуя шагам в статье Включение учетных записей skype Room System для Skype для бизнеса в рамках локального развертывания Единого леса.</span><span class="sxs-lookup"><span data-stu-id="4e1a8-111">After creating an Exchange Resource mailbox for Skype Room System, enable the account for Skype for Business by following the steps in Enabling Skype Room System Accounts for Skype for Business under Single forest on-premises deployments.</span></span>
  
## <a name="option-1-create-a-new-resource-mailbox"></a><span data-ttu-id="4e1a8-112">Вариант 1. Создание нового почтового ящика ресурса</span><span class="sxs-lookup"><span data-stu-id="4e1a8-112">Option 1: Create a new resource mailbox</span></span>

<span data-ttu-id="4e1a8-113">Развертывание системы skype Room System в среде с несколькими лесами:</span><span class="sxs-lookup"><span data-stu-id="4e1a8-113">To deploy Skype Room System in a multi-forest environment:</span></span>
  
1. <span data-ttu-id="4e1a8-114">Создание связанного пользователя (LinkedRoomTest) в Active Directory (Лес проверки подлинности).</span><span class="sxs-lookup"><span data-stu-id="4e1a8-114">Create a Linked User (LinkedRoomTest) in Active Directory (Authentication Forest).</span></span>
    
2. <span data-ttu-id="4e1a8-115">Запустите следующие команды в командной Exchange Server:</span><span class="sxs-lookup"><span data-stu-id="4e1a8-115">Run the following commands in the Exchange Server Management Shell:</span></span>
    
   ```powershell
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a><span data-ttu-id="4e1a8-116">Вариант 2. Изменение существующего почтового ящика комнаты на почтовый ящик ресурса Skype Room System (связанный)</span><span class="sxs-lookup"><span data-stu-id="4e1a8-116">Option 2: Change an existing room mailbox to Skype Room System (linked) resource mailbox</span></span>

```powershell
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```