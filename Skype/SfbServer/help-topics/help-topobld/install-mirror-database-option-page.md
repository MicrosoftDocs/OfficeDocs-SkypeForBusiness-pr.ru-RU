---
title: Страница параметров установки зеркальной базы данных
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.InstallMirrorDatabaseOptionPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7500896a-14ea-4b11-aaee-be3d81314536
description: 'Настройте параметры зеркальной базы данных, определив следующие значения:'
ms.openlocfilehash: 5b1cf1160fc28efc8a7787693cc5dd439ea53a17
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34284258"
---
# <a name="install-mirror-database-option-page"></a><span data-ttu-id="5af39-103">Страница параметров установки зеркальной базы данных</span><span class="sxs-lookup"><span data-stu-id="5af39-103">Install Mirror Database Option Page</span></span>
 
<span data-ttu-id="5af39-104">Настройте **Параметры зеркальной базы данных** , определив следующие значения:</span><span class="sxs-lookup"><span data-stu-id="5af39-104">You configure **Mirror Database Settings** by defining the following:</span></span>
  
- <span data-ttu-id="5af39-105">Введите **путь к общей папке** , чтобы задать расположение для резервных файлов SQL Server для зеркальной базы данных.</span><span class="sxs-lookup"><span data-stu-id="5af39-105">Type the **Path to file share** to define the location for the backup SQL Server files for the database being mirrored.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5af39-106">Основной экземпляр SQL Server (как именованный экземпляр, так и экземпляр по умолчанию) должен иметь разрешения на запись в указанную здесь файловую общую.</span><span class="sxs-lookup"><span data-stu-id="5af39-106">The primary SQL Server instance (either named instance or default instance) must have write permissions to the file share you define here.</span></span> <span data-ttu-id="5af39-107">Зеркальному экземпляру SQL Server (именованному экземпляру или экземпляру по умолчанию) должны быть предоставлены разрешения на чтение для того же общего файлового файла.</span><span class="sxs-lookup"><span data-stu-id="5af39-107">The mirror SQL Server instance (either named instance or default instance) must have read permissions to the same file share.</span></span> 
  
  <span data-ttu-id="5af39-108">**ОК**. Принятие и фиксация изменений, внесенных в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="5af39-108">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="5af39-109">**Отмена**. Отмена изменений и закрытие диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="5af39-109">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="5af39-110">**Справка**. Отображение этого экрана справки.</span><span class="sxs-lookup"><span data-stu-id="5af39-110">**Help** Displays this help screen.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5af39-111">См. также</span><span class="sxs-lookup"><span data-stu-id="5af39-111">See also</span></span>

[<span data-ttu-id="5af39-112">Развертывание зеркального отображения SQL Server для обеспечения высокой доступности внутреннего сервера в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="5af39-112">Deploy SQL mirroring for Back End Server high availability in Skype for Business Server 2015</span></span>](../../deploy/deploy-high-availability-and-disaster-recovery/sql-mirroring-for-high-availability.md)
