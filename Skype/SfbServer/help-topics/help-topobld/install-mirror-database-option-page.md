---
title: Страница параметров установки зеркальной базы данных
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.InstallMirrorDatabaseOptionPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7500896a-14ea-4b11-aaee-be3d81314536
description: Параметры зеркальной базы данных определяются следующим образом.
ms.openlocfilehash: d522cc62f02d9021eaf6267db0b93aa4d42d3a3d
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215330"
---
# <a name="install-mirror-database-option-page"></a><span data-ttu-id="09de0-103">Страница параметров установки зеркальной базы данных</span><span class="sxs-lookup"><span data-stu-id="09de0-103">Install Mirror Database Option Page</span></span>
 
<span data-ttu-id="09de0-104">**Параметры зеркальной базы данных** определяются следующим образом.</span><span class="sxs-lookup"><span data-stu-id="09de0-104">You configure **Mirror Database Settings** by defining the following:</span></span>
  
- <span data-ttu-id="09de0-105">Введите **путь к общему файловому ресурсу** , чтобы определить расположение резервных файлов SQL Server для зеркальной базы данных.</span><span class="sxs-lookup"><span data-stu-id="09de0-105">Type the **Path to file share** to define the location for the backup SQL Server files for the database being mirrored.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="09de0-106">Основной экземпляр SQL Server (как именованный экземпляр, так и экземпляр по умолчанию) должен иметь разрешения на запись в общую папку, которую вы определили здесь.</span><span class="sxs-lookup"><span data-stu-id="09de0-106">The primary SQL Server instance (either named instance or default instance) must have write permissions to the file share you define here.</span></span> <span data-ttu-id="09de0-107">Зеркальный экземпляр SQL Server (как именованный экземпляр, так и экземпляр по умолчанию) должен иметь разрешения на чтение того же общего файлового ресурса.</span><span class="sxs-lookup"><span data-stu-id="09de0-107">The mirror SQL Server instance (either named instance or default instance) must have read permissions to the same file share.</span></span> 
  
  <span data-ttu-id="09de0-108">При нажатии кнопки **ОК** выполняется принятие и сохранение изменений в этом диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="09de0-108">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="09de0-109">При нажатии кнопки **Отмена** изменения отменяются, а диалоговое окно закрывается.</span><span class="sxs-lookup"><span data-stu-id="09de0-109">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="09de0-110">При нажатии кнопки **Справка** отображается данный экран справки.</span><span class="sxs-lookup"><span data-stu-id="09de0-110">**Help** Displays this help screen.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="09de0-111">См. также</span><span class="sxs-lookup"><span data-stu-id="09de0-111">See also</span></span>

[<span data-ttu-id="09de0-112">Развертывание зеркального отображения SQL для обеспечения высокой доступности внутреннего сервера в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="09de0-112">Deploy SQL mirroring for Back End Server high availability in Skype for Business Server 2015</span></span>](../../deploy/deploy-high-availability-and-disaster-recovery/sql-mirroring-for-high-availability.md)
