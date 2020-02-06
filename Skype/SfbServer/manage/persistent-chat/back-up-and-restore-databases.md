---
title: Резервное копирование и восстановление баз данных сохраняемого чата в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4f2b689b-7f15-48dc-a069-da7bc8527def
description: Сводка. сведения о том, как архивировать и восстанавливать сохраняемые базы данных сервера чата в Skype для бизнеса Server 2015.
ms.openlocfilehash: 9da64a3ba6f6ad8053faebf0d536a610e02cce8f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817345"
---
# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a><span data-ttu-id="7d921-103">Резервное копирование и восстановление баз данных сохраняемого чата в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="7d921-103">Back up and restore Persistent Chat databases in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="7d921-104">**Сводка:** Сведения о том, как архивировать и восстанавливать сохраняемые базы данных сервера чата в Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="7d921-104">**Summary:** Learn how to back up and restore Persistent Chat Server databases in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="7d921-105">Для сервера сохраняемого чата требуется, чтобы программа базы данных SQL Server содержала данные комнаты чата, такие как журнал и содержимое, конфигурация, подготовка пользователей и другие необходимые метаданные.</span><span class="sxs-lookup"><span data-stu-id="7d921-105">Persistent Chat Server requires SQL Server database software to store chat room data, such as history and content, configuration, user provisioning, and other relevant metadata.</span></span> <span data-ttu-id="7d921-106">Кроме того, если в вашей организации есть нормативы, для которых требуется архивировать действия сохраняемого чата и включена служба соответствия требованиям, программное обеспечение баз данных SQL Server используется для хранения данных о соответствии требованиям, в том числе содержания и событий чата, например присоединение к комнатам и выход из нее.</span><span class="sxs-lookup"><span data-stu-id="7d921-106">In addition, if your organization has regulations that require Persistent Chat activity to be archived, and the optional Compliance service is enabled, SQL Server database software is used to store compliance data, including chat content and events, such as joining and leaving rooms.</span></span> <span data-ttu-id="7d921-107">Содержимое комнаты чата хранится в базе данных сохраняемого чата (MGC).</span><span class="sxs-lookup"><span data-stu-id="7d921-107">Chat room content is stored in the Persistent Chat database (mgc).</span></span> <span data-ttu-id="7d921-108">Данные о соответствии хранятся в базе данных соответствия (mgccomp).</span><span class="sxs-lookup"><span data-stu-id="7d921-108">Compliance data is stored in the Compliance database (mgccomp).</span></span> <span data-ttu-id="7d921-109">Необходимо регулярно создавать резервные копии этих критически важных для бизнеса данных.</span><span class="sxs-lookup"><span data-stu-id="7d921-109">This is business-critical data that should be backed up regularly.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="7d921-110">Сохраняемый чат доступен в Skype для бизнеса Server 2015, но больше не поддерживается в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="7d921-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="7d921-111">Такие же функции доступны в Teams.</span><span class="sxs-lookup"><span data-stu-id="7d921-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="7d921-112">Дополнительные сведения см. в статье [Начало перехода на Microsoft Teams](/microsoftteams/upgrade-start-here).</span><span class="sxs-lookup"><span data-stu-id="7d921-112">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="7d921-113">Если вам нужно использовать сохраняемый чат, то вы можете либо перенести пользователей, которым нужна эта функция, в Teams, либо продолжать использовать Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="7d921-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="back-up-the-databases"></a><span data-ttu-id="7d921-114">Резервное копирование баз данных</span><span class="sxs-lookup"><span data-stu-id="7d921-114">Back up the databases</span></span>

<span data-ttu-id="7d921-115">Существует два способа резервного копирования данных сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="7d921-115">There are two ways of backing up Persistent Chat data.</span></span> 
  
- <span data-ttu-id="7d921-116">Резервное копирование SQL Server</span><span class="sxs-lookup"><span data-stu-id="7d921-116">SQL Server Backup</span></span>
    
- <span data-ttu-id="7d921-117">Командлет **Export-ксперсистентчатдата** , который экспортирует сохраняемые данные чата в виде файла</span><span class="sxs-lookup"><span data-stu-id="7d921-117">The **Export-CsPersistentChatData** cmdlet, which exports Persistent Chat data as a file</span></span>
    
<span data-ttu-id="7d921-118">Для данных, созданных с помощью резервного копирования SQL Server, требуется значительно больше места на диске (возможно, до 20 раз больше), чем для данных, созданных с помощью командлета **Export-CsPersistentChatData**, но ваше знакомство с процедурой резервного копирования SQL Server более вероятно.</span><span class="sxs-lookup"><span data-stu-id="7d921-118">Data that is created by using SQL Server backup requires significantly more disk space—possibly 20 times more—than that created by the **Export-CsPersistentChatData** cmdlet, but SQL Server backup is likely to be a procedure with which you are familiar.</span></span>
  
<span data-ttu-id="7d921-119">Чтобы использовать процедуры резервного копирования SQL, см. подробнее в документации по SQL.</span><span class="sxs-lookup"><span data-stu-id="7d921-119">If you want to use SQL Server backup procedures, see your SQL documentation for more information.</span></span> 
  
<span data-ttu-id="7d921-120">Если планируется использовать командлет **Export-CsPersistentChatData**, данную команду можно указать следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7d921-120">If you want to use the **Export-CsPersistentChatData** cmdlet, you can specify the command as follows:</span></span>
  
```PowerShell
Export-CsPersistentChatData [-FileName <String>] <COMMON PARAMETERS>
```

<span data-ttu-id="7d921-121">или</span><span class="sxs-lookup"><span data-stu-id="7d921-121">or</span></span>
  
```PowerShell
Export-CsPersistentChatData [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>
```

<span data-ttu-id="7d921-p103">Например, приведенная ниже команда экспортирует данные сохраняемого чата из базы данных сохраняемого чата, расположенной на сервере atl-sql-001.contoso.com. Экспортируемые данные будут храниться в файле C:\Logs\PersistentChatData.zip. Поскольку параметр Level не задан, данная команда будет выполнять полный экспорт сведений о сохраняемом чате.</span><span class="sxs-lookup"><span data-stu-id="7d921-p103">For example, the following command exports Persistent Chat data from the Persistent Chat database located on the server atl-sql-001.contoso.com; the exported data will be stored in the file C:\Logs\PersistentChatData.zip. Because the Level parameter was not specified, the command will do a full export of the Persistent Chat information:</span></span>
  
```PowerShell
Export-CsPersistentChatData -DBInstance "atl-sql-001.contoso.com\rtc" -FileName "C:\Logs\PersistentChatData.zip"
```

## <a name="restore-the-databases"></a><span data-ttu-id="7d921-124">Восстановление баз данных</span><span class="sxs-lookup"><span data-stu-id="7d921-124">Restore the databases</span></span>

<span data-ttu-id="7d921-125">Способ восстановления сохраняемых данных чата зависит от того, какой метод вы использовали для архивации.</span><span class="sxs-lookup"><span data-stu-id="7d921-125">How you restore your Persistent Chat data depends on the method that you used to back it up.</span></span> <span data-ttu-id="7d921-126">Если были использованы процедуры резервного копирования SQL Server, необходимо использовать процедуры восстановления SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7d921-126">If you used SQL Server backup procedures, you must use SQL Server restore procedures.</span></span> <span data-ttu-id="7d921-127">Если вы использовали командлет **Export-ксперсистентчатдата** для резервного копирования сохраненных данных чата, необходимо использовать командлет **Import-ксперсистентчатдата** для восстановления данных.</span><span class="sxs-lookup"><span data-stu-id="7d921-127">If you used the **Export-CsPersistentChatData** cmdlet to back up Persistent Chat data, then you must use the **Import-CsPersistentChatData** cmdlet to restore the data:</span></span>
  
```PowerShell
Import-CsPersistentChatData -FileName <String> <COMMON PARAMETERS>
```

<span data-ttu-id="7d921-128">или</span><span class="sxs-lookup"><span data-stu-id="7d921-128">or</span></span>
  
```PowerShell
Import-CsPersistentChatData -ByteInput <Byte > <COMMON PARAMETERS>
```
