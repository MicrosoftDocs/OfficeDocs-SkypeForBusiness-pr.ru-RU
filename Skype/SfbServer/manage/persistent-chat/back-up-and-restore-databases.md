---
title: Back up and restore Persistent Chat databases in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4f2b689b-7f15-48dc-a069-da7bc8527def
description: Сводка. Узнайте, как с помощью Skype для бизнеса Server 2015 восстанавливать базы данных сервера сохраняемой беседы.
ms.openlocfilehash: 2c99f5e955756020f68b51ea214858c23fee0a48
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826379"
---
# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a><span data-ttu-id="95e62-103">Back up and restore Persistent Chat databases in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="95e62-103">Back up and restore Persistent Chat databases in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="95e62-104">**Сводка:** Learn how to back up and restore Persistent Chat Server databases in Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="95e62-104">**Summary:** Learn how to back up and restore Persistent Chat Server databases in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="95e62-105">Серверу сохраняемого чата требуется SQL Server базы данных для хранения данных комнат чата, таких как история и содержимое, конфигурация, подготовка пользователей и другие соответствующие метаданные.</span><span class="sxs-lookup"><span data-stu-id="95e62-105">Persistent Chat Server requires SQL Server database software to store chat room data, such as history and content, configuration, user provisioning, and other relevant metadata.</span></span> <span data-ttu-id="95e62-106">Кроме того, если в организации имеются нормативы, которые требуют архивировать действия сохраняемой беседы и включена необязательная служба соответствия, программное обеспечение базы данных SQL Server используется для хранения данных соответствия требованиям, включая содержимое чата и события, такие как присоединение и выход из комнат.</span><span class="sxs-lookup"><span data-stu-id="95e62-106">In addition, if your organization has regulations that require Persistent Chat activity to be archived, and the optional Compliance service is enabled, SQL Server database software is used to store compliance data, including chat content and events, such as joining and leaving rooms.</span></span> <span data-ttu-id="95e62-107">Содержимое комнаты чата хранится в базе данных сохраняемой беседы (mgc).</span><span class="sxs-lookup"><span data-stu-id="95e62-107">Chat room content is stored in the Persistent Chat database (mgc).</span></span> <span data-ttu-id="95e62-108">Данные соответствия требованиям хранятся в базе данных соответствия (mgccomp).</span><span class="sxs-lookup"><span data-stu-id="95e62-108">Compliance data is stored in the Compliance database (mgccomp).</span></span> <span data-ttu-id="95e62-109">Это критически важные для бизнеса данные, которые следует регулярно обновлять.</span><span class="sxs-lookup"><span data-stu-id="95e62-109">This is business-critical data that should be backed up regularly.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="95e62-110">Сохраняемая беседа доступна в Skype для бизнеса Server 2015, но больше не поддерживается в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="95e62-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="95e62-111">Такие же функции доступны в Teams.</span><span class="sxs-lookup"><span data-stu-id="95e62-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="95e62-112">Дополнительные сведения [см. в сведениях о том,](/microsoftteams/upgrade-start-here)как начать обновление Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="95e62-112">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="95e62-113">Если необходимо использовать сохраняемого чата, вы можете либо перенести пользователей, которым требуются эти функции, в Teams, либо продолжить использование Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="95e62-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="back-up-the-databases"></a><span data-ttu-id="95e62-114">Back up the databases</span><span class="sxs-lookup"><span data-stu-id="95e62-114">Back up the databases</span></span>

<span data-ttu-id="95e62-115">Существует два способа сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="95e62-115">There are two ways of backing up Persistent Chat data.</span></span> 
  
- <span data-ttu-id="95e62-116">SQL Server резервного копирования</span><span class="sxs-lookup"><span data-stu-id="95e62-116">SQL Server Backup</span></span>
    
- <span data-ttu-id="95e62-117">The **Export-CsPersistentChatData cmdlet,** which exports Persistent Chat data as a file</span><span class="sxs-lookup"><span data-stu-id="95e62-117">The **Export-CsPersistentChatData** cmdlet, which exports Persistent Chat data as a file</span></span>
    
<span data-ttu-id="95e62-118">Для данных, созданных с помощью резервного копирования SQL Server, требуется значительно больше места на диске (возможно, в 20 раз больше), чем для создания с помощью cmdlet **Export-CsPersistentChatData,** но резервное копирование SQL Server, скорее всего, является процедурой, с которой вы знакомы.</span><span class="sxs-lookup"><span data-stu-id="95e62-118">Data that is created by using SQL Server backup requires significantly more disk space—possibly 20 times more—than that created by the **Export-CsPersistentChatData** cmdlet, but SQL Server backup is likely to be a procedure with which you are familiar.</span></span>
  
<span data-ttu-id="95e62-119">Если вы хотите использовать SQL Server резервного копирования, см. SQL документации по резервному копированию.</span><span class="sxs-lookup"><span data-stu-id="95e62-119">If you want to use SQL Server backup procedures, see your SQL documentation for more information.</span></span> 
  
<span data-ttu-id="95e62-120">Чтобы использовать командлет **Export-CsPersistentChatData,** можно указать команду следующим образом:</span><span class="sxs-lookup"><span data-stu-id="95e62-120">If you want to use the **Export-CsPersistentChatData** cmdlet, you can specify the command as follows:</span></span>
  
```PowerShell
Export-CsPersistentChatData [-FileName <String>] <COMMON PARAMETERS>
```

<span data-ttu-id="95e62-121">или</span><span class="sxs-lookup"><span data-stu-id="95e62-121">or</span></span>
  
```PowerShell
Export-CsPersistentChatData [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>
```

<span data-ttu-id="95e62-122">Например, следующая команда экспортирует данные сохраняемой беседы из базы данных сохраняемой беседы, расположенной на сервере atl-sql-001.contoso.com; экспортные данные будут сохранены в файле C:\Logs\PersistentChatData.zip.</span><span class="sxs-lookup"><span data-stu-id="95e62-122">For example, the following command exports Persistent Chat data from the Persistent Chat database located on the server atl-sql-001.contoso.com; the exported data will be stored in the file C:\Logs\PersistentChatData.zip.</span></span> <span data-ttu-id="95e62-123">Так как параметр Level не указан, команда будет полностью экспортировать сведения о сохраняемом чате:</span><span class="sxs-lookup"><span data-stu-id="95e62-123">Because the Level parameter was not specified, the command will do a full export of the Persistent Chat information:</span></span>
  
```PowerShell
Export-CsPersistentChatData -DBInstance "atl-sql-001.contoso.com\rtc" -FileName "C:\Logs\PersistentChatData.zip"
```

## <a name="restore-the-databases"></a><span data-ttu-id="95e62-124">Восстановление баз данных</span><span class="sxs-lookup"><span data-stu-id="95e62-124">Restore the databases</span></span>

<span data-ttu-id="95e62-125">Способ восстановления данных сохраняемого чата зависит от метода, который использовался для их восстановления.</span><span class="sxs-lookup"><span data-stu-id="95e62-125">How you restore your Persistent Chat data depends on the method that you used to back it up.</span></span> <span data-ttu-id="95e62-126">Если вы использовали SQL Server резервного копирования, необходимо использовать SQL Server восстановления.</span><span class="sxs-lookup"><span data-stu-id="95e62-126">If you used SQL Server backup procedures, you must use SQL Server restore procedures.</span></span> <span data-ttu-id="95e62-127">Если для восстановления данных сохраняемого чата использовался cmdlet **Export-CsPersistentChatData,** то для восстановления данных необходимо использовать его с помощью **import-CsPersistentChatData:**</span><span class="sxs-lookup"><span data-stu-id="95e62-127">If you used the **Export-CsPersistentChatData** cmdlet to back up Persistent Chat data, then you must use the **Import-CsPersistentChatData** cmdlet to restore the data:</span></span>
  
```PowerShell
Import-CsPersistentChatData -FileName <String> <COMMON PARAMETERS>
```

<span data-ttu-id="95e62-128">или</span><span class="sxs-lookup"><span data-stu-id="95e62-128">or</span></span>
  
```PowerShell
Import-CsPersistentChatData -ByteInput <Byte > <COMMON PARAMETERS>
```
