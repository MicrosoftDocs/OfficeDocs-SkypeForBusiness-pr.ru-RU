---
title: Развертывание нескольких локальных лесов для системы комнат Skype
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6793fca0-3970-44e4-8703-1925428c1967
description: В этом разделе описывается развертывание системы комнат Skype в локальной среде с несколькими лесами.
ms.openlocfilehash: 607177a1b091fb4d7872b726fa31cd0329b3b975
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33895042"
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a><span data-ttu-id="48e2a-103">Развертывание нескольких локальных лесов для системы комнат Skype</span><span class="sxs-lookup"><span data-stu-id="48e2a-103">Skype Room System multiple forest on-premises deployments</span></span>
 
<span data-ttu-id="48e2a-104">В этом разделе описывается развертывание системы комнат Skype в локальной среде с несколькими лесами.</span><span class="sxs-lookup"><span data-stu-id="48e2a-104">Read this topic to learn how to deploy Skype Room System in a multiple forest on-premises environment.</span></span>
  
> [!NOTE]
> <span data-ttu-id="48e2a-105">Для развертывания в нескольких лесах, система комнаты Скайп требуется Exchange Server 2013 CU6 выпущен 26 августа 2014 г.</span><span class="sxs-lookup"><span data-stu-id="48e2a-105">In order to deploy in multiple forests, Skype Room System requires Exchange Server 2013 CU6 released on August 26, 2014.</span></span> <span data-ttu-id="48e2a-106">Избегайте повторное использование существующего почтового ящика для помещения Скайп системы.</span><span class="sxs-lookup"><span data-stu-id="48e2a-106">Avoid re-using an existing mailbox for Skype Room System.</span></span> <span data-ttu-id="48e2a-107">Использовать новый (удаление старых почтовых ящиков и повторное создание) почтового ящика ресурса для помещения Скайп системы.</span><span class="sxs-lookup"><span data-stu-id="48e2a-107">Use a new (delete old mailbox and re-create) resource mailbox for Skype Room System.</span></span> <span data-ttu-id="48e2a-108">Чтобы восстановить собраний, потеряны при удалении почтового ящика, видеть [подключение или восстановление удаленного почтового ящика](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="48e2a-108">To restore the meetings lost by deleting the mailbox, see [Connect or restore a deleted mailbox](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx).</span></span> 
  
<span data-ttu-id="48e2a-109">After creating the mailbox, you can use Set-CalendarProcessing to configure the mailbox.</span><span class="sxs-lookup"><span data-stu-id="48e2a-109">After creating the mailbox, you can use Set-CalendarProcessing to configure the mailbox.</span></span> <span data-ttu-id="48e2a-110">Refer to steps 3 through 6 under Single forest on-premises deployments for more details.</span><span class="sxs-lookup"><span data-stu-id="48e2a-110">Refer to steps 3 through 6 under Single forest on-premises deployments for more details.</span></span> <span data-ttu-id="48e2a-111">После создания почтового ящика Exchange ресурсов для системы Скайп помещения, включить учетную запись для Скайп для бизнеса, выполнив действия в Включение Скайп комнаты системных учетных записей для Скайп для бизнеса в разделе локальные развертывания одного леса.</span><span class="sxs-lookup"><span data-stu-id="48e2a-111">After creating an Exchange Resource mailbox for Skype Room System, enable the account for Skype for Business by following the steps in Enabling Skype Room System Accounts for Skype for Business under Single forest on-premises deployments.</span></span>
  
## <a name="option-1-create-a-new-resource-mailbox"></a><span data-ttu-id="48e2a-112">Вариант 1. Создание нового почтового ящика ресурсов</span><span class="sxs-lookup"><span data-stu-id="48e2a-112">Option 1: Create a new resource mailbox</span></span>

<span data-ttu-id="48e2a-113">Для развертывания в среде с несколькими лесами Скайп комнаты системы:</span><span class="sxs-lookup"><span data-stu-id="48e2a-113">To deploy Skype Room System in a multi-forest environment:</span></span>
  
1. <span data-ttu-id="48e2a-114">Создайте связанного пользователя (LinkedRoomTest) в Active Directory (Authentication Forest).</span><span class="sxs-lookup"><span data-stu-id="48e2a-114">Create a Linked User (LinkedRoomTest) in Active Directory (Authentication Forest).</span></span>
    
2. <span data-ttu-id="48e2a-115">Выполните следующие команды в командной консоли Exchange Server:</span><span class="sxs-lookup"><span data-stu-id="48e2a-115">Run the following commands in the Exchange Server Management Shell:</span></span>
    
   ```
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a><span data-ttu-id="48e2a-116">Вариант 2: Изменение существующего почтового ящика помещения к почтовому ящику (связанные) ресурсов системы Скайп комнаты</span><span class="sxs-lookup"><span data-stu-id="48e2a-116">Option 2: Change an existing room mailbox to Skype Room System (linked) resource mailbox</span></span>

```
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```


