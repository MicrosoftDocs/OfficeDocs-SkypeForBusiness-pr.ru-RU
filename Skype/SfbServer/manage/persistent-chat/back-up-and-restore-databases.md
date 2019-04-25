---
title: Резервное копирование и восстановление баз данных сохраняемого чата в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4f2b689b-7f15-48dc-a069-da7bc8527def
description: 'Сводка: Узнайте, как резервное копирование и восстановление баз данных сервера сохраняемого чата в Скайп для Business Server 2015.'
ms.openlocfilehash: a07321c7e9167e830a7af472e9022b669a45c3e7
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32222089"
---
# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a><span data-ttu-id="15b3c-103">Резервное копирование и восстановление баз данных сохраняемого чата в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="15b3c-103">Back up and restore Persistent Chat databases in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="15b3c-104">**Сводка:** Узнайте, как резервное копирование и восстановление баз данных сервера сохраняемого чата в Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="15b3c-104">**Summary:** Learn how to back up and restore Persistent Chat Server databases in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="15b3c-105">Persistent Chat Server требуется программное обеспечение баз данных SQL Server для хранения данных чат, например истории и контент, конфигурации, подготовке пользователей и других соответствующих метаданных.</span><span class="sxs-lookup"><span data-stu-id="15b3c-105">Persistent Chat Server requires SQL Server database software to store chat room data, such as history and content, configuration, user provisioning, and other relevant metadata.</span></span> <span data-ttu-id="15b3c-106">Кроме того Если включена дополнительная служба соответствия требованиям вашей организации есть правилам, которые требуют активности сохраняемого чата для архивации, программное обеспечение баз данных SQL Server используется для хранения данных соответствия требованиям, включая контент чата и события, такие как присоединении и выходе из комнаты.</span><span class="sxs-lookup"><span data-stu-id="15b3c-106">In addition, if your organization has regulations that require Persistent Chat activity to be archived, and the optional Compliance service is enabled, SQL Server database software is used to store compliance data, including chat content and events, such as joining and leaving rooms.</span></span> <span data-ttu-id="15b3c-107">В базе данных сохраняемого чата (mgc) будет храниться содержимое комнат чата.</span><span class="sxs-lookup"><span data-stu-id="15b3c-107">Chat room content is stored in the Persistent Chat database (mgc).</span></span> <span data-ttu-id="15b3c-108">Данные о соответствии хранятся в базе данных соответствия (mgccomp).</span><span class="sxs-lookup"><span data-stu-id="15b3c-108">Compliance data is stored in the Compliance database (mgccomp).</span></span> <span data-ttu-id="15b3c-109">Необходимо регулярно создавать резервные копии этих критически важных для бизнеса данных.</span><span class="sxs-lookup"><span data-stu-id="15b3c-109">This is business-critical data that should be backed up regularly.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="15b3c-110">Сохраняемый чат доступна в Скайп для Business Server 2015, но больше не поддерживается в Скайп для Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="15b3c-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="15b3c-111">Те же функциональные возможности доступны в группах.</span><span class="sxs-lookup"><span data-stu-id="15b3c-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="15b3c-112">Для получения дополнительных сведений см [Реализация из Скайп для бизнеса для групп Майкрософт](/microsoftteams/journey-skypeforbusiness-teams).</span><span class="sxs-lookup"><span data-stu-id="15b3c-112">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="15b3c-113">Если необходимо использовать сохраняемого чата, возможны либо перенос пользователей, которым требуется эта функция групп, или для дальнейшего использования Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="15b3c-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="back-up-the-databases"></a><span data-ttu-id="15b3c-114">Резервное копирование баз данных</span><span class="sxs-lookup"><span data-stu-id="15b3c-114">Back up the databases</span></span>

<span data-ttu-id="15b3c-115">Существует два способа создания резервной копии данных Persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="15b3c-115">There are two ways of backing up Persistent Chat data.</span></span> 
  
- <span data-ttu-id="15b3c-116">Резервное копирование SQL Server</span><span class="sxs-lookup"><span data-stu-id="15b3c-116">SQL Server Backup</span></span>
    
- <span data-ttu-id="15b3c-117">Командлет **Export-CsPersistentChatData** , который экспортирует данные сохраняемого сеанса беседы в виде файла</span><span class="sxs-lookup"><span data-stu-id="15b3c-117">The **Export-CsPersistentChatData** cmdlet, which exports Persistent Chat data as a file</span></span>
    
<span data-ttu-id="15b3c-118">Для данных, созданных с помощью резервного копирования SQL Server, требуется значительно больше места на диске (возможно, до 20 раз больше), чем для данных, созданных с помощью командлета **Export-CsPersistentChatData**, но ваше знакомство с процедурой резервного копирования SQL Server более вероятно.</span><span class="sxs-lookup"><span data-stu-id="15b3c-118">Data that is created by using SQL Server backup requires significantly more disk space—possibly 20 times more—than that created by the **Export-CsPersistentChatData** cmdlet, but SQL Server backup is likely to be a procedure with which you are familiar.</span></span>
  
<span data-ttu-id="15b3c-119">Чтобы использовать процедуры резервного копирования SQL, см. подробнее в документации по SQL.</span><span class="sxs-lookup"><span data-stu-id="15b3c-119">If you want to use SQL Server backup procedures, see your SQL documentation for more information.</span></span> 
  
<span data-ttu-id="15b3c-120">Если планируется использовать командлет **Export-CsPersistentChatData**, данную команду можно указать следующим образом:</span><span class="sxs-lookup"><span data-stu-id="15b3c-120">If you want to use the **Export-CsPersistentChatData** cmdlet, you can specify the command as follows:</span></span>
  
```
Export-CsPersistentChatData [-FileName <String>] <COMMON PARAMETERS>
```

<span data-ttu-id="15b3c-121">или</span><span class="sxs-lookup"><span data-stu-id="15b3c-121">or</span></span>
  
```
Export-CsPersistentChatData [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>
```

<span data-ttu-id="15b3c-p103">Например, приведенная ниже команда экспортирует данные сохраняемого чата из базы данных сохраняемого чата, расположенной на сервере atl-sql-001.contoso.com. Экспортируемые данные будут храниться в файле C:\Logs\PersistentChatData.zip. Поскольку параметр Level не задан, данная команда будет выполнять полный экспорт сведений о сохраняемом чате.</span><span class="sxs-lookup"><span data-stu-id="15b3c-p103">For example, the following command exports Persistent Chat data from the Persistent Chat database located on the server atl-sql-001.contoso.com; the exported data will be stored in the file C:\Logs\PersistentChatData.zip. Because the Level parameter was not specified, the command will do a full export of the Persistent Chat information:</span></span>
  
```
Export-CsPersistentChatData -DBInstance "atl-sql-001.contoso.com\rtc" -FileName "C:\Logs\PersistentChatData.zip"
```

## <a name="restore-the-databases"></a><span data-ttu-id="15b3c-124">Восстановление баз данных</span><span class="sxs-lookup"><span data-stu-id="15b3c-124">Restore the databases</span></span>

<span data-ttu-id="15b3c-125">Как восстановить данные Persistent Chat, зависит от метода, который можно использовать для резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="15b3c-125">How you restore your Persistent Chat data depends on the method that you used to back it up.</span></span> <span data-ttu-id="15b3c-126">Если были использованы процедуры резервного копирования SQL Server, необходимо использовать процедуры восстановления SQL Server.</span><span class="sxs-lookup"><span data-stu-id="15b3c-126">If you used SQL Server backup procedures, you must use SQL Server restore procedures.</span></span> <span data-ttu-id="15b3c-127">Если используется командлет **Export-CsPersistentChatData** для резервного копирования данных Persistent Chat, необходимо использовать командлет **Import-CsPersistentChatData** для восстановления данных:</span><span class="sxs-lookup"><span data-stu-id="15b3c-127">If you used the **Export-CsPersistentChatData** cmdlet to back up Persistent Chat data, then you must use the **Import-CsPersistentChatData** cmdlet to restore the data:</span></span>
  
```
Import-CsPersistentChatData -FileName <String> <COMMON PARAMETERS>
```

<span data-ttu-id="15b3c-128">или</span><span class="sxs-lookup"><span data-stu-id="15b3c-128">or</span></span>
  
```
Import-CsPersistentChatData -ByteInput <Byte > <COMMON PARAMETERS>
```
