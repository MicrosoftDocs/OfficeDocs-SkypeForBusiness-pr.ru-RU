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
localization_priority: Normal
ms.assetid: 4f2b689b-7f15-48dc-a069-da7bc8527def
description: Сводка. сведения о том, как архивировать и восстанавливать сохраняемые базы данных сервера чата в Skype для бизнеса Server 2015.
ms.openlocfilehash: 07d904620bbc5925ec6457924af6ee1e48d98d55
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279363"
---
# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a><span data-ttu-id="f9b44-103">Резервное копирование и восстановление баз данных сохраняемого чата в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="f9b44-103">Back up and restore Persistent Chat databases in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="f9b44-104">**Сводка:** Сведения о том, как архивировать и восстанавливать сохраняемые базы данных сервера чата в Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="f9b44-104">**Summary:** Learn how to back up and restore Persistent Chat Server databases in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="f9b44-105">Для сервера сохраняемого чата требуется, чтобы программа базы данных SQL Server содержала данные комнаты чата, такие как журнал и содержимое, конфигурация, подготовка пользователей и другие необходимые метаданные.</span><span class="sxs-lookup"><span data-stu-id="f9b44-105">Persistent Chat Server requires SQL Server database software to store chat room data, such as history and content, configuration, user provisioning, and other relevant metadata.</span></span> <span data-ttu-id="f9b44-106">Кроме того, если в вашей организации есть нормативы, для которых требуется архивировать действия сохраняемого чата и включена служба соответствия требованиям, программное обеспечение баз данных SQL Server используется для хранения данных о соответствии требованиям, в том числе содержания и событий чата, например присоединение к комнатам и выход из нее.</span><span class="sxs-lookup"><span data-stu-id="f9b44-106">In addition, if your organization has regulations that require Persistent Chat activity to be archived, and the optional Compliance service is enabled, SQL Server database software is used to store compliance data, including chat content and events, such as joining and leaving rooms.</span></span> <span data-ttu-id="f9b44-107">Содержимое комнаты чата хранится в базе данных сохраняемого чата (MGC).</span><span class="sxs-lookup"><span data-stu-id="f9b44-107">Chat room content is stored in the Persistent Chat database (mgc).</span></span> <span data-ttu-id="f9b44-108">Данные о соответствии хранятся в базе данных соответствия (mgccomp).</span><span class="sxs-lookup"><span data-stu-id="f9b44-108">Compliance data is stored in the Compliance database (mgccomp).</span></span> <span data-ttu-id="f9b44-109">Необходимо регулярно создавать резервные копии этих критически важных для бизнеса данных.</span><span class="sxs-lookup"><span data-stu-id="f9b44-109">This is business-critical data that should be backed up regularly.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="f9b44-110">Сохраняемый чат доступен в Skype для бизнеса Server 2015, но больше не поддерживается в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f9b44-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="f9b44-111">Эта функция доступна в Teams.</span><span class="sxs-lookup"><span data-stu-id="f9b44-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="f9b44-112">Дополнительные сведения можно найти в разделе [путешествие из Skype для бизнеса в Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span><span class="sxs-lookup"><span data-stu-id="f9b44-112">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="f9b44-113">Если вы хотите использовать сохраняемый чат, вы можете либо перенести пользователей, которым требуются эти функции, в Teams, либо продолжить работу с Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="f9b44-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="back-up-the-databases"></a><span data-ttu-id="f9b44-114">Резервное копирование баз данных</span><span class="sxs-lookup"><span data-stu-id="f9b44-114">Back up the databases</span></span>

<span data-ttu-id="f9b44-115">Существует два способа резервного копирования данных сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="f9b44-115">There are two ways of backing up Persistent Chat data.</span></span> 
  
- <span data-ttu-id="f9b44-116">Резервное копирование SQL Server</span><span class="sxs-lookup"><span data-stu-id="f9b44-116">SQL Server Backup</span></span>
    
- <span data-ttu-id="f9b44-117">Командлет **Export-ксперсистентчатдата** , который экспортирует сохраняемые данные чата в виде файла</span><span class="sxs-lookup"><span data-stu-id="f9b44-117">The **Export-CsPersistentChatData** cmdlet, which exports Persistent Chat data as a file</span></span>
    
<span data-ttu-id="f9b44-118">Для данных, созданных с помощью резервного копирования SQL Server, требуется значительно больше места на диске (возможно, до 20 раз больше), чем для данных, созданных с помощью командлета **Export-CsPersistentChatData**, но ваше знакомство с процедурой резервного копирования SQL Server более вероятно.</span><span class="sxs-lookup"><span data-stu-id="f9b44-118">Data that is created by using SQL Server backup requires significantly more disk space—possibly 20 times more—than that created by the **Export-CsPersistentChatData** cmdlet, but SQL Server backup is likely to be a procedure with which you are familiar.</span></span>
  
<span data-ttu-id="f9b44-119">Чтобы использовать процедуры резервного копирования SQL, см. подробнее в документации по SQL.</span><span class="sxs-lookup"><span data-stu-id="f9b44-119">If you want to use SQL Server backup procedures, see your SQL documentation for more information.</span></span> 
  
<span data-ttu-id="f9b44-120">Если планируется использовать командлет **Export-CsPersistentChatData**, данную команду можно указать следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f9b44-120">If you want to use the **Export-CsPersistentChatData** cmdlet, you can specify the command as follows:</span></span>
  
```
Export-CsPersistentChatData [-FileName <String>] <COMMON PARAMETERS>
```

<span data-ttu-id="f9b44-121">или</span><span class="sxs-lookup"><span data-stu-id="f9b44-121">or</span></span>
  
```
Export-CsPersistentChatData [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>
```

<span data-ttu-id="f9b44-p103">Например, приведенная ниже команда экспортирует данные сохраняемого чата из базы данных сохраняемого чата, расположенной на сервере atl-sql-001.contoso.com. Экспортируемые данные будут храниться в файле C:\Logs\PersistentChatData.zip. Поскольку параметр Level не задан, данная команда будет выполнять полный экспорт сведений о сохраняемом чате.</span><span class="sxs-lookup"><span data-stu-id="f9b44-p103">For example, the following command exports Persistent Chat data from the Persistent Chat database located on the server atl-sql-001.contoso.com; the exported data will be stored in the file C:\Logs\PersistentChatData.zip. Because the Level parameter was not specified, the command will do a full export of the Persistent Chat information:</span></span>
  
```
Export-CsPersistentChatData -DBInstance "atl-sql-001.contoso.com\rtc" -FileName "C:\Logs\PersistentChatData.zip"
```

## <a name="restore-the-databases"></a><span data-ttu-id="f9b44-124">Восстановление баз данных</span><span class="sxs-lookup"><span data-stu-id="f9b44-124">Restore the databases</span></span>

<span data-ttu-id="f9b44-125">Способ восстановления сохраняемых данных чата зависит от того, какой метод вы использовали для архивации.</span><span class="sxs-lookup"><span data-stu-id="f9b44-125">How you restore your Persistent Chat data depends on the method that you used to back it up.</span></span> <span data-ttu-id="f9b44-126">Если были использованы процедуры резервного копирования SQL Server, необходимо использовать процедуры восстановления SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f9b44-126">If you used SQL Server backup procedures, you must use SQL Server restore procedures.</span></span> <span data-ttu-id="f9b44-127">Если вы использовали командлет **Export-ксперсистентчатдата** для резервного копирования сохраненных данных чата, необходимо использовать командлет **Import-ксперсистентчатдата** для восстановления данных.</span><span class="sxs-lookup"><span data-stu-id="f9b44-127">If you used the **Export-CsPersistentChatData** cmdlet to back up Persistent Chat data, then you must use the **Import-CsPersistentChatData** cmdlet to restore the data:</span></span>
  
```
Import-CsPersistentChatData -FileName <String> <COMMON PARAMETERS>
```

<span data-ttu-id="f9b44-128">или</span><span class="sxs-lookup"><span data-stu-id="f9b44-128">or</span></span>
  
```
Import-CsPersistentChatData -ByteInput <Byte > <COMMON PARAMETERS>
```
